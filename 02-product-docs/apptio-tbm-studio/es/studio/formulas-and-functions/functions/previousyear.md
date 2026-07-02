---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "PreviousYear función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/previousyear.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PreviousYear función

Devuelve la suma de una métrica especificada en la tabla actual para el número anterior de periodos de un ejercicio. En un calendario de 12 periodos, serían 12 periodos. En un calendario de 13 periodos, serían 13 periodos.

## Sintaxis

`PreviousYear(metric)`

## Parámetros

*métrica* : Una métrica en la misma tabla.

## Comportamiento

- Devuelve el valor total de la métrica especificada durante el ejercicio anterior.
- El número de periodos sumados viene determinado por la configuración del calendario (por ejemplo, 12 periodos para calendarios mensuales, 13 para calendarios fiscales 4-4-5).
- Los cálculos son relativos al periodo de tiempo actual en contexto.

## Tipo de retorno

Número

## Ejemplo

- `=PreviousYear(Cost)`: Para la fecha actual de agosto de 2012, el siguiente ejemplo devuelve la suma de {Cost} de agosto de 2011 a julio de 2012.
- `Revenue - PreviousYear(Revenue)`: Calcula la diferencia interanual de ingresos restando el total del ejercicio anterior del valor del periodo actual.

Nota: El número de períodos utilizados en el cálculo depende de la configuración del calendario (por ejemplo, 12 ó 13).
