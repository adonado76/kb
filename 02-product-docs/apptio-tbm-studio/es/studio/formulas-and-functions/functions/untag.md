---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de eliminación de etiquetas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/untag.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de eliminación de etiquetas

**Se aplica a** : TBM Studio 12.0 y posteriores

La función Untag indica a la aplicación que ignore cualquier etiqueta asignada a los controladores del modelo actual.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Columnas de fórmulas en tablas de informes
- Fórmulas de origen de la asignación

En una fórmula de asignación **avanzada** en un modelo.

## Sintaxis

`Untag(value)`

## Argumentos

*valor*

Ya sea una métrica modelada o calculada, o una fórmula.

## Tipo de retorno

El tipo de retorno es el mismo que la columna de argumentos.

## Ejemplo

`=SOURCE*Untag({Qualified CtB (Cost driver)})`
