---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guía práctica: cómo subir datos a través de la API"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Integrar y ampliar"
  - "Integración de API"
source_path: "studio/new-uc/howtoguides/integrate-extend/upload-data-via-api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía práctica: cómo subir datos a través de la API

**Objetivo:** Cargar archivos de datos en las tablas de TBM Studio mediante programación

**Tiempo estimado:** entre 10 y 20 minutos por integración

**Cuándo utilizarlo: para** automatizar cargas de datos mensuales, integrarse con procesos ETL o realizar cargas desde sistemas en los que no se pueden instalar los agentes de « DataLink ».

**Requisitos previos**

- Token de autenticación válido e ID de entorno (consulte «Autenticarse con la API»)
- Permisos de carga asignados a tu cuenta de API
- Archivo de datos en un formato compatible ( CSV, TSV, CSV.GZ o TSV.GZ )

## Estructura de la API « URL »

`https://[customerid].apptio.com/biit/api/v1/[domain]/[project]/[table]/[time-period]/[action]`

**URL Parámetros:**

|  |  |  |
| --- | --- | --- |
| **Parámetro** | **Obligatorio** | **Descripción** |
| ID de cliente | Sí | Tu ID de cliente de Apptio (por ejemplo, acme) |
| Dominio | Sí | Tu dominio de cliente (por ejemplo, acme.com ) |
| proyecto | Sí | Nombre del proyecto de destino (codificado en URL, si contiene espacios) |
| tabla | Sí | Nombre de la tabla de destino (codificado según URL si contiene espacios) |
| período | Sí | Apptio formato de fecha (por ejemplo, January:2024 ) o actual |
| acción | Nee | añadir o sobrescribir (por defecto, sobrescribir) |

**Parámetros adicionales:**

|  |  |  |
| --- | --- | --- |
| **Parámetro** | **Valores** | **Descripción** |
| force | verdadero/falso | Anular las comprobaciones de validación de datos. No se puede combinar con la acción de URL; utiliza el cuerpo de la solicitud POST en su lugar. |

## Pasos

**Paso 1: Prepara tu archivo de datos**

- Asegúrate de que los datos estén en formato « CSV » o TSV
- Los encabezados de las columnas deben coincidir con el esquema de la tabla de destino
- En el caso de archivos grandes, comprímelos con gzip (. csv.gz o. tsv.gz )

**Paso 2: Sube el archivo**

**cURL:**

```
curl -X POST "https://customer.apptio.com/biit/api/v1/customer.com/Cost%20Transparency/GL%20Data/January:2024/overwrite" \
 -H "apptio-opentoken: YOUR_TOKEN" \
 -H "apptio-current-environment: YOUR_ENV_ID" \
 -H "app-type: Flagship" \
 -H "app-version: NA" \
 -F "myfile=@/path/to/data.csv"
```

**Python:**

```
import requests
import urllib.parse
 
def upload_data(token, env_id, customer_id, domain, project, table, 
 time_period, file_path, action="overwrite"):
 """
 Upload data to TBM Studio via API.
 
 Args:
 token: Authentication token from login
 env_id: Environment ID
 customer_id: Your Apptio customer ID
 domain: Your domain (e.g., 'customer.com')
 project: Target project name
 table: Target table name
 time_period: Time period (e.g., 'January:2024' or 'current')
 file_path: Path to the data file
 action: 'append' or 'overwrite' (default: 'overwrite')
 
 Returns:
 dict: Response containing md5, length, and fileName
 """
 # URL-encode project and table names
 project_encoded = urllib.parse.quote(project)
 table_encoded = urllib.parse.quote(table)
 
 url = (f"https://{customer_id}.apptio.com/biit/api/v1/"
 f"{domain}/{project_encoded}/{table_encoded}/"
 f"{time_period}/{action}")
 
 headers = {
 "apptio-opentoken": token,
 "apptio-current-environment": str(env_id),
 "app-type": "Flagship",
 "app-version": "NA"
 }
 
 with open(file_path, 'rb') as f:
 files = {'myfile': f}
 response = requests.post(url, headers=headers, files=files)
 
 response.raise_for_status()
 return response.json()
 
# Usage example
result = upload_data(
 token=token,
 env_id=env_id,
 customer_id="acme",
 domain="acme.com",
 project="Cost Transparency",
 table="GL Data",
 time_period="January:2024",
 file_path="/path/to/gl_data.csv"
)
print(f"Upload complete: {result['fileName']}, {result['length']} bytes")
```

## Resultados previstos

Si la carga se realiza correctamente, se devuelve una respuesta JSON:

```
{
 "md5": "3727119d89edcdd71377e39e18f3a5e1",
 "length": 13,
 "fileName": "data.csv"
}
```

Una vez realizada la carga, en la pestaña «Datos > Resumen» de TBM Studio aparece «Datos de la API» en el campo «Origen».

## Añadir frente a sobrescribir

|  |  |  |
| --- | --- | --- |
| **Acción** | **Comportamiento** | **Caso de uso** |
| sobrescribir | Sustituye todos los datos existentes en el periodo de tiempo seleccionado | Actualización mensual completa de los datos |
| añadir | Añade datos a los registros existentes | Actualizaciones incrementales, con la incorporación de nuevos registros |

Consejo: Para utilizar los parámetros «action» y «force», inclúyelos en el cuerpo de la solicitud POST como campos de formulario, en lugar de en el atributo « URL »: --form "action=append" --form "force=true"

## Errores habituales

- **URL Codificación:** Los nombres de proyectos y tablas que contengan espacios deben codificarse según el estándar « URL » (los espacios se sustituyen por %20 o +).
- **Formato de fecha:** Utiliza el formato exacto Mes:Año (por ejemplo, January:2024 ). «current» utiliza el mes natural actual.
- **Tipo MIME:** El único tipo MIME admitido es multipart/form-data.
- **Creación de la tabla:** si la tabla de destino no existe, la API la crea en el primer periodo del proyecto, y los datos aparecen en el periodo especificado.

**Tema principal:** [Integración de API](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
