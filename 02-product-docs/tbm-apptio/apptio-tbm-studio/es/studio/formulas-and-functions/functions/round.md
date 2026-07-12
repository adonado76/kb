---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función redonda"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/round.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función redonda

Redondea un número real a un número especificado de decimales utilizando el algoritmo 'round-half-up'. Esto significa que los valores que terminan en.5 se redondean a partir de cero.

## Sintaxis

`Round(numeric_expression, digits)`

## Argumentos

*expresión\_numérica* : Expresión que evalúa el número a redondear. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*dígitos* : Expresión entera que especifica el número de decimales a redondear. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Comportamiento

- Redondea el valor de entrada al número especificado de decimales.
- Utiliza el algoritmo "round-half-up": los valores que terminan en.5 se redondean a partir de cero.
- Si los dígitos son cero, el valor se redondea al número entero más próximo.

## Tipo de retorno

Número

**Ejemplos básicos** :

| Ejemplo de función | Valor de retorno |
| --- | --- |
| =Round( 1.23,1) | 1.2 |
| =Round( 1.23,0) | 1 |
| =Round( 1.57,1) | 1.6 |
| =Round( 1.452,0) | 1 |
| Ronda( -23.5, 0) | -23 ya que el redondeo se aleja de cero para los valores de 0,5. |

## Incorporar una función

Suponga que tiene el siguiente conjunto de datos:

| A | B |
| --- | --- |
| 3 | 2 |
| 6 | 5 |
| 5 | 7 |
| 4 | 9 |

Desea dividir la columna A entre la columna B y redondear a dos decimales, colocando el resultado en la columna C. Introduzca lo siguiente en el campo Valor de la columna C:

`=Round((A/B),2)`

El resultado es la siguiente tabla:

| A | B | C |
| --- | --- | --- |
| 3 | 2 | 1.5 |
| 6 | 5 | 0.55 |
| 5 | 7 | 0.71 |
| 4 | 9 | 0.44 |
