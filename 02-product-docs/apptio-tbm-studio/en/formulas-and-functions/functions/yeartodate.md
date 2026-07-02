---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "YearToDate function"
breadcrumb: []
source_path: "formulas-and-functions/functions/yeartodate.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# YearToDate function

Applies to: TBM Studio 12.0 and later

Returns the value in a specified metric in the same table for the current fiscal year, summing
the values up to and including the selected period.

YearToDate is different from the [Annual](annual.htm "(Opens in a new tab or window)") function, which returns the total for the entire year regardless of the period in
which it is viewed.

The current year is the fiscal year as defined in the Configure Time Periods dialog box,
regardless of the current date selection in the date picker.

## Where to use

This function can be used in:

- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`YearToDate(column)`

## Arguments

*column*

> Specifies the metric to sum.

## Return type

Number

## Example

The following example returns the year-to-date value of the Cost metric.

> `=YearToDate(Cost)`

## See also

- [Annual](annual.htm "(Opens in a new tab or window)")
- [PreviousMonth](previousmonth.htm "(Opens in a new tab or window)")
- [PreviousYear](previousyear.htm "(Opens in a new tab or window)")
- [TimePeriod](timeperiod.htm "(Opens in a new tab or window)")
- [QuarterToDate](quartertodate.htm "(Opens in a new tab or window)")
