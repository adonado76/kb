---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "LookupMetric función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/lookupmetric.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupMetric función

**Se aplica a** : TBM Studio 12.0 y posteriores

Busca una columna de otra métrica utilizando la misma ruta de datos. Toma la ruta actual, sustituye una nueva métrica y vuelve a ejecutar el modelo antes de buscar un valor en una columna especificada.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Métricas calculadas e informes con columnas de métricas
- Columnas de fórmulas en tablas de informes

Se utiliza para buscar una métrica en la ruta de datos actual que normalmente no está disponible.

## Sintaxis

`LookupMetric(metric,column)`

## Argumentos

*métrico*

El nombre de la métrica a utilizar.

*columna*

La columna de la nueva tabla a consultar.

## Tipo de retorno

Métrica

## Ejemplo

Este ejemplo da como resultado una tabla AssignmentRatios que tiene una columna adicional denominada {NewCol}.

```
demo.apptio.com:BanksDemo/
CostModels/
Default/
Cost/
1199145600000/
Services/
.Drivers/
Servers/
!FILTER[ServerCMDB.Server Product="ASP.NET"]/
!GROUPBY[ServerCMDB.Server Product]/
.AssignmentRatios/
!NEWCOLUMN[{NewCol}=LookupMetric(Chargeback,{ASP.NET})]/
```

El valor de la columna {NewCol} lo proporciona la función LookupMetric haciendo referencia a la columna {ASP.NET} de la siguiente tabla:

```
demo.apptio.com:BanksDemo/
CostModels/
Default/
```

`Chargeback`

```
/
1199145600000/
Services/
.Drivers/
Servers/
!FILTER[ServerCMDB.Server Product="ASP.NET"]/!GROUPBY[ServerCMDB.Server
              Product]/
.AssignmentRatios/
```

Consulte también:

- [Búsqueda de IP](iplookup.htm "(se abre en una pestaña o una ventana nueva)")
- [Lookup y Lookup\_Wild](lookupandlookup_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupEx](lookupexandlookupex_wild.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupFromPath](lookupfrompath.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(se abre en una pestaña o una ventana nueva)")
