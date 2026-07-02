---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "TimePeriod function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/timeperiod.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# TimePeriod function

Returns the value of a specified metric at the beginning of a time period (e.g., month,
quarter, year) that is a specified number of periods before or after the current period. The
time unit is determined by the selected view or an explicit granularity suffix.

## Syntax

`TimePeriod(metric, offset)`

## Parameters

- **metric**: The metric column to retrieve values from for a prior or future time
  unit. Must refer to a column in the same table. Required
- **offset** : A numeric offset combined with an optional time unit suffix (e.g., 'm',
  'q', 'h', 'y') indicating how many periods to shift. Negative values shift backward;
  positive values shift forward. If no suffix is provided, the unit defaults to months.
  Required

## Behavior

- Returns the value of the metric at the beginning of the resolved period at the specified
  offset.
- The unit of time is determined by the suffix ('m' for month, 'q' for quarter, 'h' for
  half-year, 'y' for year), or defaults to month if omitted.

## Examples

- `TimePeriod(Sales, -6)`: Returns the value of {Sales} at the beginning of the
  period 6 months ago. The unit is month by default.
- `TimePeriod(Sales, -3q)`: Returns the value of {Sales} at the beginning of
  the period 3 quarters ago.
- `TimePeriod(Sales, -1y)`: Returns the value of {Sales} at the beginning of
  the period one year ago.

Note: Valid granularity suffixes include 'm' (month), 'q' (quarter), 'h' (half-year), and 'y'
(year).

## Return type

Number
