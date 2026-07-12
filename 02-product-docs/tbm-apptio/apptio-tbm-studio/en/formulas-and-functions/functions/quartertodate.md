---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "QuarterToDate function"
breadcrumb: []
source_path: "formulas-and-functions/functions/quartertodate.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# QuarterToDate function

Applies to: TBM Studio 12.0 and later

Returns the value in a specified metric in the same table for the current quarter, summing the
values up to and including the selected period.

The current quarter is the fiscal quarter as defined in the Configure Time Periods dialog
box, regardless of the current date selection in the date picker. The number of quarters summed will
be 1, 2, 3, or 4 depending on the current quarter.

## Where to use

This function can be used in:

- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

> `QuarterToDate(column)`

## Arguments

*column*

> Specifies the metric to sum.

## Return type

Number

## Example

The following example returns the value of the Cost metric.

> `=QuarterToDate(Cost)`

See also:

- [Annual](annual.htm "(Opens in a new tab or window)")
- [PreviousMonth](previousmonth.htm "(Opens in a new tab or window)")
- [PreviousYear](previousyear.htm "(Opens in a new tab or window)")
- [TimePeriod](timeperiod.htm "(Opens in a new tab or window)")
- [YearToDate](yeartodate.htm "(Opens in a new tab or window)")
