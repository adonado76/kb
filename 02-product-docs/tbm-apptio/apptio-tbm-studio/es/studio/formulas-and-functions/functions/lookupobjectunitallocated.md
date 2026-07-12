---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "LookupObjectUnitAllocated función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/lookupobjectunitallocated.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupObjectUnitAllocated función

**Se aplica a** : TBM Studio 12.0 y posteriores

Busca el valor asignado entre dos objetos para una métrica determinada unidad por unidad.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Informes con columnas métricas modeladas
- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

```
=LookupObjectUnitAllocated(sourceObject,destObject,metric,
columnInLocalTable,columnInSourceObjectTable)
```

## Argumentos

*sourceObject*

El objeto que proporciona el valor.

*destObject*

El objeto que recibe el valor.

*métrica*

El nombre de la métrica a buscar.

*columnInLocalTable*

El nombre de la columna de la tabla de destino que identifica las unidades.

*columnInSourceObjectTable*

La columna de la tabla de origen que identifica las unidades.

## Tipo de retorno

Serie

**Notas** :

La aplicación Apptio Billing utiliza esta función junto con la función LookupObjectUnitValue para determinar la cantidad total de un servicio que se está consumiendo dentro de un modelo de estilo de precios.

¡Si utiliza esta función con!¡NEWCOLUMN mientras edita una ruta de datos, generalmente tendrá que especificar la palabra clave [ canSum ] en el campo!NEWCOLUMN porque no puede recalcular con parámetros de agrupación diferentes.

## Ejemplo

El siguiente ejemplo de ruta de datos determina el coste asignado del objeto Soporte al objeto Servicios. El valor se toma de las unidades de la columna Support.ID y se asigna a las unidades de la columna Services.ID.

```
!NEWCOLUMN[alloc=LookupObjectUnitAllocated
(Support,Services,Cost,ID,ID)][canSum]
```

Consulte también:

- [Búsqueda de IP](iplookup.htm "(se abre en una pestaña o una ventana nueva)")
- [Lookup y Lookup\_Wild](lookupandlookup_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupEx](lookupexandlookupex_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupFromPath](lookupfrompath.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupMetric](lookupmetric.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(se abre en una pestaña o una ventana nueva)")
