---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Pequeña función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/small.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu014.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Pequeña función

Devuelve el valor más pequeño de una columna especificada.

## Sintaxis

`Small([rollup_operator]column)`

## Parámetros

*operador\_rollup*

@, SOURCE, ~, o TARGET. Este argumento es opcional y sólo se utiliza con métricas. Véase [Operadores Rollup](../operators.html "Se aplica a: TBM Studio 12.0 y posteriores").

*columna* : La columna donde buscar el valor más pequeño. Puede especificar un prefijo de tabla utilizando TableName:ColumnName. Obligatorio

## Comportamiento

Analiza la columna especificada y devuelve el valor más pequeño (mínimo).

## Tipo de retorno

Número

## Ejemplos

![imagen de función pequeña](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu014.png)

`=Small(@Desktop)`

`=Small(Desktop)`

`Small(Budget)`: Devuelve el valor más pequeño de la columna 'Presupuesto'.

`Small(Financials:Cost)`: Devuelve el valor más pequeño de la columna 'Coste' de la tabla 'Finanzas'.
