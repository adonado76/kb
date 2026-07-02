---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Solucionar problemas de formatos de fecha no válidos en Planificación"
breadcrumb:
  - "Planning"
  - "Solución de problemas y preguntas frecuentes"
source_path: "it-planning/planning/ts_invalid_date_formats.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Solucionar problemas de formatos de fecha no válidos en Planificación

## Síntoma

No puede importar valores de fecha en Planning debido a un formato no válido, y no está seguro de qué formatos de fecha son correctos.

## ¿Qué está pasando?

Planning tiene requisitos estrictos para el formato de fecha que son más específicos que otros productos de Apptio.

## Solución: Sintaxis

Puede utilizar los siguientes formatos de fecha:

| América del Norte | Internacional | Asia oriental |
| --- | --- | --- |
| MM-DD-AAAA | DD-MM-AAAA | AAAA-MM-DD |
| MM/DD/AAAA | DD/MM/AAAA | AAAA/MM/DD |

Debe utilizar el mismo formato de fecha en todo el proyecto Planning .

Los formatos de fecha deben cumplir los siguientes requisitos sintácticos:

- Los meses deben representarse mediante números enteros. El texto no es válido. Por ejemplo, para el mes de agosto, 10 es válido, pero agosto o AUG no lo es.
- El mes y el día deben contener uno o dos dígitos.
- El año debe tener los 4 dígitos: AAAA.
- Puede utilizar "-" o "/" para separar números en la fecha, siempre que la puntuación seleccionada sea coherente.
- El orden de Mes y Día depende de su configuración regional.

## Solución: Configuración del idioma del navegador

Planning extrae el formato de fecha de tu navegador o de la configuración del sistema. Busque su navegador en la siguiente sección y asegúrese de que los ajustes del navegador están configurados correctamente.

## Google Chrome

Google Chrome utiliza el formato de fecha definido por la configuración del navegador.

1. En el navegador Google Chrome, abra el menú Chrome en la esquina superior derecha y seleccione Configuración.
2. Seleccione Avanzado > Idiomas > Idioma.
3. Cambia los ajustes de idioma para que el idioma que prefieras aparezca en primer lugar.

Tus ajustes se guardan automáticamente.

Para más información, visite [Google Chrome Help Center](https://support.google.com/chrome/?p=help "(se abre en una pestaña o una ventana nueva)").

## Microsoft Edge

Los navegadores de Microsoft utilizan el formato de fecha definido en la configuración regional de Windows.

1. Abra el Panel de control y seleccione Cambiar formatos de fecha, hora o número.
2. En el cuadro de diálogo Región de la pestaña Formatos, seleccione la configuración de fecha y hora que prefiera y, a continuación, seleccione Aplicar y Aceptar.
3. Borre las cookies y la memoria caché de su navegador.
