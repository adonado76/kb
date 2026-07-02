---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función Undrill"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/undrill.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función Undrill

**Se aplica a** : TBM Studio 12.0 y posteriores

Devuelve el valor de una métrica en el nivel superior de un modelo.

El valor devuelto para una métrica se basa en el nivel hasta el que se ha perforado en un modelo. Si se encuentra varios niveles más abajo en un modelo, pero desea el valor de la métrica en el nivel superior del modelo, puede utilizar la función Undrill.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

`Undrill(metric)`

## Argumentos

*métrica*

Una métrica modelada o calculada.

## Tipo de retorno

Número

## Ejemplos

Suponga que tiene un modelo que incluye varias unidades de negocio y que los costes de servidor se han asignado a cada unidad de negocio. Si profundiza varios niveles de informes en una de las unidades de negocio, digamos Retail, verá los costes de servidor para Retail. Pero, ¿y si quisiera mostrar el porcentaje de los costes del servidor asignados a la venta al por menor?

Puede utilizar la función Undrill para obtener los costes totales de servidor de todas las unidades de negocio y dividirlos entre los costes de servidor de Retail. Podría añadir una columna a la tabla del informe para contener el coste no perforado utilizando lo siguiente:

`=Undrill(Cost)`
