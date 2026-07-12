---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Small function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Small function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/small.html"
images:
  - "03-media/apptio-tbm-studio/stu014.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Small function

*Returns the smallest value in a specified column.*

## Syntax

Small([rollup_operator]column)

## Parameters

rollup_operator

@, SOURCE, ~, or TARGET. This argument is optional and used only with metrics. See Rollup Operators .

column : The column to search for the smallest value. You may specify a table prefix using TableName:ColumnName. Required

## Behavior

Scans the specified column and returns the smallest (minimum) value.

## Return type

Number

## Examples

=Small(@Desktop)

=Small(Desktop)

Small(Budget) : Returns the smallest value from the 'Budget' column.

Small(Financials:Cost) : Returns the smallest value from the 'Cost' column in the 'Financials' table.
