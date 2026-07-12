---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Months function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/months.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Months function

Converts a specified date to a decimal value representing the number of periods since
January 1, 1970. Useful for time-based calculations such as determining durations or pro-rating
costs.

## Syntax

`Months(date_expression, format)`

## Arguments

- *date\_expression*: An expression that evaluates to a date to be converted to a
  double value. Format is: "MM/DD/YYYY HH:MM" or any other standard date format supported by
  the application. The expression can be the name of a column.
- *format*: A string literal that specifies the format of the date (e.g.,
  "MM/dd/yyyy"). Optional if the date format is auto-detectable. Optional

## Behavior

- Returns the number of periods (months) since January 1, 1970 as a decimal number.
- Partial periods are included as fractional values. For example, 1.1 represents one full
  month and part of another.
- Can be used in formulas for calculating durations, allocating costs, or comparing
  timeframes.

## Return type

Number

## Example

- `Months("01/01/1970")`: Returns 1 because it is the reference date.
- `Months("01/02/1970")`: Returns 1.032.
- `Months({ProjectEnd}) - Months({ProjectStart})`: Calculates the duration
  in months between two project dates.
- `(Months({ProjectEnd}) - Months({ProjectStart}))*` Multiplies the number
  of months between start and end dates by the monthly project cost to estimate total cost.

Note:

- The result includes partial months as decimal values, making it suitable for prorated
  calculations.
- Date format is required only if the date input cannot be parsed automatically by the
  platform.
- The function is based on January 1, 1970 as the epoch reference.
