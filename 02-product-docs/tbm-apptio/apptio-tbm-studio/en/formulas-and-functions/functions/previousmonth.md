---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "PreviousMonth function"
breadcrumb: []
source_path: "formulas-and-functions/functions/previousmonth.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PreviousMonth function

Applies to: TBM Studio 12.0 and later

Returns the value of a specified metric in the current table for the previous period.

## Where to use

This function can be used in:

- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`PreviousMonth(metric)`

## Arguments

*metric*

> A metric in the same table. The function returns the value of this metric for the previous
> month.

## Return type

Number

## Example

For a current date of August 2012, the following example returns the sum of Cost for July
2012.

> `=PreviousMonth(Cost)`

See also:

- [Annual](annual.htm "(Opens in a new tab or window)")
- [PreviousYear](previousyear.htm "(Opens in a new tab or window)")
- [TimePeriod](timeperiod.htm "(Opens in a new tab or window)")
- [YearToDate](yeartodate.htm "(Opens in a new tab or window)")
