---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función Trunc"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/trunc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función Trunc

Trunca un número real eliminando su parte fraccionaria.

## Sintaxis

`Trunc(value)`

## Parámetros

*valor* : El valor numérico a truncar. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Tipo de retorno

Número

## Ejemplos

| Ejemplo de función | Valor de retorno |
| --- | --- |
| =Trunc( 1.23 ) | 1 |
| =Trunc( 1.985 ) | 1 |
| Trunc( -2.75 ) | -2 truncando hacia cero. |
| Trunc( {Usage Hours} ) | Trunca los valores de la columna {Usage Hours} a su parte entera. |

Nota: A diferencia de las funciones de redondeo, Trunc simplemente corta la parte decimal en lugar de ajustar el número hacia arriba o hacia abajo. Útil para cálculos en los que es necesario aplicar valores enteros sin redondear.
