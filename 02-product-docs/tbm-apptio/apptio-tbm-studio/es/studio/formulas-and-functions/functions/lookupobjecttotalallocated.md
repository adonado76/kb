---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "LookupObjectTotalAllocated función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/lookupobjecttotalallocated.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupObjectTotalAllocated función

**Se aplica a** : TBM Studio 12.0 y posteriores

Busca el valor unitario asignado desde un objeto origen a uno o más objetos destino en un modelo. La función sólo funciona desde el contexto de un objeto.

Esta función se centra en el objeto de origen, no en los objetos de destino. La función extrae el valor de la columna **Asignados** de la tabla **.No asignados**.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Métricas calculadas e informes con columnas de métricas
- Columnas de fórmulas en tablas de informes
- Texto dinámico
- Fórmulas de origen de la asignación

## Sintaxis

`LookupObjectTotalAllocated(metric)`

## Argumentos

*métrico*

El valor a recuperar. Por lo general, se trata de una métrica modelo, como el coste.

## Tipo de retorno

Serie

Consulte también:

- [Búsqueda de IP](iplookup.htm "(se abre en una pestaña o una ventana nueva)")
- [Lookup y Lookup\_Wild](lookupandlookup_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupEx](lookupexandlookupex_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupFromPath](lookupfrompath.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupMetric](lookupmetric.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(se abre en una pestaña o una ventana nueva)")
