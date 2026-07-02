---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "SmallIf función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/smallif.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SmallIf función

Devuelve el valor más pequeño de un grupo basado en una categoría especificada y criterios opcionales.

## Sintaxis

`SmallIf(category_column, value_column, [criteria])`

## Argumentos

*columna\_categoria* : La columna utilizada para agrupar los datos. Obligatorio

*columna\_valores* : La columna que contiene los valores a evaluar para el valor mínimo dentro de cada categoría. Obligatorio

*criterios* : Opcional. Un nombre de columna, valor de texto o valor numérico utilizado para filtrar la categoría. Si no se especifica, se utiliza el valor de category\_column de la fila actual. Opcional (por defecto: valor de la fila actual en category\_column)

## Comportamiento

- Agrupa las filas por la columna categoría\_especificada.
- Filtra las filas utilizando los criterios proporcionados (si los hay).
- Devuelve el valor más pequeño de la columna\_valor que coincide con los criterios del grupo.

## Tipo de retorno

Número

## Ejemplo 1: SmallIf con un criterio especificado

| Elemento | Categoría | Comparar categorías | Precio medio | SmallIf |
| --- | --- | --- | --- | --- |
| A | Gato ABC | Gato DEF | 10 | 6 |
| D | Gato DEF | Gato ABC | 6 | 10 |
| E | Gato DEF | Gato ABC | 7 | 10 |
| F | Gato DEF | Gato ABC | 8 | 10 |

`=SmallIf(Category, Average Price, Compare Category)`

## Ejemplo 2: SmallIfwithout un criterio especificado

| Elemento | Categoría | Precio medio | SmallIf |
| --- | --- | --- | --- |
| A | Gato ABC | 10 | 10 |
| D | Gato DEF | 6 | 6 |
| E | Gato DEF | 7 | 6 |
| F | Gato DEF | 8 | 6 |

`=SmallIf(Category, Average Price)`

`SmallIf(Region, Weight, Weight)` devuelve el peso más pequeño de cada región cuando la región coincide con el valor de la fila actual.

`SmallIf(Department, Budget, "Finance")` : Devuelve el valor de Presupuesto más pequeño para las filas del departamento 'Finanzas'.

`SmallIf(Category, Amount)` : Devuelve el menor Importe para la Categoría de cada fila.
