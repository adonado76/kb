---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "SplitEx función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/splitex.html"
images:
  - "resources/images/studio_images/studioimages/studio_splitex-function_separate-row.png"
  - "resources/images/studio_images/studioimages/studio_splitex_formulas.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SplitEx función

Divide una cadena en una columna en varias filas en función de uno o varios caracteres delimitadores. Cada segmento de la división se convierte en una fila separada en el conjunto de datos transformado.. Si una columna de sus datos contiene varios valores separados por un carácter, como una coma, y desea generar una fila distinta para cada valor, utilice la función SplitEx. Por ejemplo, suponga que tiene la tabla que se muestra a continuación:

![muestra split ex f](../../../resources/images/studio_images/studioimages/studio_splitex_state%20and%20city.png)

Desea generar una fila distinta para cada ciudad, como se muestra a continuación:

![muestra split ex f](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_splitex-function_separate-row.png)

Introduzca la fórmula que se muestra a continuación para la columna **Ciudad** :

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_splitex_formulas.png)

![muestra split ex f]()

## Sintaxis

`Split(column,delimiter)`

## Parámetros

*columna* : La columna de una tabla que se va a dividir.

*delimitador* : Uno o más caracteres utilizados para dividir la cadena. Los delimitadores deben ir entre comillas dobles. Por ejemplo, ";>/" utiliza punto y coma, mayor que y barra oblicua como delimitadores. Obligatorio

## Tipo de retorno

Serie

## Ejemplos

`SplitEx(City, ",")`: Divide la columna {City} en comas. Por ejemplo:

**Entrada:**

| Estado | Ciudad |
| --- | --- |
| Washington | Seattle, Tacoma, Spokane |
| California | Los Ángeles, San Francisco, San Diego |

**Salida:**

| Estado | Ciudad |
| --- | --- |
| Washington | Seattle |
| Washington | Tacoma |
| Washington | Spokane |
| California | Los Ángeles |
| California | San Francisco |
| California | San Diego |

`SplitEx(Items, ";>/")`: Divide la columna {Items} utilizando punto y coma, mayor que o barra oblicua como delimitadores.
