---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "GetTimeOffset función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/gettimeoffset.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetTimeOffset función

**Se aplica a** : TBM Studio v12.1 y posteriores.

Utilice la función GetTimeOffset para determinar el desfase del período actual con respecto al mes, trimestre, semestre o año completo en curso. Por ejemplo, si estamos en abril de 2017 y configuras la función para determinar el desfase desde el final del trimestre (junio de 2017), devolvería un valor de 2.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos (sólo campos de tipo etiqueta)
- Métricas calculadas e informes con columnas de métricas
- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

`=GetTimeOffset("granularity","start/end","span",[period])`

## Argumentos

*granularidad*

Especifica el bloque de tiempo utilizado para expresar el desplazamiento.

Valores: mes, trimestre, semestre, año

El valor debe ser igual o inferior al valor introducido para el argumento "span".

*inicio/fin*

Especifica a partir de cuándo debe calcularse el desplazamiento.

Valores: inicio, fin, calendarStart, calendarEnd

Si el segundo argumento es "start" o "end", los argumentos de granularidad y span se basan en "año fiscal", no en "año natural" Si el segundo argumento es "calendarStart," el cálculo se realiza a partir del primer mes natural del año natural en curso (siempre enero). Si el segundo argumento es "calendarEnd", el cálculo se realiza a partir del último mes natural del año (siempre diciembre). Por defecto se utilizará el formato especificado por la configuración regional.

*span*

Especifica el bloque de tiempo dentro del cual se calcula el desplazamiento.

Valores: mes, trimestre, semestre, año, todo el tiempo

El tiempo total se refiere al periodo de tiempo cubierto por las fechas de inicio y fin del proyecto. Las fechas se establecen en el cuadro de diálogo **Configuración de hora del proyecto** y se reflejan en el selector de fechas.

*periodo*

Se trata de un argumento opcional. Proporciona una fecha alternativa a la fecha actual por defecto utilizada en el cálculo. La fecha debe especificarse en el siguiente formato: Jan:FY2016. Sólo admite períodos fiscales.

## Posibles resultados en un calendario de 12 periodos

- GetTimeOffset(Month,Start/End,Quarter ) da 0, 1 ó 2.
- GetTimeOffset(Month,Start/End,Half ) da 0, 1, 2, 3, 4 ó 5.
- GetTimeOffset(Month,Start/End,Year ) da 0 a 11.

## Posibles resultados en un calendario de 13 periodos

- GetTimeOffset(Month,Start/End,Quarter ) da 0, 1, 2 ó 3.
- GetTimeOffset(Month,Start/End,Half ) da 0, 1, 2, 3, 4, 5 ó 6.
- GetTimeOffset(Month,Start/End,Year ) da 0 a 12.

## Posibles salidas en cualquier calendario

- GetTimeOffset(Month,CalendarStart/CalendarEnd,Quarter ) da 0, 1 ó 2.
- GetTimeOffset(Month,CalendarStart/CalendarEnd,Half ) da 0, 1, 2, 3, 4 ó 5.
- GetTimeOffset(Month,CalendarStart/CalendarEnd,Year ) da 0 a 11.

## Ejemplos

- GetTimeOffset("Quarter","End","Year" )=0 en cualquier mes del último trimestre del año, 1 en el penúltimo trimestre.
- GetTimeOffset("Month","End","Quarter" )=0 en el último mes del trimestre, 1 en el penúltimo mes.
