---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función mínima"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/min.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función mínima

Compara dos expresiones numéricas y devuelve el valor menor.

## Sintaxis

`Min(numeric_expression1, numeric_expression2)`

## Parámetros

*expresión\_numérica 1 y 2*

El valor numérico o expresión a comparar. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio. Debe introducir dos, y sólo dos, expresiones numéricas.

## Comportamiento

- Evalúa ambas expresiones numéricas y devuelve la menor de las dos.
- Admite expresiones o funciones anidadas como parámetros de entrada.
- Devuelve el valor exacto de la expresión menor sin modificar.

## Tipo de retorno

Número

## Ejemplo

`=Min(42*Hours,Min(3,7))`: Devuelve el menor de 42 veces el valor en {Hours} o 3 (ya que Min(3, 7) se evalúa a 3).

`Min(10, 20)`: Devuelve 10 porque es el menor de los dos números.

`Min({Planned Hours}, {Actual Hours})`: Devuelve el valor más pequeño entre las columnas {Planned Hours} y {Actual Hours} para cada fila.

Nota:

- Útil para establecer límites inferiores o determinar valores mínimos entre dos métricas.
- Ambos parámetros deben ser numéricos o resolverse en expresiones numéricas.
- Si desea encontrar el valor mínimo de una columna, utilice la función Pequeño.
