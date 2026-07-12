---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "PreviousYear function"
breadcrumb: []
source_path: "formulas-and-functions/functions/previousyear.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PreviousYear function

Applies to: TBM Studio 12.0 and later

Returns the sum of a specified metric in the current table for the previous number of periods in
a fiscal year. In a 12-period calendar, this would be 12 periods. In a 13-period calendar, this
would be 13 periods.

## Where to use

This function can be used in:

- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`PreviousYear(metric)`

## Arguments

*metric*

> A metric in the same table.

## Return type

Number

## Example

For the current date of August 2012, the following example returns the sum of Cost for August
2011 to July 2012.

> `=PreviousYear(Cost)`

See also:

- [Annual](annual.htm "(Opens in a new tab or window)")
- [PreviousMonth](https://help.apptio.com/en-us/studio/formulas-and-functions/functions/previousmonth.htm "(Opens in a new tab or window)")
- [TimePeriod](timeperiod.htm "(Opens in a new tab or window)")
- [YearToDate](yeartodate.htm "(Opens in a new tab or window)")
