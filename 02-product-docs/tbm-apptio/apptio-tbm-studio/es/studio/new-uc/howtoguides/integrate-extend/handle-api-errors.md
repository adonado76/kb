---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guía práctica: cómo gestionar los errores de la API"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Integrar y ampliar"
  - "Integración de API"
source_path: "studio/new-uc/howtoguides/integrate-extend/handle-api-errors.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía práctica: cómo gestionar los errores de la API

**Objetivo:** Implementar una gestión de errores sólida y una lógica de reintentos para las integraciones de API en producción

**Tiempo estimado:** entre 30 y 45 minutos para la implementación

**Cuándo utilizarlo: Para** crear integraciones de producción que deban gestionar con flexibilidad los problemas de red, la caducidad de la autenticación y las interrupciones del servicio.

## Códigos de respuesta de la API

|  |  |  |
| --- | --- | --- |
| **Código** | **Descripción** | **Acción** |
| 200 | Éxito (GET) | Datos de respuesta del proceso |
| 201 | Creación correcta | El recurso se ha creado correctamente |
| 202 | Actualización correcta | El recurso se ha actualizado correctamente |
| 400 | Cadena de API incorrecta / Solicitud no válida | Comprueba el formato, los parámetros y el cuerpo de la solicitud de URL |
| 401 | No autorizado | Vuelve a iniciar sesión e inténtalo de nuevo |
| 403 | Prohibido | Comprueba los permisos de los usuarios |
| 404 | No encontrado | Comprueba que el recurso existe (proyecto, tabla, periodo de tiempo) |
| 500 | Error interno del servidor | Vuelve a intentarlo con un retraso exponencial; si el problema persiste, ponte en contacto con el servicio de asistencia |

## Comprender las respuestas de error

Las respuestas de error devuelven un objeto JSON con un campo «message» que describe el problema:

```
{
 "message": "Poorly formatted date string: 'SOMEDATE:2010'. Ought to be of the form 'granularity':'year'."
}
```

## Mensajes de error habituales:

|  |  |  |
| --- | --- | --- |
| **Patrón de mensajes** | **Causa** | **Solución** |
| Formato incorrecto de la cadena de fecha | Formato de intervalo de tiempo no válido | Utiliza el formato Mes:Año (por ejemplo, January:2024 ) |
| El usuario X no existe | Nombre de usuario no válido en la solicitud | Comprueba que el nombre de usuario tenga el formato correcto y que la cuenta exista |
| Acceso denegado | Permisos insuficientes | Comprueba que la cuenta disponga de los conjuntos de permisos necesarios |
| No se ha encontrado la tabla | La tabla de destino no existe | Comprueba la ortografía del nombre de la tabla y el proyecto |

## Implementación de la lógica de reintento

Las integraciones de producción deben implementar un retroceso exponencial para los fallos transitorios:

```
import requests
import time
import logging
 
class TBMStudioAPIClient:
 """Production-ready TBM Studio API client with retry logic."""
 
 def __init__(self, customer_id, domain, max_retries=3, base_delay=1.0):
 self.customer_id = customer_id
 self.domain = domain
 self.max_retries = max_retries
 self.base_delay = base_delay
 self.token = None
 self.env_id = None
 self.logger = logging.getLogger(__name__)
 
 def authenticate(self, public_key, secret_key):
 """Authenticate and store token."""
 url = "https://frontdoor.apptio.com/service/apikeylogin"
 response = self._make_request(
 "POST", url,
 json={"keyAccess": public_key, "keySecret": secret_key},
 headers={"Content-Type": "application/json"}
 )
 self.token = response.cookies.get('apptio-opentoken')
 
 # Get environment ID
 env_url = f"https://frontdoor.apptio.com/api/environment/{self.domain}/main"
 env_response = self._make_request("GET", env_url)
 self.env_id = env_response.json()["id"]
 
 def _make_request(self, method, url, **kwargs):
 """Make HTTP request with retry logic."""
 last_exception = None
 
 for attempt in range(self.max_retries):
 try:
 # Add auth headers if authenticated
 if self.token and 'headers' not in kwargs:
 kwargs['headers'] = {}
 if self.token:
 kwargs['headers'].update({
 "apptio-opentoken": self.token,
 "apptio-current-environment": str(self.env_id) if self.env_id else "",
 "app-type": "Flagship",
 "app-version": "NA"
 })
 
 response = requests.request(method, url, **kwargs)
 
 # Check for retryable status codes
 if response.status_code == 401:
 self.logger.warning("Token expired, re-authentication required")
 raise AuthenticationError("Token expired")
 
 if response.status_code >= 500:
 response.raise_for_status() # Will be caught and retried
 
 response.raise_for_status()
 return response
 
 except requests.exceptions.RequestException as e:
 last_exception = e
 
 if attempt < self.max_retries - 1:
 delay = self.base_delay * (2 ** attempt) # Exponential backoff
 self.logger.warning(
 f"Request failed (attempt {attempt + 1}/{self.max_retries}), "
 f"retrying in {delay}s: {e}"
 )
 time.sleep(delay)
 
 raise last_exception
 
 def upload(self, project, table, time_period, file_path, action="overwrite"):
 """Upload data with error handling."""
 import urllib.parse
 
 project_enc = urllib.parse.quote(project)
 table_enc = urllib.parse.quote(table)
 
 url = (f"https://{self.customer_id}.apptio.com/biit/api/v1/"
 f"{self.domain}/{project_enc}/{table_enc}/{time_period}/{action}")
 
 with open(file_path, 'rb') as f:
 response = self._make_request("POST", url, files={'myfile': f})
 
 return response.json()
 
 
class AuthenticationError(Exception):
 """Raised when authentication fails or token expires."""
 pass
 
 
# Usage with error handling
def main():
 logging.basicConfig(level=logging.INFO)
 
 client = TBMStudioAPIClient("acme", "acme.com")
 
 try:
 client.authenticate("public_key", "secret_key")
 result = client.upload(
 project="Cost Transparency",
 table="GL Data",
 time_period="January:2024",
 file_path="data.csv"
 )
 print(f"Upload successful: {result}")
 
 except AuthenticationError:
 print("Authentication failed. Check API credentials.")
 except requests.exceptions.HTTPError as e:
 print(f"API error: {e.response.status_code} - {e.response.text}")
 except Exception as e:
 print(f"Unexpected error: {e}")
```

## Estrategia de actualización de tokens

En el caso de los procesos de larga duración, implementa una actualización proactiva de los tokens:

```
import time
from datetime import datetime, timedelta
 
class TokenManager:
 """Manage API token lifecycle."""
 
 def __init__(self, client, refresh_margin_minutes=5):
 self.client = client
 self.refresh_margin = timedelta(minutes=refresh_margin_minutes)
 self.token_expiry = None
 self.token_lifetime = timedelta(hours=1) # Adjust based on actual expiry
 
 def get_valid_token(self, public_key, secret_key):
 """Get a valid token, refreshing if necessary."""
 now = datetime.now()
 
 if (self.token_expiry is None or 
 now >= self.token_expiry - self.refresh_margin):
 self.client.authenticate(public_key, secret_key)
 self.token_expiry = now + self.token_lifetime
 
 return self.client.token
```

## Buenas prácticas en la tala

- **Registrar todas las llamadas a la API:** incluir la marca de tiempo, el punto final, el método HTTP y el estado de la respuesta
- **Registrar los tiempos de respuesta:** supervisar si se produce una disminución del rendimiento
- **No registrar nunca las credenciales:** ocultar los tokens, las claves API y las contraseñas de los registros
- **Registrar las respuestas de error:** Capturar los mensajes de error completos para la resolución de problemas
- **Utiliza el registro estructurado:** formatea los registros en formato JSON para facilitar su interpretación y análisis

Advertencia: Evita registrar datos confidenciales, como claves de API, tokens o información de identificación personal. Utiliza marcadores de posición o cifrado para ocultar la información identificable en los registros.

## Errores habituales

- **No se realizan reintentos ante errores 500:** los errores del servidor suelen ser pasajeros. Aplica siempre el reintento con retrasos progresivos.
- **Ignorar los límites de frecuencia:** aunque no se indique explícitamente, evita enviar solicitudes en rápida sucesión. Añade retrasos entre las operaciones por lotes.
- **No gestionar la caducidad del token:** gestiona siempre las respuestas 401 volviendo a autenticarte e intentando de nuevo.
- **Falta el análisis de errores:** analiza y registra siempre el campo «mensaje» de las respuestas de error para obtener un diagnóstico significativo.

**Tema principal:** [Integración de API](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
