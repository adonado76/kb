---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de anualización"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/annualize.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de anualización

**Se aplica a** : TBM Studio 12.0 y posteriores

La función Anualizar calcula el valor medio del periodo hasta la fecha para una métrica y, a continuación, multiplica ese valor por el número de periodos para proyectar el valor anual total del ejercicio. Esta función se utiliza más a menudo para proyectar valores reales, como costes y unidades, que valores de planificación y previsión. Estos últimos valores suelen entregarse para todo el año de una sola vez.

La función Anualizar es diferente de la [función Anualizar](annual.htm "(se abre en una pestaña o una ventana nueva)"). La función Anual devuelve el valor de una métrica especificada en la misma tabla para un año fiscal o natural determinado, sumando los valores de todo el año.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Métricas calculadas e informes con columnas de métricas
- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

`Annualize(metric)`

## Argumentos

*métrica*

Una métrica en el proyecto. La función devuelve el valor total anual proyectado de la métrica para el ejercicio fiscal basado en el valor de la métrica hasta el periodo actual.

## Tipo de retorno

Número

## Ejemplo

Supongamos que su ejercicio fiscal va de julio a junio. Estamos en enero y quiere proyectar los costes para el resto del año fiscal. Los costes totales hasta la fecha ascienden a 2.400.000 dólares. Se introduciría la siguiente función:

`=Annualize(Cost)`

La función realiza los siguientes cálculos:

2.400.00 $/6 periodos \* 12 periodos= 48.000.000 $

2.400.00 $/6 periodos \* 13 periodos= 52.000.000 $

Consulte también:

- [Anual](annual.htm "(se abre en una pestaña o una ventana nueva)")
- [PreviousMonth](previousmonth.htm "(se abre en una pestaña o una ventana nueva)")
- [PreviousYear](previousyear.htm "(se abre en una pestaña o una ventana nueva)")
- [TimePeriod](timeperiod.htm "(se abre en una pestaña o una ventana nueva)")
- [YearToDate](yeartodate.htm "(se abre en una pestaña o una ventana nueva)")
