---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función Max"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/max.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función Max

Compara dos expresiones y devuelve el valor mayor.

## Sintaxis

`Max(numeric_expression1, numeric_expression2)`

## Argumentos

*expresión\_numérica* : numeric\_expression1: El primer valor numérico o expresión a comparar. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*expresión\_numérica2* : El segundo valor numérico o expresión a comparar. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Comportamiento

- Evalúa ambas expresiones numéricas y devuelve la mayor de las dos.
- Admite expresiones o funciones anidadas como parámetros de entrada.
- Devuelve el valor exacto de la expresión mayor sin modificar.

## Tipo de retorno

Número

## Ejemplo

El siguiente ejemplo contiene argumentos complejos en una función Max. El primer argumento es 42 veces el valor en Horas. El segundo argumento es el mayor de 3 y 7, que es 7. Así, si Horas es 3, el primer argumento se evalúa a 126, que es mayor que 7, por lo que la función devuelve 126.

`=Max(42*{Hours},Max(3,7))`

`Max(10, 20)`: Devuelve 20 porque es el mayor de los dos números.

`Max({Planned Hours}, {Actual Hours})`: Devuelve el valor mayor entre las columnas {Planned Hours} y {Actual Hours} para cada fila.

Nota:

- Útil para establecer límites superiores o determinar valores máximos entre dos métricas.
- Ambos parámetros deben ser numéricos o resolverse en expresiones numéricas.
- Si desea encontrar el valor máximo de una columna, utilice la función Grande.
