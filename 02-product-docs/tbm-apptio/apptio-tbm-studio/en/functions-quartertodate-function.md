---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "QuarterToDate function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "QuarterToDate function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/quartertodate.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# QuarterToDate function

*Returns the cumulative value of a specified metric from the beginning of the current fiscal quarter up to and including the current period.*

The current quarter is the fiscal quarter as defined in the Configure Time Periods dialog box, regardless of the current date selection in the date picker. The number of quarters summed will be 1, 2, 3, or 4 depending on the current quarter.

## Syntax

QuarterToDate(metric)

## Parameters

metric : The metric column whose values will be summed from the start of the current quarter to the current period. Must refer to a column in the same table. Required

## Behavior

- Sums the values of the specified metric from the start of the current fiscal quarter through the currently selected period.
- The fiscal quarter structure is defined in the Time Periods configuration, not based on the calendar date picker.

## Return type

Number

## Example

The following example returns the sum of the {Cost} metric from the beginning of the current quarter through the current period.

=QuarterToDate(Cost)
