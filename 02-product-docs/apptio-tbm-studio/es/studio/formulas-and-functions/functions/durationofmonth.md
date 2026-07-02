---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "DurationOfMonth función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/durationofmonth.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DurationOfMonth función

La función DurationOfMonth devuelve el número de días, horas, minutos, segundos o milisegundos de un mes para un año concreto. Tiene en cuenta los años bisiestos.

## Sintaxis

```
DurationOfMonth (time_unit [, month [, year]])
```

## Tipo de retorno

Número

## Parámetros

- *unidad\_tiempo* : Especifica la unidad de tiempo a devolver. Valores admitidos: 'd' para días, 'h' para horas, 'm' para minutos, 's' para segundos, 'S' para milisegundos. Obligatorio
- *mes* : Opcional. Expresión que evalúa el mes (1-12). Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Opcional (por defecto: mes actual)
- *año* : Opcional. Expresión que evalúa el año. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Opcional (por defecto: año en curso)

## Ejemplos

- Devuelve 29 porque febrero de 2024 tiene 29 días (año bisiesto):`=DurationOfMonth("d", 2,
  2024)`
- Devuelve el número de horas del mes actual:`=DurationOfMonth("h")`

Nota: Unidades de tiempo admitidas: 'd' (día), 'h' (hora), 'm' (minuto), 's' (segundo), 'S' (milisegundo). Si se omiten el mes o el año, se utiliza la fecha actual por defecto.
