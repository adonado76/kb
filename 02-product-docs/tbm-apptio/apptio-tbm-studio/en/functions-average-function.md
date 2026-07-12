---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Average function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Average function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/average.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Average function

*Returns the average value in a specified column or metric.*

## Syntax

Average(column)

## Arguments

rollup_operator

@, SOURCE, ~, or TARGET. This argument is optional and used only with metrics. See Rollup Operators .

column : The name of the column or metric for which to calculate the average. Optional

## Return type

Number

## Example

Average(Budget) :Returns the average value from the 'Budget' column.

Average(Financials:Expense) : Returns the average value from the 'Expense' column in the 'Financials' table.
