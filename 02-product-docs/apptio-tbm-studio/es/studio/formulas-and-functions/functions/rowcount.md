---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "RowCount función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/rowcount.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# RowCount función

Devuelve un recuento del número total de filas de una tabla especificada. Si no se especifica ninguna tabla, devuelve el número de filas en el contexto de la tabla actual.

## Sintaxis

`RowCount([table])`

## Parámetros

*tabla* : El nombre de la tabla desde la que contar filas. Si se omite, cuenta las filas en el contexto de la tabla actual. No puede especificar explícitamente el nombre de la tabla actual. Opcional (por defecto: tabla actual)

## Comportamiento

- Cuenta todas las filas de la tabla especificada.
- Si no se proporciona ninguna tabla, se utiliza por defecto el contexto de tabla actual.
- El nombre de la tabla actual no puede utilizarse explícitamente como argumento.

## Tipo de retorno

Número

## Ejemplo

En el siguiente ejemplo, si la tabla Servidores tiene 180 filas, la función devuelve 180.: `=RowCount(Servers)`

`RowCount()`: Devuelve el número de filas en el contexto de la tabla actual.
