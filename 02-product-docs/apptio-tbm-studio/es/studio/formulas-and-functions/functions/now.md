---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función Now"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/now.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función Now

La función Now( ) devuelve la fecha y hora actuales como una marca de tiempo UNIX basada en la hora del servidor. El tiempo se basa en el momento en que se ejecuta la función. El resultado se almacena en caché en el disco, a través de reinicios, etc. Sólo se actualiza cuando se realiza un nuevo cálculo completo.

## Sintaxis

`Now()`

## Comportamiento

- Devuelve la fecha y hora actuales del servidor como una marca de tiempo UNIX cuando se evalúa la función.
- Se utiliza en fórmulas que requieren la fecha actual del sistema, como el cálculo del tiempo transcurrido o el filtrado por actividad reciente.

## Parámetros

Ninguna

## Tipo de retorno

Fecha

## Ejemplo

- Devuelve la fecha y hora actual del sistema, por ejemplo para compararla con otro campo de fecha:

  ```
  Now()
  ```
- Calcula el número de periodos transcurridos desde el valor de {Start Date} column.: `Months(Now()) - Months({Start Date})`

**Notas** :

- Esta función no acepta argumentos.
- La función Ahora no puede utilizarse en tablas de transformación porque no se actualizará. Si se ha añadido una función Now a una tabla de transformación de la versión 8, debe eliminarse.
