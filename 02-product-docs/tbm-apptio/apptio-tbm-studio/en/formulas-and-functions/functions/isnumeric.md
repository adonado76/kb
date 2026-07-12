---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "IsNumeric function"
breadcrumb: []
source_path: "formulas-and-functions/functions/isnumeric.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# IsNumeric function

Applies to: TBM Studio and later

Evaluates a string or column name to determine if it is a number.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic Text

## Syntax

*IsNumeric("value")*

or

*IsNumeric({column name})*

## Arguments

*value*

> The string to be evaluated. It must be enclosed in quotes.

*{column name}*

> The name of a column in a table.

## Return type

The function returns boolean true or false.

## Remarks

You can use the function inside the IF function on both sides of the equation and in the
STATUSICON function.

For example:

> ```
> IF(IsNumeric("423"),"OK","Check for
>         error.")
> ```
>
> `STATUSICON(IsNumeric("123"), LEN(TRIM(" hello ")) = 5 )`

## Examples

The following examples are shown with their return values.

- `IsNumeric("95")` = true
- `IsNumeric("95%")`= true
- `IsNumeric("95 Percent")` = false
- `IsNumeric({Location})` = false
- `IsNumeric({345})`= true
