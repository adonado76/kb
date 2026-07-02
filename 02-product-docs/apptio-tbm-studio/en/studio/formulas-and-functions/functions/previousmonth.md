---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "PreviousMonth function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/previousmonth.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PreviousMonth function

Returns the value of a specified metric from the previous month within the same table.
Useful for comparing current values to the prior month.

## Syntax

`PreviousMonth(metric)`

## Parameters

*metric*: A metric in the same table. The function returns the value of this metric for the
previous month.

## Return type

Number

## Example

- For a current date of August 2012, the following example returns the value of Cost for
  July 2012. `PreviousMonth(Cost)`
- Calculates the month-over-month change in cost. `Cost -
  PreviousMonth(Cost)`

Note: This function operates on the current table context and does not reference external
tables. If there is no data for the previous month, the function will return null.
