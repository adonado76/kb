---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "GetLastPublishTime función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/getlastpublishtime.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetLastPublishTime función

Se aplica a: 12.11.10 y posteriores

Devuelve la hora a la que se ejecutó la publicación recurrente para actualizar los datos de la tabla editable en la tabla de transformación asociada. También muestra la última publicación de los tres métodos: programación periódica, botón de publicación o carga del administrador en Studio. Estas fechas y horas se actualizan a nivel de cada tabla de transformación.

Los datos editables de las tablas se publican de las siguientes formas:

- Publicar desde la superficie de notificación
- Programación periódica
- "Actualizar a este período" en transform

Última publicación se actualiza cuando los datos se publican de cualquiera de las formas anteriores.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

`= GetLastPublishTime(“transform_table_name”)`

## Argumentos

TableName

Nombre de la transformación creada a partir de la tabla Editable

## Tipo de retorno

Fecha y hora

## Ejemplo

`GetLastPublishTime(“Table_Demo”)`

Resultado : 12 de noviembre de 2024 12:31:00 PM GMT+05:30
