---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guía práctica: Descargar datos a través de la API"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Integrar y ampliar"
  - "Integración de API"
source_path: "studio/new-uc/howtoguides/integrate-extend/download-data-api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía práctica: Descargar datos a través de la API

**Objetivo:** Extraer datos de las tablas y los informes de TBM Studio mediante programación

**Tiempo estimado:** entre 10 y 15 minutos por integración

**Cuándo utilizarlo: para** extraer datos con fines de análisis externo, alimentar almacenes de datos o integrarlos con herramientas de inteligencia empresarial.

**Requisitos previos**

- Token de autenticación válido e ID de entorno
- Permisos de descarga/visualización asignados a tu cuenta de API
- URL e de la API para la tabla o el informe de destino (obtenido desde la interfaz de usuario de TBM Studio)

## Paso 1: Obtener la API « URL » de TBM Studio

**Para las tablas:**

1. Ve a la tabla en TBM Studio
2. Selecciona la pestaña «Inicio», haz clic en «Exportar» y, a continuación, selecciona «Mostrar API» URL
3. Copia el texto « URL » del cuadro de diálogo modal

**Para las tablas y los gráficos de los informes:**

1. Haz clic con el botón derecho del ratón en el elemento del informe (tabla o gráfico)
2. Selecciona «Mostrar API» ( URL ) en el menú contextual
3. Copia el enlace URL para obtener el formato que desees (TSV, JSON o Excel)

## Paso 2: Descargar los datos

**cURL:**

```
# Download as TSV
curl -X GET "https://customer.apptio.com/biit/api/v2/domains/customer.com/projects/Cost%20Transparency/tables/GL%20Data/dates/Jan:FY2024.tsv" \
 -H "Content-Type: text/tab-separated-values" \
 -H "apptio-opentoken: YOUR_TOKEN" \
 -H "apptio-current-environment: YOUR_ENV_ID" \
 -o output.tsv
```

**Python:**

```
import requests
 
def download_data(token, env_id, api_url, output_path, format="tsv"):
 """
 Download data from TBM Studio via API.
 
 Args:
 token: Authentication token
 env_id: Environment ID
 api_url: API URL obtained from TBM Studio
 output_path: Path to save the downloaded file
 format: Output format ('tsv', 'json', 'xlsx')
 
 Returns:
 str: Path to downloaded file
 """
 content_types = {
 "tsv": "text/tab-separated-values",
 "json": "application/json",
 "xlsx": "application/vnd.openxmlformats-officedocument.spreadsheetml.sheet"
 }
 
 headers = {
 "Content-Type": content_types.get(format, "text/tab-separated-values"),
 "apptio-opentoken": token,
 "apptio-current-environment": str(env_id),
 "app-type": "Flagship",
 "app-version": "NA"
 }
 
 response = requests.get(api_url, headers=headers)
 response.raise_for_status()
 
 with open(output_path, 'wb') as f:
 f.write(response.content)
 
 return output_path
 
# Usage example
download_data(
 token=token,
 env_id=env_id,
 api_url="https://customer.apptio.com/biit/api/v2/domains/customer.com/projects/Cost%20Transparency/tables/GL%20Data/dates/Jan:FY2024.tsv",
 output_path="gl_data.tsv"
)
```

## Personalización de la descarga

**Cambiar el delimitador:**

Añade el parámetro delimitador con un carácter codificado en « URL »:

# Utilizar la barra vertical como delimitador ( %7C = |)

...tables/GL%20Data/dates/Jan:FY2024.tsv?delimiter=%7C

**Sustitución de caracteres delimitadores en los datos:**

Si tus datos contienen el carácter delimitador, utiliza delimiterReplacement:

# Sustituir los caracteres de barra vertical en los datos por comas

...?delimiter=%7C&delimiterReplacement=%2C

## Descarga de tablas publicadas

Las tablas publicadas proporcionan conjuntos de datos estables y controlados por esquemas, ideales para integraciones externas.

1. En el Explorador de proyectos, haz clic con el botón derecho del ratón en la tabla publicada
2. Selecciona «Mostrar API» URL y copia el enlace URL
3. Utiliza el enlace URL con el mismo código de descarga que se muestra arriba

Consejo: Las tablas publicadas se calculan previamente de forma predeterminada, lo que garantiza tiempos de respuesta rápidos de la API. Úsalos en lugar de las exportaciones de informes puntuales para las integraciones de producción.

## Formatos de descarga compatibles

|  |  |  |  |
| --- | --- | --- | --- |
| **Formato** | **Extensión** | **Tipo de contenido** | **Ideal para** |
| Separado por tabulaciones | .tsv | texto/valores separados por tabulaciones | Archivos de gran tamaño, procesamiento de datos |
| JSON | .json | application/json | Integraciones de API, aplicaciones web |
| Excel | .xlsx | application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Análisis fácil de usar |

## Errores habituales

- **Formato de fecha en URL :** Las URL de descarga utilizan el formato del año fiscal (por ejemplo, Jan:FY2024 ), que puede diferir del formato de carga.
- **Tiempo de espera para archivos grandes:** en el caso de conjuntos de datos muy grandes, utiliza el formato TSV en lugar de Excel. Considera la posibilidad de habilitar el precálculo para las tablas publicadas.
- **URL de los informes:** Las URL de la API de informes son específicas del elemento de informe. Los cambios en la estructura del informe pueden invalidar el documento « URL ».

**Tema principal:** [Integración de API](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
