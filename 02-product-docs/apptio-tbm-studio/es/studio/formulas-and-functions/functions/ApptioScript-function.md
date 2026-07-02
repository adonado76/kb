---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de publicación periódica"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/ApptioScript-function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de publicación periódica

**Aplicable a** : TBM Studio 12.11.22 y versiones posteriores

La función «**Publicación periódica** » te permite automatizar la publicación de datos de tablas editables mediante una función de ApptioScript. Al hacer clic en el botón, el sistema te permite escribir Apptioscript para programar ejecuciones de publicación periódicas. Una vez ejecutado, el script publica los datos de la tabla editable en la tabla de transformación asociada.

## Dónde utilizarlo

Utiliza la sintaxis del campo «**Acción del** servidor» de un botón en un informe.

## Sintaxis

`PublishNow("schedule2", "schedule4",autoPromoteToProd="true")`

## Parámetros

El anexo 2 es un parámetro obligatorio, mientras que el resto de parámetros son opcionales

*Anexo 2* : Define cuándo debe ejecutarse la publicación periódica.

*autoPromoteToProd="true"* Si se configura en `true`, los cambios publicados se implementan en **el entorno de producción.** Si se configura en `false`, los cambios permanecen en el entorno **de prueba**.

## Ejemplo

`PublishNow("Weekday Evening Publish", autoPromoteToProd="true")`

Esto se publicará todas las tardes de lunes a viernes y se transferirán los datos a la tabla de transformación correspondiente.
