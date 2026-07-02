---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "PreviousYear function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/previousyear.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PreviousYear function

Returns the sum of a specified metric in the current table for the previous number of
periods in a fiscal year. In a 12-period calendar, this would be 12 periods. In a 13-period
calendar, this would be 13 periods.

## Syntax

`PreviousYear(metric)`

## Parameters

*metric*: A metric in the same table.

## Behavior

- Returns the total value of the specified metric over the previous fiscal year.
- The number of periods summed is determined by the calendar settings (e.g., 12 periods
  for monthly, 13 for 4-4-5 fiscal calendars).
- Calculations are relative to the current time period in context.

## Return type

Number

## Example

- `=PreviousYear(Cost)`: For the current date of August 2012, the following
  example returns the sum of {Cost} for August 2011 to July 2012.
- `Revenue - PreviousYear(Revenue)`: Calculates the year-over-year
  difference in revenue by subtracting the previous fiscal year's total from the current
  period's value.

Note: The number of periods used in the calculation depends on the calendar configuration
(e.g., 12 or 13).
