---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "SmallAcrossTime function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "SmallAcrossTime function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/smallacrosstime.html"
images:
  - "03-media/apptio-tbm-studio/stu015.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# SmallAcrossTime function

*Applies to : TBM Studio 12.0 and later*

Returns the smallest value in a specified column across one or more time periods.

If no time period is specified, it will behave like the Small function. The exception is if there is a trend_append[timeperiods] later in the path, in which case trend_append will inject its time periods in the SmallAcrossTime function somewhere up the path when it goes to find the tables to be included in the trend.

## Where to use

- Data sets (with column and rollup arguments)
- Calculated metrics and reports with metric columns (with rollup argument)
- Formula columns in report tables (with column and rollup arguments)

In any modeled object's unit driver or in any grouped table.

## Syntax

Small(column, period, period, etc.)

## Arguments

column

The column to return the smallest number from.

period

The period or periods to look in. The format must be MMM YYYY. For example: Jan 2013. There is no limit to the number of periods you can include.

## Return type

The same as the type of column.

## Examples

In the example below, the value for the Small column is being pulled from a period other than the currently displayed period:

- Average
- Percentile
- Large
- Min
- Max
