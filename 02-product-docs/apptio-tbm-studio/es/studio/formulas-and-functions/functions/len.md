---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función Len"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/len.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función Len

Devuelve el número de caracteres de una cadena dada, incluidos los espacios.

## Sintaxis

`Len(string_expression)`

## Parámetros

*expresión\_cadena* : El valor a evaluar. Puede ser una cadena literal, una referencia de columna o una expresión concatenada. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Comportamiento

- Evalúa la expresión dada y devuelve el número total de caracteres del resultado.
- Cuenta todos los caracteres, incluidos los espacios en blanco y los signos de puntuación.

## Tipo de retorno

Número

## Ejemplos

- En el siguiente ejemplo, si la columna Descripción del ticket de la fila actual contiene la cadena Hardware, la función devuelve 8, que es el número de caracteres de la cadena Hardware.`=Len({Ticket Description})`
- En el siguiente ejemplo, la cadena Soporte se añade a la expresión. Así, si la columna Descripción del ticket de la fila actual contiene la cadena Hardware, la función devuelve 15, que es el número de caracteres de la cadena Hardware (8) más el número de caracteres de la cadena Soporte (7).`=Len("Support"+Ticket Description)`
