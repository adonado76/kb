---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "ConvertCurrencyToBase function"
breadcrumb: []
source_path: "formulas-and-functions/functions/convertcurrencytobase.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ConvertCurrencyToBase function

Applies to: TBM Studio 12.0 and later

The ConvertCurrencyToBase function divides the value by the rate in the Currency Exchange
table.

## Where to use

This function can be used in:

- Data sets (label type fields only)
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Multiple currencies

If you are working with multiple currencies, best practice recommends converting all cost figures
to a common currency before using them as drivers for objects in a model or for reporting. Perform
the conversion using a transform column on the data set.

## Syntax

> `ConvertCurrencyToBase(source column,"currency code","rate type")`

## Arguments

*source column*

> The numeric column in the current table that contains the values that will be converted. The
> values will be multiplied by the value in the Rate column in the Currency Exchange table that
> matches the given currency code and rate type.

*currency code*

> The ISO currency code that matches an entry in the Currency Exchange table’s Currency Code
> column, e.g. “EUR” (with the quotes).

*rate type*

> The rate type string that matches an entry in the Type column in the Currency Exchange table,
> e.g. “Plan” (with the quotes).

## Formats supported

In reports, the Apptio application supports currency formats for the following countries. The
format is determined by the locale selected for the project.

- Australia
- Austria
- Belgium, Dutch
- Belgium, French
- Czech Republic
- Denmark
- Finland
- France
- Germany
- Ireland, English & Irish
- Italy
- Luxembourg, French
- Luxembourg, German
- Netherlands
- Norway, Bokmal
- Norway, Nynorsk
- Peru
- Portugal
- Slovakia
- Spain, Catalan
- Spain, Spanish
- Sweden
- Switzerland, French
- Switzerland, German
- Switzerland, Italian
- United Kingdom
- United States
