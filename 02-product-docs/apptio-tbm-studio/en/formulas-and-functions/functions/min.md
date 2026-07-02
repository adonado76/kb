---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Min function"
breadcrumb: []
source_path: "formulas-and-functions/functions/min.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Min function

Applies to: TBM Studio 12.0 and later

Compares two expressions and returns the lesser value.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Min(numeric_expression 1,numeric_expression 2)`

## Arguments

*numeric\_expression 1 and 2*

> Any expression that evaluates to a number. You must enter two, and only two, numeric
> expressions.

## Return type

The type of the expression of lessor value.

## Example

The following example contains complex arguments in a Min function. The first argument is 42
times the value in Hours. The second argument is the smaller of 3 and 7, which is 3. So, if Hours is
3, the first argument evaluates to 126, which is greater than 3, so the function returns 3.

> `=Min(42*Hours,Min(3,7))`

See also:

- [Max](max.htm "(Opens in a new tab or window)")
- [Large](large.htm "(Opens in a new tab or window)")
- [Small](small.htm "(Opens in a new tab or window)")
