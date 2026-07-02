---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "ObjectName función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/objectname.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ObjectName función

**Se aplica a** : TBM Studio 12.0 y posteriores

La función devuelve el nombre del objeto que conduce el informe actual.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Columnas de fórmulas en tablas de informes
- Texto dinámico

Esta función se utiliza sobre todo en los cuadros de texto HTML de los informes como parte del texto dinámico.

## Sintaxis

`ObjectName()`

## Argumentos

Ninguna

## Tipo de retorno

Serie

## Ejemplos

El siguiente texto dinámico en un cuadro de texto HTML en un informe devuelve el nombre del objeto de informe actual.

`<%=ObjectName()%>`
