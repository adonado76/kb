---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función SLN"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/sln.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función SLN

**Se aplica a** : TBM Studio 12.0 y posteriores

Devuelve la amortización lineal de un activo durante un año.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Columnas de fórmulas en tablas de informes
- Texto dinámico
- Métricas calculadas e informes con columnas de métricas

## Sintaxis

`SLN(original,salvage,lifespan)`

## Argumentos

*original*

El valor original del activo que se amortiza.

*salvamento*

El valor de salvamento del activo que se amortiza.

*vida útil*

El número de años a amortizar.

## Tipo de retorno

Número

## Ejemplo

El siguiente ejemplo calcula la depreciación lineal a lo largo de 5 años para un activo de $4000 con un valor de salvamento de $800. Esta función devuelve un valor de amortización anual de 640.

`=SLN(4000,800,5)`
