---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "LookupObjectUnitValue función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/lookupobjectunitvalue.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug558.png"
  - "resources/images/studio_images/studioimages/studio/aug559.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupObjectUnitValue función

**Se aplica a** : TBM Studio 12.0 y posteriores

Encuentra el valor de una unidad para un objeto. Si se suministra el parámetro controlador, busca el valor total del controlador especificado.

La función LookupObjectUnitValue se utiliza a menudo para ponderar un inductor de coste frente al coste calculado en otra parte de un modelo. Tenga cuidado de no crear referencias circulares en sus cálculos.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Métricas calculadas e informes con columnas de métricas
- Columnas de fórmulas en tablas de informes
- Texto dinámico
- Fórmulas de origen de la asignación

## Sintaxis

*LookupObjectUnitValue(object,metric,targetCol,lookupCol[,driver])*

## Argumentos

*objeto*

El nombre del objeto que proporcionará un valor de coste.

*métrico*

El nombre de la métrica a buscar. A menudo se trata de la misma métrica en la que se utiliza la función.

*targetCol*

El nombre de la columna de la tabla de origen que se comparará con lookupCol.

*lookupCol*

Nombre de la columna de la tabla de correspondencia que proporcionará el valor de búsqueda.

*controlador*

Se trata de un parámetro opcional. Si especifica un controlador, limita la función al valor aportado por el controlador especificado. Por ejemplo, si los controladores A y B aportan ambos valor a la unidad C, entonces se podría limitar la función LookupObjectUnitValue al valor suministrado por el controlador A o el controlador B.

## Tipo de retorno

Serie

## **Ejemplo 1**

Suponga que tiene el siguiente objeto y tabla en un modelo llamado Estadísticas:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug559.png)

Como se muestra arriba, el objeto Actividad tiene un identificador de unidad de Matching.Activity y un controlador con la fórmula de =1. La fórmula produce los valores de la columna Estadísticas de la tabla anterior. La función LookupObjectUnitValue utilizará los valores de la columna Estadísticas para realizar los cálculos.

Ha colocado la siguiente tabla Objetivo en un informe:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug558.png)

Desea determinar el número de actividades asociadas a cada servidor y mostrar el resultado en la columna **Número de actividades** de la tabla Destino.

En la columna **Número de actividades** se introduce la siguiente fórmula:

`=LookupObjectUnitValue(Activity,Statistics,Server,Matching.Server)`

donde:

- **Actividad** es el nombre del objeto.
- **Estadísticas** es el nombre de la métrica del modelo.
- **Servidor** es el nombre de la columna en la tabla Destino.
- **Matching.Server** es el nombre de la columna de búsqueda en la tabla de unidades de objeto Actividad.

## Ejemplo 2

Suponga que tiene el modelo de costes que se muestra en la siguiente imagen:

![](../../../resources/images/studio_images/studioimages/visio%20diagrams/lookupobjectunitvalue.png)

En el modelo, los valores del objeto Servidores se asignan al objeto OS Direct como se muestra. El resultado es que el 80% de los costes directos se asignan a servidores Windows y el 20% a servidores Linux. El objeto Compartido representa un único cubo de 600 dólares. Desea asignar los 600 dólares al objeto OS Indirecto en la misma proporción que los costes del objeto OS Directo.

Para asignar los costes, se crean dos asignaciones separadas del objeto Compartido al objeto Indirecto del SO: una para Windows y otra para Linux. Para ambas asignaciones, se utiliza la siguiente fórmula:

=SOURCE\*LookupObjectUnitValue(OS Directo,Coste,OS Indirect.OS,OS Direct.OS)/LookupObjectTotalValue(OS Directo,Coste)

En la fórmula, los 600 $ (FUENTE) se multiplican por la relación entre LookupObjectUnitValue y LookupObjectTotalValue.

Para destinar cada asignación al sistema operativo correcto, seleccione la opción **Algunos** en el cuadro de diálogo **Propiedades** y filtre por Windows o Linux.

**Consulte también:**

- [Búsqueda de IP](iplookup.htm "(se abre en una pestaña o una ventana nueva)")
- [Lookup y Lookup\_Wild](lookupandlookup_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupEx](lookupexandlookupex_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupFromPath](lookupfrompath.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupMetric](lookupmetric.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(se abre en una pestaña o una ventana nueva)")
