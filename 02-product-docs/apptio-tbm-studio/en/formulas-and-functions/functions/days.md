---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Days function"
breadcrumb: []
source_path: "formulas-and-functions/functions/days.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Days function

Applies to: TBM Studio 12.0 and later

Converts a specified date to a decimal value, which can be used in formulas. The decimal value is
the number of days since January 1, 1970.

## Where to use

This function can be used in:

- Data sets (with column, rollup)
- Calculated metrics and reports with metric columns (with rollup operators)
- Formula columns in report tables (with column)
- In any modeled object's unit driver or in any grouped table.

## Syntax

`Days(date_expression)`

## Arguments

*date\_expression*

> An expression that evaluates to a date to be converted to a double value. The expression must be
> date only. It cannot include time.

## Return type

Number

## Example

The following example calculates the number of days between the project start and project end
dates, and then multiplies the result by the project cost per day.

> `=(Days(ProjectEnd)-Days(ProjectStart))*ProjectCostPerDay`

## Converting days to a UNIX time stamp

A UNIX time stamp is the number of seconds that have elapsed since January 1, 1970. This number
can be useful if you want to do math with dates. You can convert the result from the Days function
into a UNIX time stamp using the following formula:

> `=Days(date_expression)*24*60*60`

This takes the out put from the Days function and multiplies it by the number of seconds in a
day: 24 hours x 60 minutes x 60 seconds.

For example, you could convert the dates shown in the table below:

![](../../../resources/images/studio_images/studioimages/studio/stu126.png)

The formula for the Days Function column is: =Days(Date)

The formula for the UNIX Time Stamp column is: =(Days Function)\*24\*60\*60

See also:

- [CurrentDate](currentdate.htm "(Opens in a new tab or window)")
- [Hours](hours.htm "(Opens in a new tab or window)")
- [Minutes](minutes.htm "(Opens in a new tab or window)")
- [Months](months.htm "(Opens in a new tab or window)")
