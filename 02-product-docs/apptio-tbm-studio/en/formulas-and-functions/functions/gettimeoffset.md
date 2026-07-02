---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "GetTimeOffset function"
breadcrumb: []
source_path: "formulas-and-functions/functions/gettimeoffset.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetTimeOffset function

Applies to: TBM Studio v12.1 and later.

Use the GetTimeOffset function to determine the offset of the current period to the current
month, quarter, half year, or whole year. For example, if it is April 2017, and you set the function
to determine the offset from the end of the quarter (June 2017), it would return a value of 2.

## Where to use

This function can be used in:

- Data sets (label type fields only)
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`=GetTimeOffset("granularity","start/end","span",[period])`

## Arguments

*granularity*

> Specifies the block of time used to express the offset.
>
> Values: month, quarter, half, year
>
> The value must be equal to or smaller than the value entered for the "span" argument.

*start/end*

> Specifies when the offset should be calculated from.
>
> Values: start, end, calendarStart, calendarEnd
>
> If the second argument is "start" or "end," the granularity and span arguments are based on
> "fiscal year", not "calendar year." If the second argument is "calendarStart," the calculation is
> made from the first calendar month of the current calendar year (always January). If the second
> argument is "calendarEnd", the calculation is made from the last calendar month in the year (always
> December). Default will use the format specified by the locale.

*span*

> Specifies the block of time within which the offset is calculated.
>
> Values: month, quarter, half, year, alltime
>
> Alltime refers to the time span covered by the project start and end dates of the project. The
> dates are set in the Project Time Settings dialog and reflected in the date picker.

*period*

> This is an optional argument. It provides an alternate date to the default current date used in
> the calculation. The date must be specified in the following format: Jan:FY2016. It only supports
> fiscal periods.

## Possible outputs on a 12 period calendar

- GetTimeOffset(Month,Start/End,Quarter) gives 0, 1, or 2.
- GetTimeOffset(Month,Start/End,Half) gives 0, 1, 2, 3, 4, or 5.
- GetTimeOffset(Month,Start/End,Year) gives 0 through 11.

## Possible outputs on a 13 period calendar

- GetTimeOffset(Month,Start/End,Quarter) gives 0, 1, 2, or 3.
- GetTimeOffset(Month,Start/End,Half) gives 0, 1, 2, 3, 4, 5, or 6.
- GetTimeOffset(Month,Start/End,Year) gives 0 through 12.

## Possible outputs on any calendar

- GetTimeOffset(Month,CalendarStart/CalendarEnd,Quarter) gives 0, 1, or 2.
- GetTimeOffset(Month,CalendarStart/CalendarEnd,Half) gives 0, 1, 2, 3, 4, or 5.
- GetTimeOffset(Month,CalendarStart/CalendarEnd,Year) gives 0 through 11.

## Examples

- GetTimeOffset("Quarter","End","Year")=0 in any month of the last quarter of the year, 1 in the
  second to last quarter.
- GetTimeOffset("Month","End","Quarter")=0 in the last month of the quarter, 1 in the second to
  the last month.
