---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "RowCount_EditableTable( ) función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/rowcount-editabletable.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# RowCount_EditableTable( ) función

**Se aplica a** : TBM Studio 12.11.3 y posteriores

Devuelve un recuento del número total de filas de una tabla editable.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Métricas calculadas e informes con columnas de métricas
- Columnas de fórmulas en tablas de informes

## Sintaxis

`RowCount([editabletable])`

## Argumentos

*tabla*

Indica qué tabla editable contar. Si no se especifica una tabla editable, devuelve el recuento de la tabla editable actual. No se puede introducir como argumento el nombre de la tabla editable actual.

## Tipo de retorno

Número

## Ejemplo

En el siguiente ejemplo, si la tabla editable Servidores tiene 180 filas, la función devuelve 180.

`=RowCount(Servers)`

**Véase también** : [UniqueCount](uniquecount.htm "(se abre en una pestaña o una ventana nueva)")
