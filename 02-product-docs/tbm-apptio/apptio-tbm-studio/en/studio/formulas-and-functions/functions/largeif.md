---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "LargeIf function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/largeif.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LargeIf function

Returns the largest value in a group based on a specified category and optional
criteria.

## Syntax

`LargeIf(category_column, value_column, criteria)`

## Parameters

*category\_column*: The column used to group the data. Required

*value\_column*: The column containing the values to evaluate for maximum value within each
category. Required

*criteria*: Optional. A column name, text value, or numeric value used to filter the
category. If not specified, the current row’s category\_column value is used. Optional
(default: current row’s value in category\_column)

## Behavior

- Groups rows by the specified category\_column.
- Filters rows using the provided criteria (if any).
- Returns the largest value from value\_column that matches the criteria within the group.

## Return type

Number

## Examples

**Example 1**: LargeIf with a criteria specified:

| Item | Category | Compare category | Average price | LargeIf |
| --- | --- | --- | --- | --- |
| A | Cat ABC | Cat DEF | 10 | 8 |
| D | Cat DEF | Cat ABC | 6 | 10 |
| E | Cat DEF | Cat ABC | 7 | 10 |
| F | Cat DEF | Cat ABC | 8 | 10 |

`=LargeIf(Category, Average Price, Compare Category)`

**Example 2**: LargeIf without a criteria specified:

| Item | Category | Average price | LargeIf |
| --- | --- | --- | --- |
| A | Cat ABC | 10 | 10 |
| D | Cat DEF | 6 | 8 |
| E | Cat DEF | 7 | 8 |
| F | Cat DEF | 8 | 8 |

`=LargeIf(Category, Average Price)`: Returns the largest Amount for each row’s
Category.

`LargeIf(Region, Weight, Weight)`: Returns the largest Weight in each Region
where the Region matches the current row's value.

`LargeIf(Department, Budget, "Finance")`: Returns the largest Budget value
for rows in the 'Finance' department.
