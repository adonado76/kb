---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "GetNextPublishTime función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/getnextpublishtime.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetNextPublishTime función

Se aplica a: 12.11.10 y posteriores

Devuelve la hora de ejecución prevista en la que se producirá la siguiente publicación recurrente. Estas fechas y horas se actualizan a nivel de cada tabla de transformación.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

`= GetNextPublishTime(“Table_name”)`

## Argumentos

TableName

Nombre de la transformación creada a partir de la tabla Editable

## Tipo de retorno

Fecha y hora

## Ejemplo

`GetNextPublishTime(“Table_Demo”)`

Resultado : 12 de noviembre de 2024 12:31:00 PM GMT+05:30
