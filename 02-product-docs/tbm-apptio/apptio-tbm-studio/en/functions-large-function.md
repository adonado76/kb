---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Large function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Large function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/large.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Large function

*Returns the largest value in a specified column.*

## Syntax

Large([rollup_operator]column)

## Parameters

rollup_operator

@, SOURCE, ~, or TARGET. This argument is optional and used only with metrics. See Rollup Operators .

column : The column to search for the largest value. You may specify a table prefix using TableName:ColumnName. Required

## Behavior

Scans the specified column and returns the largest (maximum) value.

## Return type

Numeric

## Example

Large(Budget) : Returns the largest value from the 'Budget' column.

Large(Financials:Cost) : Returns the largest value from the 'Cost' column in the 'Financials' table.
