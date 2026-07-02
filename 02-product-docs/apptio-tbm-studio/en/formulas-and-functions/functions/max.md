---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Max function"
breadcrumb: []
source_path: "formulas-and-functions/functions/max.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Max function

Applies to: TBM Studio 12.0 and later

Compares two expressions and returns the greater value.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Max(numeric_expression,numeric_expression)`

## Arguments

*numeric\_expression*

> Any expression that evaluates to a number.

## Return type

Number

## Example

The following example contains complex arguments in a Max function. The first argument is 42
times the value in Hours. The second argument is the larger of 3 and 7, which is 7. So, if Hours is
3, the first argument evaluates to 126, which is greater than 7, so the function returns 126.

> `=Max(42*Hours,Max(3,7))`

See also:

- [Min](min.htm "(Opens in a new tab or window)")
- [Large](large.htm "(Opens in a new tab or window)")
- [Small](small.htm "(Opens in a new tab or window)")
