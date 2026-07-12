---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "ConvertCurrencyFromBase function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "ConvertCurrencyFromBase function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/convertcurrencyfrombase.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# ConvertCurrencyFromBase function

*Converts a value from the base currency to another currency by multiplying it with a corresponding rate from the Currency Exchange table.*

## Syntax

ConvertCurrencyFromBase(sourceColumn, currencyCode, rateType)

## Parameters

source column : A text string specifying the ISO currency code (e.g., "EUR") that identifies the target currency. Required

currency code : A text string specifying the ISO currency code (e.g., "EUR") that identifies the target currency. Required

rate type : A text string that specifies the type of rate to use from the Currency Exchange table (e.g., "Plan"). Required

## Behavior

- Looks up the exchange rate in the Currency Exchange table that matches the provided currency code and rate type.
- Multiplies the source value by the matched rate to convert the amount from base currency to the specified currency.
- If no matching rate is found, the function returns zero.

## Return Type

Number

## Examples

ConvertCurrencyFromBase(Cost, "EUR", "Plan") : Converts the value in the Cost column from the base currency to Euros using the 'Plan' rate type.

ConvertCurrencyFromBase(Revenue, "GBP", "Actual") : Converts the value in the Revenue column from the base currency to British Pounds using the 'Actual' rate type.
