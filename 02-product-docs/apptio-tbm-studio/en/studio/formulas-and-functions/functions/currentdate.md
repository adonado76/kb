---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "CurrentDate function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/currentdate.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CurrentDate function

Returns the starting date of the currently selected time period, if time is enabled. If
not, returns Eon 2000.

## Syntax

`CurrentDate([format_string])`

## Parameters

*format\_string*

Specifies a custom date format for the return value, following the same conventions as [DateFormat](dateformat.html "Converts a date expression to a specified date format.") function. Optional.

## Behavior

- Returns the start date of the currently selected time period.
- If a format\_string is provided, the output is formatted accordingly; otherwise, a
  default format is used.
- The function accepts zero or one argument.

## Examples

- `CurrentDate()`

  Returns the start date in the default format.
- `CurrentDate("yyyy-MM-dd")`

  Returns the start date formatted as
  'year-month-day'.

## Return type

String

See also:

- [Hours](hours.html "Converts a date value into the number of hours since January 1, 1970, as a numeric value.")
- [Now](now.html)
- [Minutes](minutes.html "Converts a date value into the number of minutes since January 1, 1970, as a numeric value.")
- [Months](months.html "Converts a specified date to a decimal value representing the number of periods since January 1, 1970. Useful for time-based calculations such as determining durations or pro-rating costs.")
