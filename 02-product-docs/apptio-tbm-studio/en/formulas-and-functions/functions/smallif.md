---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "SmallIf function"
breadcrumb: []
source_path: "formulas-and-functions/functions/smallif.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SmallIf function

◆ Applies to: TBM Studio 12.0 and later

Returns the smallest value in a category in a transform.

## Where to use

This function can be used in:

- Data sets (with column and rollup arguments)
- Calculated metrics and reports with metric columns (with rollup argument)
- Formula columns in report tables (with column and rollup arguments)

## Syntax

`SmallIf(category_column, value_column, [criteria])`

## Arguments

*category\_column*

> The column containing the entries that will be grouped.

*value\_column*

> The column containing the values that will be used to find the smallest value in a category.

*criteria*

> The values in the key column that will be evaluated, or the column name. If no criteria is
> specified, then the criteria will be the current row value for the category\_column.

## Return type

Number

## Example 1: SmallIf with a criteria specified

| Item | Category | Compare category | Average price | SmallIf |
| --- | --- | --- | --- | --- |
| A | Cat ABC | Cat DEF | 10 | 6 |
| D | Cat DEF | Cat ABC | 6 | 10 |
| E | Cat DEF | Cat ABC | 7 | 10 |
| F | Cat DEF | Cat ABC | 8 | 10 |

`=SmallIf(Category, Average Price, Compare Category)`

## Example 2: SmallIfwithout a criteria specified

| Item | Category | Average price | SmallIf |
| --- | --- | --- | --- |
| A | Cat ABC | 10 | 10 |
| D | Cat DEF | 6 | 6 |
| E | Cat DEF | 7 | 6 |
| F | Cat DEF | 8 | 6 |

`=SmallIf(Category, Average Price)`
