---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Len function"
breadcrumb: []
source_path: "formulas-and-functions/functions/len.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Len function

Applies to: TBM Studio 12.0 and later

Returns the length of a string.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic Text

## Syntax

`Len(string_expression)`

## Arguments

string\_expression

> The expression that is evaluated. The string\_expression can include a column name, in which case
> the string contained in that column for the current row is evaluated along with the rest of the
> expression.

## Return type

Number

## Examples

- In the following example, if the column Ticket Description for the current row contains the
  string Hardware, the function returns 8, which is the number of characters in the string
  Hardware.`=Len({Ticket Description})`
- In the following example, the string Support is added to the expression. So, if the column
  Ticket Description for the current row contains the string Hardware, the function returns 15, which
  is the number of characters in the string Hardware (8) plus the number of characters in the string
  Support (7).`=Len("Support"+Ticket Description)`
