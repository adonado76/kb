---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "PreviousMonth función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/previousmonth.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PreviousMonth función

Devuelve el valor de una métrica especificada del mes anterior dentro de la misma tabla. Útil para comparar los valores actuales con los del mes anterior.

## Sintaxis

`PreviousMonth(metric)`

## Parámetros

*métrica* : Una métrica en la misma tabla. La función devuelve el valor de esta métrica para el mes anterior.

## Tipo de retorno

Número

## Ejemplo

- Para una fecha actual de agosto de 2012, el siguiente ejemplo devuelve el valor de Coste de julio de 2012. `PreviousMonth(Cost)`
- Calcula la variación intermensual del coste. `Cost -
  PreviousMonth(Cost)`

Nota: Esta función opera en el contexto de la tabla actual y no hace referencia a tablas externas. Si no hay datos para el mes anterior, la función devolverá null.
