---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Percentile function"
breadcrumb: []
source_path: "formulas-and-functions/functions/percentile.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Percentile function

Applies to: TBM Studio 12.0 and later

Returns a specified percentile for a specified column.

For a given set of numbers, a percentile is the value below which a certain percentage of the
numbers fall. For example, for a column containing 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9, the 30th
percentile is 2.3, which is the value below which 30 percent of the numbers fall (0,1,2). The
decimal point value .3 in the result is derived by taking the value that is 30% of the way between 2
and 3.

## Where to use

This function can be used in:

- Data sets (with column and rollup arguments)
- Calculated metrics and reports with metric columns (with column and rollup arguments)
- Formula columns in report tables (with column argument)
- In any modeled object's unit driver or in any grouped table.

## Syntax

`Percentile([rollup_operator]column,percentage)`

## Arguments

*rollup\_operator*

> @, SOURCE, ~, or TARGET. This argument is optional and used only with metrics. See [Rollup Operators](../operators.htm#Rollup).

*column*

> The column containing the set of numbers from which to evaluate the percentile.

*percentage*

> An number specifying the percentage threshold.

## Return type

Number

## Example

The following example returns the 50th percentile for the values contributing to the rollup in
the column Servers. If Servers in the source table contains: 500, 600, 700, and 1200, this example
returns 650.

> `=Percentile(@Servers,50)`
>
> `=Percentile(Servers,50)`

See also:

- [Average](average.htm "(Opens in a new tab or window)")
- [Large](large.htm "(Opens in a new tab or window)")
- [Small](small.htm "(Opens in a new tab or window)")
