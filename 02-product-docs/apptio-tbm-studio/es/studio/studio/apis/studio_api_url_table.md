---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "API URL para cargar una tabla"
breadcrumb: []
source_path: "studio/studio/apis/studio_api_url_table.html"
images:
  - "resources/images/studio_images/studioimages/studio-upload-table.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API URL para cargar una tabla

♦ Se aplica a: v11.x, v12.0, v12.1, v12.2+

Puede cargar datos en Apptio utilizando la línea de comandos de la API URL o la herramienta ETL (Extract, Transform, Load) Apptio. La siguiente información describe cómo utilizar la API URL. Para obtener información sobre la herramienta ETL, consulte [https://community.apptio.com/docs/DOC-4223](https://community.apptio.com/docs/DOC-4223 "(se abre en una pestaña o una ventana nueva)")[DataLink Scripts de ejemplo de la API](../../../datalink-classic/api-dlc-sample-scripts.html).

## URL

Utilice la siguiente dirección URL para cargar una tabla en Apptio :

```
https://[customerid].apptio.com/biit/api/v1/[domain]/[project]/[table]/[time-period]/[action
        | force]
```

A continuación se describen los parámetros utilizados en URL. Los parámetros marcados con un asterisco (\*) son obligatorios.

| Parámetro | Descripción |
| --- | --- |
| id\_cliente\* | El ID asignado al cliente. |
| dominio | El dominio del cliente ( es decir, customer.com ). |
| proyecto\* | El proyecto dentro del dominio del cliente. |
| mesa\* | El nombre de la tabla en la que se almacenarán los datos. |
| período de tiempo\* | Una designación de tiempo compatible con Apptio (es decir, January:2000 ) o actual para representar el mes:año actual en el calendario gregoriano. |
| acción | El comportamiento a realizar en la tabla con los datos, ya sea Anexar o Sobrescribir. Si utiliza este parámetro, no utilice el parámetro Force parameter.ValuesAppend: añade los datos a los datos actuales set.Overwrite: elimina los datos actuales y los sustituye por los nuevos datos**.NOTA** : Si necesita utilizar los parámetros Action y Force, deberá incluir los parámetros en el cuerpo del POST en lugar de en URL. |
| force | Se utiliza para anular las comprobaciones de validez del conjunto de datos realizadas por la función de importación de la aplicación. Si utiliza este parámetro, no utilice el parámetro Acción. Valores:true: Las comprobaciones de validez serán overridden.false: Las comprobaciones de validez no se anularán. |

## Ejemplos de URL

A continuación se muestran ejemplos de URL con los parámetros incluidos en URL.

| Ejemplo | URL |
| --- | --- |
| El parámetro Force está predeterminado a false | biit/api/v1/[domain ]/[proyecto]/[tabla]/[periodo de tiempo]/sobrescribir |
| El parámetro Force está predeterminado a false | biit/api/v1/[domain ]/[proyecto]/[tabla]/[periodo de tiempo]/aplicar |
| El parámetro de acción por defecto es sobrescribir | biit/api/v1/[domain ]/[proyecto]/[tabla]/[periodo de tiempo]/fuerza |
| Forzar validación pasada y añadir | --form "force=true" biit/api/v1/[domain ]/[proyecto]/[tabla]/[periodo]/append |

## Uso de campos de formulario en el cuerpo del POST para especificar parámetros

En lugar de incluir los parámetros overwrite/append/force en URL, puede especificarlos en campos de formulario en el cuerpo del POST. Los parámetros se muestran a continuación.

| Parámetro | Valores |
| --- | --- |
| force | "verdadero" o "falso" |
| acción | "añadir" o "sobrescribir" |

## Método

Para cargar datos en Apptio, utilice el método http:POST.

## Formatos de archivo compatibles

Los formatos de archivo compatibles son:

- CSV
- TSV
- CSV.GZ
- TSV.GZ

Nota: El único tipo mime admitido es multipart/form-data.

## Códigos de devolución

Hay tres posibles códigos de retorno:

- 200 OK
- 400 Cadena API incorrecta
- 500 Error interno de carga

## Respuestas

Las respuestas se devuelven en JavaScript Object Notation (JSON). Las respuestas correctas incluirán el nombre del archivo, su longitud y la suma de comprobación MD5 basada en los datos transmitidos a Apptio. A continuación se muestra un ejemplo de respuesta.

```
{
"md5":"3727119d89edcdd71377e39e18f3a5e1\",
"length":13,
"fileName":"testFile.csv"
}
```

Las respuestas de error devuelven el mensaje que describe el error. A continuación se muestra un ejemplo en el que se facilitó una fecha incorrecta.

```
{

"message":"Poorly formatted date string: 'SOMEDATE:2010'. Ought to be of the form 'granularity':'year'."

}
```

## Cargas reflejadas en la pestaña Datos>Vista general

Cuando carga datos en Apptio a través de la API, **los Datos API** aparecen en el campo **Fuente de** la pestaña **Datos>Vista general**, como se muestra a continuación.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio-upload-table.png)

## Diferencias con la API del servicio de carga (API ULS)

Cuando se utiliza esta llamada a la API para cargar en un proyecto R12 en el que la tabla de destino aún no existe, Apptio crea la tabla en el primer periodo de tiempo del proyecto, pero los datos aparecen en el periodo especificado en la llamada a la API. Esto difiere de la API ULS.

Para obtener más información sobre la API ULS, consulte [Uploader Service API](../../admin/uploader-service-api.htm "(se abre en una pestaña o una ventana nueva)")
