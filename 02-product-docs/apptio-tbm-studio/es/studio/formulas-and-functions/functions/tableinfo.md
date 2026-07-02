---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "TableInfo función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/tableinfo.html"
images:
  - "resources/images/studio_images/studioimages/getgroupbycolumn.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# TableInfo función

**Se aplica a** : TBM Studio 12.9 y posteriores

La función TableInfo añade una o más columnas a la tabla que proporcionan información sobre la última subida a la tabla. TableInfo son especialmente útiles para la validación de datos. No se admiten periodos agregados.

**Dónde utilizarlo**

Esta función se utiliza en cualquier tabla en la que se puedan aplicar fórmulas.

**Sintaxis**

`TableInfo(metric,<tableName>,[timePeriod])`

**Argumentos**

*métrica*

Cada una de las siguientes métricas añade una columna:

- **Última actualización** - Fecha (marca de tiempo) en que se actualizaron por última vez los datos brutos. Esta métrica devuelve el número de segundos transcurridos desde el 1 de enero de 1970, que puede formatearse opcionalmente con la fórmula DateFormat. Por ejemplo:
- =DateFormat(TableInfo("Last Actualizado"), "M/d/a hh:mm:ss a")
- Última actualización: userID de la persona que actualizó los datos por última vez.
- **Fuente** - El nombre del archivo cargado, similar a la columna Fuente de la tabla.Datasets.
- **Tipo** - El tipo de la fuente de datos, similar a la columna Tipo de la tabla.Datasets.
- **Utiliza datos de** - El período de tiempo desde el que se copian los datos sin procesar.
- **Actualizado en este periodo** - Verdadero/falso, indica si el archivo fue cargado en este periodo.
- *tableName-* El nombre de la tabla que ingiere la información recuperada. Por defecto es el nombre de la tabla actual, a menos que se especifique lo contrario.
- *timePeriod* - El periodo actual, si no se especifica lo contrario.
- **Tipo de retorno** - La función admite tanto texto como números.

## Ejemplos

A continuación se muestra un ejemplo de fórmulas de métricas múltiples y las columnas resultantes.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/getgroupbycolumn.png)
