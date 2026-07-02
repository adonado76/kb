---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de depuración"
breadcrumb: []
source_path: "studio/apptioscript/debug_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de depuración

Utilice Debug() para mostrar un cuadro de diálogo que contenga texto o datos en un lugar específico del script.

Esta función puede adjuntarse a un botón o a la página onCellValueChange de una tabla editable.

## Sintaxis

`Debug(expression)`

## expresión

La expresión puede ser una de las siguientes

- Una cadena de texto entre comillas dobles.
- Una fila y una columna de una tabla editable.

## Ejemplo

Muestra las palabras Estoy aquí cuando se ejecuta el script:

`Debug("I'm here")`
