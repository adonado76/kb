---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "LookupContains función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/lookupcontains.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupContains función

**Se aplica a** : TBM Studio 12.0 y posteriores

Realiza una búsqueda de coincidencias parciales en varias columnas. El uso principal es la limpieza de datos mediante búsquedas de uno a muchos (una sola fuente, varias columnas de destino) y búsquedas de muchos a uno (varias fuentes, una sola columna de destino).

Para más información sobre esta función, consulte el blog [R12 Quick Guide: Lookup Contains](https://community.apptio.com/people/dmahan@apptio.com/blog/2017/02/04/r12-quick-guide-lookupcontains "(se abre en una pestaña o una ventana nueva)") por Douglas Mahan.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Columnas de fórmulas en tablas de informes (aunque no se recomienda por problemas de rendimiento)
- Texto dinámico

## Sintaxis

Consultas de uno a muchos:

`LookupContains(sourceColumn,TargetTable,[targetCol1,TargetCol2,...TargetColN],TargetValueColumnName,caseSensitivity={true/false},outputVariousOnMultipleMatches={true/false}))`

La función devolverá el valor de TargetTable:TargetValueColumnName para la fila cuando se cumplan las siguientes condiciones:

1. La fila tiene una coincidencia: el valor de al menos una de las columnas de destino está "contenido" en el valor de la columna de origen en esa fila (distingue entre mayúsculas y minúsculas y contiene determinado por el último indicador opcional).
2. La fila tiene el máximo número de coincidencias posibles.
3. La fila es única (sólo existe una fila con el número máximo de columnas coincidentes).

Si sólo las dos primeras condiciones son verdaderas, y outputVariousOnMultipleMatches es verdadero, la función devuelve " {Various} ", de lo contrario la función devuelve null.

Búsquedas múltiples:

`LookupContains([sourceColumn1,..sourceColumnN],TargetTable,targetCol,TargetValueColumnName,caseSensitivity={true/false},outputVariousOnMultipleMatches={true/false})`

La función devolverá el valor de TargetTable:TargetValueColumnName para la fila cuando se cumplan las siguientes condiciones:

1. La fila tiene una coincidencia: el valor de al menos una de las columnas de origen está "contenido" en el valor de la columna de destino (distingue entre mayúsculas y minúsculas y contiene determinado por el último indicador opcional).
2. La fila tiene el máximo número de coincidencias posibles.
3. La fila es única (sólo existe una fila con el número máximo de columnas coincidentes).

Si sólo las dos primeras condiciones son verdaderas, y outputVariousOnMultipleMatches es verdadero, la función devuelve " {Various} ", de lo contrario la función devuelve null.

Búsquedas uno a uno:

`LookupContains(sourceColumn,TargetTable,targetCol,TargetValueColumnName,caseSensitivity={true/false},outputVariousOnMultipleMatches={true/false},oneToOneBidirectional={true/false},oneToOneSourceToTarget={true/false})`

Análogo a los casos anteriores, con una bandera opcional para especificar si la coincidencia requiere contención en ambas direcciones ( oneToOneBidirectional ), o si la coincidencia requiere contención sólo desde el origen al destino ( oneToOneSourceToTarget ).

## Argumentos

sourceColumn

La columna de la tabla actual que contiene el valor a buscar. Este valor puede ser el nombre de una columna de tipo etiqueta. La búsqueda no admite valores numéricos en la columna de origen.

TargetTable

El nombre de la tabla que contiene los valores de retorno. Debe ser una constante y no puede hacer referencia a otras columnas o fórmulas.

targetCol

La(s) columna(s) de la tabla de destino en las que buscar una coincidencia.

TargetValueColumnName

La columna de la tabla de destino que proporciona el valor de retorno.

Si coloca un signo igual (=) delante del nombre de la columna, la función comprobará el valor de la columna en la tabla de origen. El valor que encuentre se utilizará como nombre de la columna que se utilizará en la tabla de destino. Esto permite que la columna de sustitución sea dinámica en cada fila.

caseSensitivity={true/false}

El valor puede ser verdadero o falso.

outputVariousOnMultipleMatches={true/false}

true: Si hay más de una coincidencia, la función devuelve " {Various}."

falso: Si hay más de una coincidencia, la función devuelve null. [¿Es esto correcto, o devuelve la primera o la última coincidencia?]

oneToOneBidirectional={true/false}

true: El partido requiere contención en ambas direcciones.

falso: La coincidencia requiere contención en una sola dirección.

oneToOneSourceToTarget={true/false}

true: La coincidencia requiere la contención de un único origen a un único destino.

falso: La coincidencia puede tener contención de más de un origen a más de un destino.

## Tipo de retorno

Tipo de columna de consulta.

Consulte también:

- [Búsqueda de IP](iplookup.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupEx](lookupexandlookupex_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupFromPath](lookupfrompath.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupMetric](lookupmetric.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(se abre en una pestaña o una ventana nueva)")
