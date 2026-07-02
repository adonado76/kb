---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función grande"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/large.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función grande

Devuelve el mayor valor de una columna especificada.

## Sintaxis

`Large([rollup_operator]column)`

## Parámetros

*operador\_rollup*

@, SOURCE, ~, o TARGET. Este argumento es opcional y sólo se utiliza con métricas. Véase [Operadores Rollup](../operators.html "Se aplica a: TBM Studio 12.0 y posteriores").

*columna* : La columna donde buscar el valor mayor. Puede especificar un prefijo de tabla utilizando TableName:ColumnName. Obligatorio

## Comportamiento

Analiza la columna especificada y devuelve el valor mayor (máximo).

## Tipo de retorno

Numérico

## Ejemplo

*Grande(Presupuesto)* : Devuelve el mayor valor de la columna 'Presupuesto'.

*Grande(Finanzas:Coste)* : Devuelve el mayor valor de la columna 'Coste' de la tabla 'Finanzas'.
