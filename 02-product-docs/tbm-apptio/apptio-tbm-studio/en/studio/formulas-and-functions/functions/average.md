---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Average function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/average.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Average function

Returns the average value in a specified column or metric.

## Syntax

`Average(column)`

## Arguments

*rollup\_operator*

@, SOURCE, ~, or TARGET. This argument is optional and used only with metrics. See [Rollup Operators](../operators.html "Applies to: TBM Studio 12.0 and later").

*column*: The name of the column or metric for which to calculate the average. Optional

## Return type

Number

## Example

`Average(Budget)`:Returns the average value from the 'Budget' column.

`Average(Financials:Expense)`: Returns the average value from the 'Expense'
column in the 'Financials' table.

Note: You can specify just a column or a table and column together using a colon separator.
The function ignores null values and non-numeric values when calculating the average.
