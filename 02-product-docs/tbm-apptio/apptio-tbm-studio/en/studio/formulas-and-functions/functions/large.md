---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Large function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/large.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Large function

Returns the largest value in a specified column.

## Syntax

`Large([rollup_operator]column)`

## Parameters

*rollup\_operator*

@, SOURCE, ~, or TARGET. This argument is optional and used only with metrics. See [Rollup Operators](../operators.html "Applies to: TBM Studio 12.0 and later").

*column*: The column to search for the largest value. You may specify a table prefix using
TableName:ColumnName. Required

## Behavior

Scans the specified column and returns the largest (maximum) value.

## Return type

Numeric

## Example

*Large(Budget)*: Returns the largest value from the 'Budget' column.

*Large(Financials:Cost)*: Returns the largest value from the 'Cost' column in the
'Financials' table.
