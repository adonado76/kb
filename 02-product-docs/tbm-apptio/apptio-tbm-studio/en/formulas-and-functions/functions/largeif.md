---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "LargeIf function"
breadcrumb: []
source_path: "formulas-and-functions/functions/largeif.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LargeIf function

◆ Applies to: TBM Studio 12.0 and later

Returns the largest value in a category in a transform.

## Where to use

This function can be used in:

- Data sets (with column and rollup arguments)
- Calculated metrics and reports with metric columns (with rollup argument)
- Formula columns in report tables (with column and rollup arguments)

## Syntax

`LargeIf(category_column, value_column, [criteria])`

## Arguments

*category\_column*

The column containing the entries that will be grouped.

*value\_column*

The column containing the values that will be used to find the largest value in a category.

*criteria*

The values in the key column that will be evaluated, or the column name. If no criteria is
specified, then the criteria will be the current row value for the category\_column.

## Return type

Number

## Examples

Example 1: LargeIf with a criteria specified:

| Item | Category | Compare category | Average price | LargeIf |
| --- | --- | --- | --- | --- |
| A | Cat ABC | Cat DEF | 10 | 8 |
| D | Cat DEF | Cat ABC | 6 | 10 |
| E | Cat DEF | Cat ABC | 7 | 10 |
| F | Cat DEF | Cat ABC | 8 | 10 |

`=LargeIf(Category, Average Price, Compare Category)`

Example 2: LargeIf without a criteria specified:

| Item | Category | Average price | LargeIf |
| --- | --- | --- | --- |
| A | Cat ABC | 10 | 10 |
| D | Cat DEF | 6 | 8 |
| E | Cat DEF | 7 | 8 |
| F | Cat DEF | 8 | 8 |

`=LargeIf(Category, Average Price)`
