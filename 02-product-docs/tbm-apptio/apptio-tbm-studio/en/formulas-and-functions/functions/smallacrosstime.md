---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "SmallAcrossTime function"
breadcrumb: []
source_path: "formulas-and-functions/functions/smallacrosstime.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SmallAcrossTime function

Applies to: TBM Studio 12.0 and later

Returns the smallest value in a specified column across one or more time periods.

If no time period is specified, it will behave like the Small function. The exception is if there
is a trend\_append[timeperiods] later in the path, in which case trend\_append will inject its time
periods in the SmallAcrossTime function somewhere up the path when it goes to find the tables to be
included in the trend.

## Where to use

This function can be used in:

- Data sets (with column and rollup arguments)
- Calculated metrics and reports with metric columns (with rollup argument)
- Formula columns in report tables (with column and rollup arguments)

In any modeled object's unit driver or in any grouped table.

## Syntax

`Small(column, period, period, etc.)`

## Arguments

*column*

> The column to return the smallest number from.

*period*

> The period or periods to look in. The format must be MMM YYYY. For example: Jan 2013. There is no
> limit to the number of periods you can include.

## Return type

The same as the type of column.

## Examples

In the example below, the value for the Small column is being pulled from a period other than the
currently displayed period:

![](../../../resources/images/studio_images/studioimages/studio/stu015.png)

See also:

- [Average](average.htm "(Opens in a new tab or window)")
- [Percentile](percentile.htm "(Opens in a new tab or window)")
- [Large](large.htm "(Opens in a new tab or window)")
- [Min](min.htm "(Opens in a new tab or window)")
- [Max](max.htm "(Opens in a new tab or window)")
