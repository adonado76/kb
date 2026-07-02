---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "GetLastFilterColumn función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/getlastfiltercolumn.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetLastFilterColumn función

**Se aplica a** : TBM Studio 12.0 y posteriores

Devuelve el nombre de la última columna a la que se aplicó un filtro.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

`GetLastFilterColumn()`

## Tipo de retorno

Texto

## Ejemplo

Lo siguiente devolvería el valor "Unidad de Negocio"

`!Filter[Business Unit=Sales]`

**Véase también** : [GetLastFilterValue](getlastfiltervalue.htm "(se abre en una pestaña o una ventana nueva)")
