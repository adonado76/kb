---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "API: Descarga de datos"
breadcrumb: []
source_path: "studio/studio/apis/studio_api_download_data.html"
images:
  - "resources/images/studio_images/api-change_623x294.png"
  - "resources/images/studio_images/studioimages/studio_api_download_1_800x458.png"
  - "resources/images/studio_images/studioimages/studio_api_download_800x380.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API: Descarga de datos

**Se aplica a** : TBM Studio v11.x, v12.0, v12.1, v12.2 y posteriores

Mediante la API, puede descargar tablas sin procesar y también transformar tablas desde la pestaña Datos. Además, puedes descargar los datos de las tablas y gráficos de los informes. Puede descargar los datos en formato Excel (archivo.xls o.xlsx). Para archivos de gran tamaño, puede utilizar el formato de archivo TSV (.TSV).

## Autenticación

Para más información, consulte el enlace comunitario [Autenticación de usuarios mediante API](https://community.ibm.com/community/user/viewdocument/user-authentication-using-apis?CommunityKey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8&tab=librarydocuments "(se abre en una pestaña o una ventana nueva)")

## Obtención de URL de API para tablas

Navegue hasta una tabla en TBM Studio. Seleccione la pestaña **Inicio**, haga clic en **Exportar** en el menú desplegable y, a continuación, seleccione **Mostrar API URL**.

![obtención de URL de API](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_api_download_800x380.png)

Aparece un cuadro de diálogo modal que le permite seleccionar y copiar la dirección URL adecuada:

![obtención de URL de API](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_api_download_1_800x458.png)

## Obtención de URL de API para elementos de información

Haga clic con el botón derecho del ratón en la parte inferior de las tablas, en cualquier lugar de un gráfico o utilice el menú desplegable situado en la parte superior izquierda de los elementos de los informes (si están equipados para ello) y obtendrá un menú contextual en el que podrá seleccionar Mostrar API URL :

![obtención de rizos API para elementos de informe](../../../resources/images/studio_images/studioimages/studio_api_download%202_800x469.png)![obtención de rizos API para la tendencia de los elementos del informe](../../../resources/images/studio_images/studioimages/studio_api_download%203_800x587.png)

Aparece un cuadro de diálogo modal que le permite seleccionar y copiar la dirección URL adecuada:

![diálogo modal](../../../resources/images/studio_images/studioimages/studio_api_download%204_800x533.png)

## Cambio del Delimitador

En algunos casos, puede que desee cambiar el delimitador. Para ello, puede utilizar el argumento "delimiter" especificando un valor de codificación de caracteres hexadecimales (para buscar codificaciones de caracteres, [consulte esta página de Wikipedia](https://en.wikipedia.org/wiki/ASCII#Printable_characters "(se abre en una pestaña o una ventana nueva)") ).

https://HOST/biit/api/v2/domains/DOMAIN/projects/PROJECT\_NAME/tables/TABLE\_NAME/dates/TIME\_PERIOD.tsv?delimiter=ENCODED\_CHARACTER

Por ejemplo, si desea cambiar el delimitador para que sea un carácter de tubo "|", obtendría el formato TSV URL como se muestra anteriormente en este documento, luego especificaría el delimitador como “%7C” que es la codificación hexadecimal para un carácter de tubo similar a éste:

https://customer.apptio.com/biit/api/v2/domains/customer.com/projects/Cost Transparencia/tablas/Pruebas Table/dates/Jan:FY2020.tsv?delimiter=%7C

A veces los datos pueden contener el delimitador que desea utilizar. Por poner un ejemplo, supongamos que se parte de una tabla como la siguiente:

![cambiar delimitador](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/api-change_623x294.png)

Sin embargo, debe utilizar el carácter pipa como delimitador. Observe que en la 3ª fila, los valores incluyen caracteres de tubería. Para utilizar con éxito el carácter pipa debe sustituir los valores de los datos por otra cosa. En el siguiente ejemplo, los caracteres de tubo ( %7C ) se sustituirán por comas ( %2C ):

https://customer.apptio.com/biit/api/v2/domains/customer.com/projects/Cost Transparencia/tablas/Pruebas Table/dates/Jan:FY2020.tsv?delimiter=%7C&delimiterReplacement=%2C

La descarga resultante tendrá este aspecto:

ColumnA|ColumnB

ValueA1|ValueB1

ValueA2|ValueB2

ValueA,3|ValueB,3

## Descarga a través de la API

Consulte cualquiera de los siguientes artículos para obtener más información sobre cómo utilizar la API para ejecutar una descarga:

- [Tutorial de la API: Descarga y carga de la tabla v.12 Costing Standard utilizando la herramienta Postman](studio_tutorial.html)
- [Apptio Scripts de demostración de la API](studio_demo_scripts.html)
