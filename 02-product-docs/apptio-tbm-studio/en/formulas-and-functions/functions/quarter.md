---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Quarter function"
breadcrumb: []
source_path: "formulas-and-functions/functions/quarter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Quarter function

Applies to: TBM Studio 12.0 and later

Returns the value of a specified metric in the same table for a specified quarter, summing the
values for the entire quarter. If no quarter is specified, the function is evaluated for the current
quarter. This function returns the total for the entire quarter regardless of what month in which it
is viewed.

## Where to use

This function can be used in:

- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Quarter(metric[,delta[,type]])`

## Arguments

*metric*

> A metric in the same table. The function returns the sum of this metric for the entire
> quarter.

*delta*

> The number of quarters to look forward or backward. To look backward, enter a negative number.
> For example, to look backward two quarters, enter -2.
>
> If not specified, *delta* defaults to 0.

*type*

> Codes indicating fiscal year or calendar year:
>
> - FY = Fiscal Year (Use for 445 variant and 13-period calendar projects)
> - CY = Calendar Year (Use for Gregorian calendar projects only)
>
> If not specified, *type* defaults to FY.

## Return type

Number

## Example

The following example returns the total cost for the current quarter:

> `=Quarter(Cost)`

The following example returns the total cost for the next quarter:

> `=Quarter(Cost,1)`

See also:

- [PreviousMonth](previousmonth.htm "(Opens in a new tab or window)")
- [QuarterToDate](quartertodate.htm "(Opens in a new tab or window)")
- [PreviousYear](previousyear.htm "(Opens in a new tab or window)")
- [TimePeriod](timeperiod.htm "(Opens in a new tab or window)")
- [YearToDate](yeartodate.htm "(Opens in a new tab or window)")
