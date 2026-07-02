---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Period function"
breadcrumb: []
source_path: "formulas-and-functions/functions/period.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Period function

Applies to: TBM Studio 12.0 and later

Returns a string that represents a selected time period based on a specified example format.

This function can be useful within an HTML region, where dynamic text scripting is used. You can
specify an example format string such as monthly to be used as a suffix with a time-dependent
data value. Then when you view that data value for different time periods, the suffix reflects the
appropriate time period. In this example, if you view the data for a year, the suffix is
yearly, for a quarter, it is quarterly, and so forth.

## Where to use

This function can be used in:

- Data sets
- Formula columns in report tables
- Dynamic text

## Syntax

`Period(["time_period"][1])`

## Arguments

Enter one of the two arguments, but not both.

`time_period`

A string that provides an example of the format, such as month, monthly,
GB/month, $ per month, or $/m. The string must contain an element that
represents month. Formats include:

- "month" (case insensitive)
- "monthly" (case insensitive)
- ending in "month"ending in "Month"
- ending in "/m"
- ending in "/M"
- "period" (case sensitive)
- ending in "period"
- ending in "Period"
- ending in "/p"
- ending in "/P"

`1`

> Returns a number that represents the current time period: 1 for period or month, 3 for quarter,
> and 12 or 13 for year depending on the calendar type (Gregorian, 445 variant, or 13 period). This
> argument can be used if you want to use the return value in calculations.
>
> For example, =Cost/Period(1) would result in the average cost per period or month.

## Return type

String

## Example

In the following example, using the Period function allows Cost to be displayed with a suffix
that changes dynamically with the selected time period. If you are looking at data for a year and
Cost=$503,122, the output is $503,122 per year, but if you are looking at data for a quarter,
the output is $503,122 per quarter.

> ```
> Total Cost: <%=Cost%> <%=Period("per
>       month")%>
> ```
