---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "ConvertCurrencyToBase function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "ConvertCurrencyToBase function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/convertcurrencytobase.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# ConvertCurrencyToBase function

*Converts a value to the base currency by dividing it by the corresponding rate from the Currency Exchange table.*

## Syntax

ConvertCurrencyToBase(source column, currency code, rate type)

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

ConvertCurrencyToBase(Expense, "EUR", "Plan") : Converts the value in the Expense column from Euros to the base currency using the 'Plan' rate type.

ConvertCurrencyToBase(SalesAmount, "JPY", "Actual") : Converts the SalesAmount from Japanese Yen to the base currency using the 'Actual' rate type.
