---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "DurationOfMonth function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/durationofmonth.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DurationOfMonth function

The DurationOfMonth function returns the number of days, hours, minutes, seconds, or milliseconds
in a month for a specific year. It takes into account leap years.

## Syntax

```
DurationOfMonth (time_unit [, month [, year]])
```

## Return type

Number

## Parameters

- *time\_unit*: Specifies the time unit to return. Supported values: 'd' for days, 'h'
  for hours, 'm' for minutes, 's' for seconds, 'S' for milliseconds. Required
- *month*: Optional. An expression that evaluates to the month (1–12). Note: This
  parameter accepts an expression, meaning you can provide a literal value, a column
  reference, or the result of another function. Optional (default: Current month)
- *year*: Optional. An expression that evaluates to the year. Note: This parameter
  accepts an expression, meaning you can provide a literal value, a column reference, or the
  result of another function. Optional (default: Current year)

## Examples

- Returns 29 because February 2024 has 29 days (leap year):`=DurationOfMonth("d", 2,
  2024)`
- Returns the number of hours in the current month:`=DurationOfMonth("h")`

Note: Supported time units: 'd' (day), 'h' (hour), 'm' (minute), 's' (second), 'S'
(millisecond). If month or year are omitted, the current date is used as default.
