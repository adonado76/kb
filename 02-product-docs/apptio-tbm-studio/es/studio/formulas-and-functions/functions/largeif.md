---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "LargeIf función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/largeif.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LargeIf función

Devuelve el valor más grande de un grupo basándose en una categoría especificada y criterios opcionales.

## Sintaxis

`LargeIf(category_column, value_column, criteria)`

## Parámetros

*columna\_categoria* : La columna utilizada para agrupar los datos. Obligatorio

*columna\_valores* : La columna que contiene los valores a evaluar para el valor máximo dentro de cada categoría. Obligatorio

*criterios* : Opcional. Un nombre de columna, valor de texto o valor numérico utilizado para filtrar la categoría. Si no se especifica, se utiliza el valor de category\_column de la fila actual. Opcional (por defecto: valor de la fila actual en category\_column)

## Comportamiento

- Agrupa las filas por la columna categoría\_especificada.
- Filtra las filas utilizando los criterios proporcionados (si los hay).
- Devuelve el mayor valor de la columna\_valor que coincide con los criterios del grupo.

## Tipo de retorno

Número

## Ejemplos

**Ejemplo 1** : LargeIf con un criterio especificado:

| Elemento | Categoría | Comparar categorías | Precio medio | LargeIf |
| --- | --- | --- | --- | --- |
| A | Gato ABC | Gato DEF | 10 | 8 |
| D | Gato DEF | Gato ABC | 6 | 10 |
| E | Gato DEF | Gato ABC | 7 | 10 |
| F | Gato DEF | Gato ABC | 8 | 10 |

`=LargeIf(Category, Average Price, Compare Category)`

**Ejemplo 2** : LargeIf sin un criterio especificado:

| Elemento | Categoría | Precio medio | LargeIf |
| --- | --- | --- | --- |
| A | Gato ABC | 10 | 10 |
| D | Gato DEF | 6 | 8 |
| E | Gato DEF | 7 | 8 |
| F | Gato DEF | 8 | 8 |

`=LargeIf(Category, Average Price)`: Devuelve el mayor Importe para la Categoría de cada fila.

`LargeIf(Region, Weight, Weight)`: Devuelve el mayor Peso de cada Región cuando la Región coincide con el valor de la fila actual.

`LargeIf(Department, Budget, "Finance")`: Devuelve el mayor valor de Presupuesto para las filas del departamento 'Finanzas'.
