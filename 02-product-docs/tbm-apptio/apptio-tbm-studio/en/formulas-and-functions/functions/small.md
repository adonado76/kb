---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Small function"
breadcrumb: []
source_path: "formulas-and-functions/functions/small.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Small function

Applies to: TBM Studio 12.0 and later

Returns the smallest value in a specified column.

## Where to use

This function can be used in:

- Data sets (with column, rollup)
- Calculated metrics and reports with metric columns (with rollup operators)
- Formula columns in report tables (with column)
- In any modeled object's unit driver or in any grouped table.

## Syntax

`Small([rollup_operator]column)`

## Arguments

*rollup\_operator*

> @, SOURCE, ~, or TARGET. This argument is optional and used only with metrics. See [Rollup Operators](../operators.htm#Rollup).

*column*

> The column to return the smallest number from.

## Return type

The same as the type of column.

## Examples

![](../../../resources/images/studio_images/studioimages/studio/stu014.png)

> `=Small(@Desktop)`
>
> `=Small(Desktop)`

See also:

- [Average](average.htm "(Opens in a new tab or window)")
- [Percentile](percentile.htm "(Opens in a new tab or window)")
- [Large](large.htm "(Opens in a new tab or window)")
- [Min](min.htm "(Opens in a new tab or window)")
- [Max](max.htm "(Opens in a new tab or window)")
