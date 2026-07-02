---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "TimePeriod function"
breadcrumb: []
source_path: "formulas-and-functions/functions/timeperiod.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# TimePeriod function

**Applies to**: TBM Studio 12.0 and later

Returns the value of a specified metric in the same table for the time unit (for example, month
or period) that falls a specified number of time units prior to or after the current time unit.

The TimePeriod function is useful for comparing a value in the current period with the value in
the same period a year ago. For example, if it is September 2013, you can compare cost in the
current period with cost in September 2012.

The TimePeriod function depends on the current calendar view as selected in the date picker:
period or month, quarter, half-year, or full year.

## Where to use

This function can be used in:

- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`TimePeriod(metric,time)`

## Arguments

*metric*

> Specifies the metric to sum.

*time*

> An integer that specifies a number of time units relative to the current time unit. A
> negative integer results in that number of units prior to the current time period, a positive
> integer after the current time period. The default unit is one month.
>
> Optional timespan values
> that can be entered after the integer are:
>
> - m for month
> - q for quarter
> - h for half-year
> - y for year
>
> Other columns in the underlying table can be used as well. To reference another column,
> enclose the column name in braces. For example, if your table contains a column called
> “NumberOfTimeUnits” and you want to use that you would do
> this:
>
> =TimePeriod(metric,{NumberOfTimeUnits})
>
> If the units were years, you could do
> this:
>
> =TimePeriod(metric,{NumberOfTimeUnits}y)
>
> You can also use other functions such as
> CurrentDate and Value.

## Return type

Number

## 12-Period Calendar Examples

| Example function | Return value forcurrent month = July 2012(assuming 12-period calendar) |
| --- | --- |
| =TimePeriod(Sales,-6) | The value of Sales for January 2012. |
| =TimePeriod(Sales,-3) | The value of Sales for April 2012. |
| =TimePeriod(Sales,-1) | The value of Sales for June 2012.The same as =PREVIOUSMONTH(Sales) (if in non-aggregate view of time). |
| =TimePeriod(Sales,-12) | The value of for Sales July 2011. |

## 13-Period Calendar Examples

| Example Function | Return Value ForCurrent Period = Peroid 6 FY2012(assuming 13 period calendar) |
| --- | --- |
| =TimePeriod(Sales,-6) | The value of Sales for Period 1 FY2012 |
| =TimePeriod(Sales,-3) | The value of Sales for Period 3 FY2012 |
| =TimePeriod(Sales,-1) | The value of Sales for Period 5 FY2012The same as =PREVIOUSMONTH(Sales) |
| =TimePeriod(Sales,-12) | The value of for Sales Period 7 FY2011 |

See also:

- [Annual](annual.htm "(Opens in a new tab or window)")
- [PreviousYear](previousyear.htm "(Opens in a new tab or window)")
- [PreviousMonth](previousmonth.htm "(Opens in a new tab or window)")
- [YearToDate](yeartodate.htm "(Opens in a new tab or window)")
