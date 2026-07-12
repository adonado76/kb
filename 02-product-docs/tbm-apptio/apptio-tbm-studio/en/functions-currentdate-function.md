---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "CurrentDate function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "CurrentDate function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/currentdate.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# CurrentDate function

*Returns the starting date of the currently selected time period, if time is enabled. If not, returns Eon 2000.*

## Syntax

CurrentDate([format_string])

## Parameters

format_string

Specifies a custom date format for the return value, following the same conventions as DateFormat function. Optional.

## Behavior

- Returns the start date of the currently selected time period.
- If a format_string is provided, the output is formatted accordingly; otherwise, a default format is used.
- The function accepts zero or one argument.

## Examples

- CurrentDate() Returns the start date in the default format.
- CurrentDate("yyyy-MM-dd") Returns the start date formatted as 'year-month-day'.

## Return type

String

- Hours
- Now
- Minutes
- Months
