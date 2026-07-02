---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Large function"
breadcrumb: []
source_path: "formulas-and-functions/functions/large.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Large function

Applies to: TBM Studio 12.0 and later

Returns the largest value in a specified column.

## Where to use

This function can be used in:

- Data sets (with column and rollup arguments)
- Calculated metrics and reports with metric columns (with rollup argument)
- Formula columns in report tables (with column and rollup arguments)

## Syntax

`Large([rollup_operator]column)`

## Arguments

*rollup\_operator*

> @, SOURCE, ~, or TARGET. This argument is optional and used only with metrics. See [Rollup Operators](../operators.htm#Rollup).

*column*

> The column to return the largest number from.

## Return type

The same as the type of column.

## Example

*=Large(@Space)*

*=Large(Space)*

See also:

- [Average](average.htm "(Opens in a new tab or window)")
- [Percentile](percentile.htm "(Opens in a new tab or window)")
- [Small](small.htm "(Opens in a new tab or window)")
- [Min](min.htm "(Opens in a new tab or window)")
- [Max](max.htm "(Opens in a new tab or window)")
