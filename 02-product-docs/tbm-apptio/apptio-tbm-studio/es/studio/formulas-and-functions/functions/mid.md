---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función media"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/mid.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función media

Devuelve un número especificado de caracteres de una cadena, comenzando en una posición dada desde la izquierda.

## Sintaxis

Mid(cadena,inicio,recuento)

## Parámetros

- *cadena* : La cadena de texto de la que se extraerán los caracteres. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio
- *inicio* : Un entero que representa la posición del primer carácter a devolver, empezando por el carácter situado más a la izquierda (índice basado en 1). Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio
- *count* : Un entero que representa el número de caracteres a devolver. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Comportamiento

- Extrae una subcadena del texto de entrada basándose en la posición de inicio y la longitud proporcionadas.
- La posición está basada en 1, lo que significa que Mid("abc", 1, 1) devuelve "a".
- Si count supera el número de caracteres disponibles desde la posición inicial, devuelve los caracteres hasta el final de la cadena.

## Tipo de retorno

Serie

## Ejemplos

| Ejemplo de función | Valor de retorno |
| --- | --- |
| =Mid("123456", 2, 3) | 234 |
| =Mid("123456", 1, 2) | 6 |
| =Mid("123456", 4, 1) | 4 |
| =Mid("Me gusta la tarta.", 3, 4) | like - comienza en la posición 3 y devuelve 4 caracteres, incluidos los espacios en blanco. |
