---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "API del servicio de subida de archivos"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Integrar y ampliar"
  - "Integración de API"
source_path: "studio/admin/uploader-service-api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API del servicio de subida de archivos

**Se aplica a** : TBM Studio 12.0 y posteriores

El Apptio Uploader Service (ULS) es un nuevo vehículo para cargar datos en los proyectos Apptio. El ULS mejora el proceso existente de [la API Apptio](the-apptio-api.html "Se aplica a: TBM Studio 12.0 y posteriores") al admitir cargas de archivos más grandes y añadir las siguientes funciones:

- Los archivos de gran tamaño se cargan en varias partes.
- Las subidas pueden cancelarse.
- El estado de una carga multiparte se incluye en el último paso de incorporación.
- Se pueden registrar varias cargas como un único grupo en el proyecto de destino Apptio.
- Se admite la carga paralela de varias piezas.
- Se admite el procesamiento asíncrono de datos en el proyecto Apptio.
- Todo el transporte de datos se realiza dentro de la región y cumple la legislación sobre localización de datos.

Para ver un ejemplo de implementación, consulte el [tutorial de la API del servicio de carga](https://community.apptio.com/viewdocument/uploader-service-api-tutorial "(se abre en una pestaña o una ventana nueva)").

## Puntos finales del servicio Uploader

Para acceder al ULS, utilice una de las siguientes direcciones UrLs, en función de la región en la que tenga lugar la carga

- América del Norte - [https://datalink.apptio.com/uls](https://datalink.apptio.com/uls "(se abre en una pestaña o una ventana nueva)")
- UE - [https://datalink-eu.apptio.com/uls](https://datalink-eu.apptio.com/uls "(se abre en una pestaña o una ventana nueva)")
- APAC - [https://datalink-au.apptio.com/uls](https://datalink-au.apptio.com/uls "(se abre en una pestaña o una ventana nueva)")
- Oriente Medio - [https://datalink-me.apptio.com/uls](https://datalink-me.apptio.com/uls "(se abre en una pestaña o una ventana nueva)")

## Sintaxis de la API REST

La base URL para las llamadas a la API es la siguiente:

`<ULS_URL>/api/<VERSION>`

Actualmente, hay un valor válido para **VERSION** : v1. Por ejemplo, en Norteamérica la base URL sería: https://datalink.apptio.com/uls/v1. Los puntos finales de la API consumen y producen JSON, salvo que se indique lo contrario.

## Autenticación con Apptio opentoken

Para autenticarse, primero debe obtener un apptio-opentoken.

1. Vaya a [Enhanced Access Administration APIs](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=apis-about-enhanced-access-administration-api "(se abre en una pestaña o una ventana nueva)") para recuperar un Apptio opentoken.
2. Una vez que tenga el token, añada las siguientes cabeceras a su solicitud:

| Nombre de la cabecera | Contenido |
| --- | --- |
| tipo de aplicación | "UploaderService" |
| versión de la aplicación | "1.00.0" |
| apptio-opentoken | Un opentoken válido que represente al usuario conectado |
| apptio-entorno-actual | El entorno FrontDoor al que se dirige esta solicitud |

## API REST

Las API admiten las siguientes operaciones:

- carga de una sola pieza
- carga multiparte
- carga de procesamiento
- obtener el estado de procesamiento

## Iniciar una carga de una sola pieza

**Método** : `POST <ULS_URL>/v1/upload?partSize=<long>`

**Tipo de contenido** : multipart/form-data

**Cuerpo** :

Para formar el cuerpo de una sola pieza, es necesario que estén presentes las siguientes piezas:

```
"metadata": ( { "name": "<TABLE_NAME>" } )
"data": ()
```

**Códigos de devolución:**

200 - Éxito

400 - Cuerpo JSON incorrecto

404 - API incorrecta URL

415 - Tipo de soporte no compatible

500 - Error interno de carga (contacte con Soporte)

**Respuesta** :

N/D

## Iniciar una carga multiparte

**Método** : `POST <ULS_URL>/v1/upload/multipart`

**Content-type** : application/json

**Cuerpo** :

```
{
	"name":"<TABLE_NAME>"
}
```

**Códigos de devolución:**

200 - Éxito

400 - Cuerpo JSON incorrecto

404 - API incorrecta URL

500 - Error interno de carga (contacte con Soporte)

**Respuesta (JSON)** :

```
{
	"uploadId":""<UPLOAD_ID>", 
	"multipartId":"<MULTIPART_ID>"
}
```

## Carga de piezas

**Método** : `PUT
<ULS_URL>/v1/upload/multipart/<UPLOAD_ID>/part/<PART_ID>?lastPart=<Bool>&md5=<String>&partSize=<long>`

**Parámetros** :

| Nombre | Tipo | Descripción |
| --- | --- | --- |
| partId | Entero | Un número de secuencia, por ejemplo 1, 2 ó 3 |
| lastPart | Booleano | **cierto** : esta es la última parte. La longitud del flujo de entrada de la última parte puede ser inferior a 5MB. **falso** : La última parte no. La longitud del flujo de entrada que no es la última parte no puede ser inferior a 5MB. |
| md5 | Serie | El base64-encoded 128-bit MD5 digest de los datos de la parte |
| partSize | Entero largo | La longitud del flujo de entrada en bytes. |

**Tipo de contenido** : Dependiendo del tipo del flujo del cuerpo, se admiten los siguientes tipos:

text/plain

application/json

aplicación/zip

aplicación/octet-stream

**Cuerpo** :

El flujo de entrada en el cuerpo.

**Códigos de devolución** :

200 - Éxito

204 - Éxito

400 - Tamaño de pieza no válido (debe estar entre 5MB y 5GB )

404 - API incorrecta URL o ID de carga incorrecto

500 - Error interno de carga (contacte con Soporte)

**Respuesta (JSON)** :

Errores, si los hay.

## Finalizar una carga multiparte

**Método** : `POST
<ULS_URL>/v1/upload/multipart/<UPLOAD_ID>`

**Códigos de devolución** :

200 - Éxito

404 - API incorrecta URL

500 - Error interno de carga (contacte con Soporte)

**Respuesta (JSON** ):

Errores, si los hay.

## Abortar una carga multiparte

**Método** : `DELETE
<ULS_URL>/v1/upload/multipart/<UPLOAD_ID>`

**Códigos de devolución** :

200 - Éxito

404 - API incorrecta URL

500 - Error interno de carga (contacte con Soporte)

**Respuesta (JSON)** :

Errores, si los hay.

## Iniciar el procesamiento final de una carga

**Método** :

```
POST <ULS_URL>/v1/process
```

**Content-type** : application/json

**Cuerpo** :

Los procesos con una sola carga o cargas tienen los mismos metadatos:

```
{
	"metadata": {
		"period": "<Apptio time period e.g. Jan:FY2018>",
		"domain": "<Customer domain e.g. customer.apptio.com>",
		"name": "<File name e.g. file.tsv, file.zip, etc.>",
		"host": "<Apptio host name>",
		"format": "<File format e.g. tsv, csv, etc.>",
		"project": "<Project Name>",
		"source": "<Data source e.g. S3>",
		"category": "<Optional category name>",
		"branch": "<Optional branch name>",
		"overwrite": "<true or false to append>",
		"autoCheckin":"<true of false to check in BIIT>"
	},
	"uploadIds": [
		"<UPLOAD ID>"
	]
}
```

Para cargas múltiples con metadatos diferentes:

```
{
	"metadata": {
		"period": "<Apptio time period e.g. Jan:FY2018>",
		"domain": "<Customer domain e.g. customer.apptio.com>",
		"name": "<File name e.g. file.tsv, file.zip, etc.>",
		"host": "<Apptio host name>",
		"format": "<File format e.g. tsv, csv, etc.>",
		"project": "<Project Name>",
		"source": "<Data source e.g. S3>",
		"category": "<Optional category name>",
		"branch": "<Optional branch name>",
		"overwrite": "<true or false to append>"
		"autoCheckin": "<true of false to check in BIIT>"
	},
	"uploadIds": [
		"<UPLOAD_ID1>",
		"<UPLOAD_ID2>"
	],
	"uploadTargetMapping": {
		"<UPLOAD_ID1>": {
			"period": "<Apptio time period e.g. Jan:FY2018>",
			"domain": "<Customer domain e.g. customer.apptio.com>",
			"name": "<File name e.g. file.tsv, file.zip, etc.>",
			"host": "<Apptio host name>",
			"format": "<File format e.g. tsv, csv, etc.>",
			"project": "<Project Name>",
			"source": "<Data source e.g. S3>",
			"category": "<Optional category name>",
			"branch": "<Optional branch name>",
			"overwrite": "<true or false to append>"g
			"autoCheckin": "<true of false to check in BIIT>"
		},
		"<UPLOAD_ID1>": {
			"period": "<Apptio time period e.g. Jan:FY2018>",
			"domain": "<Customer domain e.g. customer.apptio.com>",
			"name": "<File name e.g. file.tsv, file.zip, etc.>",
			"host": "<Apptio host name>",
			"format": "<File format e.g. tsv, csv, etc.>",
			"project": "<Project Name>",
			"source": "<Data source e.g. S3>",
			"category": "<Optional category name>",
			"branch": "<Optional branch name>",
			"overwrite": "<true or false to append>"
			"autoCheckin": "<true of false to check in BIIT>"
		}
	}
}
```

Nota: Se debe proporcionar host/domain/project/autoCheckin para todos los metadatos dentro y fuera de uploadTargetMapping, y deben ser coherentes, o la API lanzará 400 solicitud errónea.

**Códigos de devolución** :

200 - Éxito

400 - Solicitud incorrecta

404 - API incorrecta URL

500 - Error interno de carga (contacte con Soporte)

**Respuesta (JSON)** :

```
{
	"processId": "<PROCESS_ID>"
}
```

O errores si los hubiera.

## Obtener el estado de una solicitud de tratamiento

Puede ejecutarse en cualquier momento de la fase de carga o procesamiento.

**Método** : `GET <ULS_URL>/v1/status/<PROCESS_ID>`

**Códigos de devolución** :

200 - Éxito

404 - API incorrecta URL

500 - Error interno de carga (contacte con Soporte)

**Respuesta (JSON)** :

```
{
	"statuses": [
		{
			  "processId": "<PROCESS_ID>",
			  ...,
			  "statusMap": {
				   "<status map ID>": {
					    "statusCode": "<Status e.g. NotStarted, Finished, etc.>",
					    "errorCode": “<Error if any>”,
					    "detail": “<Details>”,
					    "tableName": "<Table name>",
					    "lastModified": "<Last modified date>"
				    }
			   }
		}
	]
}
```

O errores si los hubiera.

## Sesión de grupo statusCode

| **statusCode** | **Descripción** |
| --- | --- |
| Nulo | statusCode es null si no es una sesión de grupo (si sólo hay un uploadId en los metadatos del proceso, entonces no es una sesión de grupo) |
| Correcto | Éxito de la sesión de grupo |
| InProcess | Sesión de grupo en curso |
| IncompleteGroupSession | Si falla una carga en trozos para la sesión de grupo, el estado del grupo es IncompleteGroupSession |
| FailedGroupCheckin | Si la llamada de fin de sesión de grupo falla (el fallo se produce durante el registro del grupo), el estado del grupo es FailedGroupCheckin |

## Sesión individual statusCode

| **statusCode** | **Descripción** |
| --- | --- |
| NotStarted | Sesión no iniciada |
| Correcto | Éxito: La sesión se ha realizado correctamente |
| Fallido | Sesión fallida |

## Diferencias con la API de la plataforma heredada

Cuando se utiliza esta llamada a la API para cargar en un proyecto R12 en el que aún no existe la tabla de destino, Apptio crea la tabla e instala los datos en el primer periodo de tiempo, independientemente del periodo de tiempo especificado en la llamada a la API. Esto sólo se aplica a la primera subida a una tabla que aún no existe. Todas las llamadas posteriores respetan la fecha especificada. La razón de este comportamiento es garantizar que las columnas estén presentes en el primer periodo de tiempo. Si desea que no haya datos hasta un periodo de tiempo determinado, puede crear la tabla manualmente o, tras la carga inicial, hacer lo siguiente:

1. Descargue los datos cargados inicialmente a través de la interfaz de usuario Apptio.
2. Cree un archivo que sólo incluya la cabecera.
3. Cargue la cabecera en el primer periodo de tiempo del proyecto.
4. Cargue los datos descargados en el paso 1 en el periodo de tiempo deseado.

Para más detalles sobre esa API, consulte [API URL para cargar una tabla.](../studio/apis/studio_api_url_table.html "♦ Se aplica a: v11.x, v12.0, v12.1, v12.2+")

**Tema principal:** [Integración de API](../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
