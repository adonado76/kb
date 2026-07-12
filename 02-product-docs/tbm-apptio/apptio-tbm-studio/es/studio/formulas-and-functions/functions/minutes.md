---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función minutos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/minutes.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug120.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función minutos

Convierte un valor de fecha en el número de minutos transcurridos desde el 1 de enero de 1970, como valor numérico.

## Sintaxis

`Minutes(date_expression, date_format)`

## Parámetros

- *expresión\_fecha* : La fecha a convertir. El formato debe ser un formato de fecha compatible. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio
- *formato\_fecha* : El formato de la cadena de fecha. Obligatorio sólo si la expresión\_fecha no está en un formato estándar admitido. OptionalAn que evalúa una fecha para convertirla en un valor doble. El formato es MM/DD/AAAA HH:MM o cualquier otro formato de fecha estándar soportado por la aplicación.

## Comportamiento

- Toma una entrada de fecha y la convierte en un valor numérico que representa los minutos transcurridos desde la época (1 de enero de 1970).
- Si no se proporciona date\_format, la aplicación asume que la entrada está en un formato estándar compatible.
- El resultado es útil para calcular diferencias horarias, duraciones o realizar operaciones aritméticas basadas en el tiempo.

## Tipo de retorno

Número

## Ejemplo

Supongamos que desea calcular la duración de las llamadas de asistencia. Tiene un conjunto de datos con dos columnas: SupportTicket\_Start y SupportTicket\_End. Los datos de las columnas tienen el formato MMDDAAA HH:MM. Se define una tercera columna en la tabla para calcular la duración de cada llamada. La fórmula de la tercera columna es:

`=(Minutes({SupportTicket_End}))-(Minutes({SupportTicket_Start}))`

El resultado se muestra a continuación:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug120.png)

Nota:

- Si la fecha introducida tiene un formato no estándar, utilice el parámetro date\_format para especificar el formato correcto.
- Consulte las reglas de formato en la función DateFormat.
- Los formatos de fecha más habituales son MM/DD/AAAA, AAAA-MM-DD y MM/DD/AAAA HH:MM.
