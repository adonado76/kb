---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guía práctica: Autenticarse en la API"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Integrar y ampliar"
  - "Integración de API"
source_path: "studio/new-uc/howtoguides/integrate-extend/how-to-authenticate-api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía práctica: Autenticarse en la API

**Objetivo:** Obtener un token de autenticación para realizar solicitudes autorizadas a la API

**Tiempo estimado:** 15-30 minutos (configuración inicial)

**Cuándo utilizarlo:** Antes de cualquier operación de carga o descarga. Se requieren tokens para todas las llamadas a la API.

**Requisitos previos**

- Una cuenta de usuario en la Administración de acceso mejorado con acceso a la API
- Se han generado claves API y se ha concedido acceso a tu entorno de destino
- Acceso a la red a través de frontdoor.apptio.com

## Permisos necesarios

**Para realizar operaciones de carga,** tu cuenta necesita:

- AccessDev
- UploadData

**Para realizar descargas,** tu cuenta debe cumplir los siguientes requisitos:

- AccessProd, AccessStg
- AllDataView, DrillDown
- ViewMetricReports, ViewObjectReports, ViewTransformReports, ViewTransparencyReports, ViewUnitReports
- ViewReportsSavedForEveryone

Consejo: Es posible que algunos permisos de visualización no sean necesarios, dependiendo de los productos instalados y de los tipos de datos que se descarguen. En caso de duda, comprueba tu configuración.

## Método 1: Autenticación mediante claves API (recomendado)

Las claves API son el método de autenticación recomendado por motivos de seguridad. Permiten un control de acceso muy preciso y pueden revocarse sin necesidad de cambiar las contraseñas de los usuarios.

**Paso 1: Generar claves API en la administración de acceso mejorado**

1. Inicie sesión en la Administración de acceso mejorado
2. Ve a la configuración de tu cuenta de usuario
3. Genera un nuevo par de claves API (pública y privada)
4. Haz clic en «Conceder acceso» junto al nombre de la clave para autorizar el acceso al entorno
5. Guarda la clave secreta en un lugar seguro; una vez creada, no se podrá recuperar

**Paso 2: Solicitar un token de autenticación**

**cURL:**

```
curl -X POST https://frontdoor.apptio.com/service/apikeylogin \
 -H "Content-Type: application/json" \
 -H "Accept: application/json" \
 -d '{"keyAccess":"YOUR_PUBLIC_KEY","keySecret":"YOUR_SECRET_KEY"}'
```

**Python:**

```
import requests
import json
 
def get_auth_token(public_key, secret_key):
 """Authenticate with TBM Studio API using API keys."""
 url = "https://frontdoor.apptio.com/service/apikeylogin"
 headers = {
 "Content-Type": "application/json",
 "Accept": "application/json"
 }
 payload = {
 "keyAccess": public_key,
 "keySecret": secret_key
 }
 
 response = requests.post(url, headers=headers, json=payload)
 response.raise_for_status()
 
 # Token is returned in cookies
 token = response.cookies.get('apptio-opentoken')
 return token
 
# Usage
token = get_auth_token("your_public_key", "your_secret_key")
```

**Paso 3: Obtén tu ID de entorno**

El identificador de entorno es necesario para las llamadas a la API posteriores. Se mantiene constante a menos que cambie la configuración de la administración de acceso mejorado.

```
curl -X GET "https://frontdoor.apptio.com/api/environment/yourdomain.com/main" \
 -H "Content-Type: application/json" \
 -H "apptio-opentoken: YOUR_TOKEN"
```

**Python:**

```
def get_environment_id(token, domain, frontdoor_env="main"):
 """Get the environment ID for API calls."""
 url = f"https://frontdoor.apptio.com/api/environment/{domain}/{frontdoor_env}"
 headers = {
 "Content-Type": "application/json",
 "apptio-opentoken": token
 }
 
 response = requests.get(url, headers=headers)
 response.raise_for_status()
 
 return response.json()["id"]
 
# Usage
env_id = get_environment_id(token, "yourdomain.com")
```

## Método 2: Autenticarse con nombre de usuario y contraseña

Advertencia: La autenticación mediante nombre de usuario y contraseña es compatible, pero no se recomienda para sistemas de producción. Utiliza claves API siempre que sea posible para garantizar una mayor seguridad.

**cURL:**

```
curl -X POST https://frontdoor.apptio.com/service/apikeylogin \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -d '{"userId":"user@domain.com","password":"your_password"}'
```

**Python:**

```
def get_auth_token_password(user_id, password):
    """Authenticate using username and password."""
    url = "https://frontdoor.apptio.com/service/apikeylogin"
    headers = {
        "Content-Type": "application/json",
        "Accept": "application/json"
    }
    payload = {
        "userId": user_id,
        "password": password
    }
    
    response = requests.post(url, headers=headers, json=payload)
    response.raise_for_status()
    
    return response.cookies.get('apptio-opentoken')
```

## Resultados previstos

- Si la autenticación se realiza correctamente, se devuelve un «apptio-opentoken» en las cookies de respuesta
- El punto final de identificación del entorno devuelve una respuesta JSON que contiene el identificador numérico del entorno
- Ambos valores son obligatorios para todas las operaciones posteriores de la API

## Errores habituales

- **No se ha concedido acceso al entorno a la clave:** tras crear una clave de API, debes concederle explícitamente acceso a los entornos a través del enlace «Conceder acceso».
- **Faltan permisos:** asegúrate de que se haya asignado el permiso « UploadData ».
- **Caducidad del token:** los tokens de autenticación caducan. Implementa la lógica de actualización de tokens en los procesos de larga duración.

**Tema principal:** [Integración de API](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
