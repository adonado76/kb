---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Annual function"
breadcrumb: []
source_path: "formulas-and-functions/functions/annual.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Annual function

Applies to: TBM Studio 12.0 and later

Returns the value of a specified metric in the same table for a specified fiscal or calendar
year, summing the values for the entire year. If no year is specified, the function is evaluated for
the current year. This function returns the total for the entire year regardless of what month it is
viewed in.

Annual is different from the [YearToDate](yeartodate.htm "(Opens in a new tab or window)") function, which sums data up to the month selected.

## Where to use

This function can be used in:

- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Annual(metric[,delta[,type]])`

## Arguments

*metric*

> A metric in the same table. The function returns the sum of this metric for entire year.

*delta*

> The number of years to look forward or backward if delta is negative. If not specified, delta
> defaults to 0.

*type*

> Codes indicating fiscal year or calendar year:
>
> - FY = Fiscal Year (Use for 445 variant and 13 period calendar projects)
> - CY = Calendar Year (Use for Gregorian calendar projects only)
>
> If not specified, type defaults to FY.

## Return type

Number

## Example

The following example returns the total Cost for the current year.

`=Annual(Cost)`

`=Annual(Budget,0,"CY`

See also:

- [PreviousMonth](previousmonth.htm "(Opens in a new tab or window)")
- [PreviousYear](previousyear.htm "(Opens in a new tab or window)")
- [TimePeriod](timeperiod.htm "(Opens in a new tab or window)")
- [YearToDate](yeartodate.htm "(Opens in a new tab or window)")
