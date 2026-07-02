---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "ConvertCurrencyFromBase función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/convertcurrencyfrombase.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ConvertCurrencyFromBase función

Convierte un valor de la moneda base a otra moneda multiplicándolo por el tipo correspondiente de la tabla de cambio de moneda.

## Sintaxis

`ConvertCurrencyFromBase(sourceColumn, currencyCode, rateType)`

## Parámetros

*columna fuente* : Una cadena de texto que especifica el código de moneda ISO (por ejemplo, "EUR") que identifica la moneda de destino. Obligatorio

*código de moneda* : Cadena de texto que especifica el código de moneda ISO (por ejemplo, "EUR") que identifica la moneda de destino. Obligatorio

*tipo de cambio* : Una cadena de texto que especifica el tipo de tasa a utilizar de la tabla de Cambio de Moneda (por ejemplo, "Plan"). Obligatorio

## Comportamiento

- Busca el tipo de cambio en la tabla de divisas que coincide con el código de divisa y el tipo de cambio proporcionados.
- Multiplica el valor de origen por el tipo coincidente para convertir el importe de la moneda base a la moneda especificada.
- Si no se encuentra ninguna tasa coincidente, la función devuelve cero.

## Tipo de retorno

Número

## Ejemplos

`ConvertCurrencyFromBase(Cost, "EUR", "Plan")`: Convierte el valor de la columna Coste de la moneda base a Euros utilizando el tipo de cambio "Plan".

`ConvertCurrencyFromBase(Revenue, "GBP", "Actual")`: Convierte el valor de la columna Ingresos de la moneda base a Libras Esterlinas utilizando el tipo de cambio "Actual".

Nota: Es una buena práctica convertir todos los valores financieros a una moneda común antes de utilizarlos en controladores o informes. Normalmente se utiliza en una columna de transformación para garantizar una representación coherente de la moneda en todos los conjuntos de datos.
