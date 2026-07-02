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
source_path: "studio/formulas-and-functions/functions/average.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función media

Devuelve el valor medio de una columna o métrica especificada.

## Sintaxis

`Average(column)`

## Argumentos

*operador\_rollup*

@, SOURCE, ~, o TARGET. Este argumento es opcional y sólo se utiliza con métricas. Véase [Operadores Rollup](../operators.html "Se aplica a: TBM Studio 12.0 y posteriores").

*columna* : El nombre de la columna o métrica para la que calcular la media. Opcional

## Tipo de retorno

Número

## Ejemplo

`Average(Budget)`:Devuelve el valor medio de la columna 'Presupuesto'.

`Average(Financials:Expense)`: Devuelve el valor medio de la columna 'Gastos' de la tabla 'Finanzas'.

Nota: Puede especificar sólo una columna o una tabla y una columna juntas utilizando un separador de dos puntos. La función ignora los valores nulos y los valores no numéricos al calcular la media.
