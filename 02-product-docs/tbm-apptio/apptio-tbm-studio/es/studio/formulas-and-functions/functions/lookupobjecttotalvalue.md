---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "LookupObjectTotalValue función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/lookupobjecttotalvalue.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupObjectTotalValue función

**Se aplica a** : TBM Studio 12.0 y posteriores

Calcula el valor total de un objeto. Si no se utiliza el parámetro métrica, la función utiliza el modelo actual. Si se suministra el parámetro controlador, busca el valor total del controlador especificado.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Métricas calculadas e informes con columnas de métricas
- Métricas de modelo
- Columnas de fórmulas en tablas de informes
- Texto dinámico
- Fórmulas de origen de la asignación

## Sintaxis

*LookupObjectTotalValue(object [,métrica [, conductor]])*

## Argumentos

*objeto*

El nombre del objeto de destino. El objeto no debe estar por encima del nivel actual en la jerarquía del modelo donde se está utilizando la función.

*métrico*

Si se especifica, devuelve el valor de la métrica tal y como se aplica al objeto.

Si no se especifica, devuelve el valor del objeto en el modelo actual.

*controlador*

Si se especifica, devuelve el valor del controlador. El controlador debe ser un controlador asociado al objeto.

## Tipo de retorno

Serie

## Ejemplos

Suponga que tiene el modelo de costes que se muestra en la siguiente imagen. El objeto C tiene dos controladores: Objeto A y Objeto B.

![Ejemplos](../../../resources/images/studio_images/studioimages/visio%20diagrams/lookupobjecttotalvalue.png)

Desea poder utilizar el valor del Objeto A en otra parte del modelo. Se utilizaría la siguiente función:

```
=LookupObjectTotalValue(Object
      A,Cost)
```

La función devolvería el valor $7M.

Ahora, supongamos que quieres encontrar el valor del Objeto C que es aportado por el conductor del Objeto A. Utilizarías la siguiente función:

```
=LookupObjectTotalValue(Object C,Cost,Object
      A)
```

En la función, Objeto A es el nombre del controlador procedente del Objeto A.

Consulte también:

- [Búsqueda de IP](iplookup.htm "(se abre en una pestaña o una ventana nueva)")
- [Lookup y Lookup\_Wild](lookupandlookup_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupEx](lookupexandlookupex_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupFromPath](lookupfrompath.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupMetric](lookupmetric.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(se abre en una pestaña o una ventana nueva)")
