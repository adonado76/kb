---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "YearToDate function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "YearToDate function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/yeartodate.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# YearToDate function

*Returns the cumulative value of a specified metric from the beginning of the current fiscal year up to and including the current period. This differs from the Annual function, which always returns the total for the entire year regardless of the current period.*

YearToDate is different from the Annual function, which returns the total for the entire year regardless of the period in which it is viewed.

The current year is the fiscal year as defined in the Configure Time Periods dialog box, regardless of the current date selection in the date picker.

## Syntax

YearToDate(metric)

## Parameters

metric : The metric column whose values will be summed from the start of the fiscal year through the current period. Must refer to a column in the same table. Required

## Behavior

Sums the values of the specified metric from the beginning of the fiscal year up through the currently selected period. The fiscal year structure is defined in the Time Periods configuration and is not affected by the date picker.

## Return type

Number

## Example

The following example returns the year-to-date sum of the {Cost} metric.

=YearToDate(Cost)
