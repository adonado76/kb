---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "DateSum función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/datesum.html"
images:
  - "resources/images/studio_images/datesum-1.png"
  - "resources/images/studio_images/datesum-2.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DateSum función

Suma los valores de todas las columnas cuyos nombres se ajustan a los formatos de fecha reconocidos, ignorando las columnas no fechadas.

La función DateSum es útil si tiene tablas con columnas que contienen datos numéricos en columnas de fecha, así como en otras columnas. La función suma sólo las columnas con encabezados de fecha.

## Sintaxis

`DateSum()`

## Comportamiento

- Escanea las columnas de la tabla actual.
- Identifica las columnas cuyos nombres coinciden con los formatos de fecha estándar de la aplicación (como "Ene 2025", "02/2025", etc.).
- Suma los valores numéricos de todas las columnas de fecha identificadas.
- Ignora las columnas que no coinciden con un formato de fecha.

## Parámetros

No hay argumentos para esta función.

## Tipo de retorno

Número

## Ejemplo

Suma todas las columnas cuyas cabeceras son fechas, omitiendo cualquier columna no fechada.

La siguiente tabla muestra un ejemplo sencillo de la función DateSum. La función añade las columnas 2nd,3rd y 5ª, que son columnas con fecha como cabecera, pero ignora las columnas 1st,4th y 5ª. Y la diferencia entre Datesum y Total sum se puede ver en el siguiente ejemplo

![ejemplo de suma de fechas](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/datesum-1.png)

Ejemplo de pantalla con sintaxis

![ejemplo de suma de damas](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/datesum-2.png)

Nota: Esta función es útil para tablas que combinan columnas normales con columnas que representan periodos de tiempo. Los formatos de fecha reconocidos vienen determinados por la configuración regional y la configuración de la aplicación. Esta función no recibe argumentos.
