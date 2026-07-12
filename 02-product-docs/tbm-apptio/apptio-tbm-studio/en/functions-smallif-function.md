---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "SmallIf function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "SmallIf function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/smallif.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# SmallIf function

*Returns the smallest value in a group based on a specified category and optional criteria.*

## Syntax

SmallIf(category_column, value_column, [criteria])

## Arguments

category_column : The column used to group the data. Required

value_column : The column containing the values to evaluate for minimum value within each category. Required

criteria : Optional. A column name, text value, or numeric value used to filter the category. If not specified, the current row’s category_column value is used. Optional (default: current row’s value in category_column)

## Behavior

- Groups rows by the specified category_column.
- Filters rows using the provided criteria (if any).
- Returns the smallest value from value_column that matches the criteria within the group.

## Return type

Number

## Example 1: SmallIf with a criteria specified

| Item | Category | Compare category | Average price | SmallIf |
| --- | --- | --- | --- | --- |
| A | Cat ABC | Cat DEF | 10 | 6 |
| D | Cat DEF | Cat ABC | 6 | 10 |
| E | Cat DEF | Cat ABC | 7 | 10 |
| F | Cat DEF | Cat ABC | 8 | 10 |

=SmallIf(Category, Average Price, Compare Category)

## Example 2: SmallIfwithout a criteria specified

| Item | Category | Average price | SmallIf |
| --- | --- | --- | --- |
| A | Cat ABC | 10 | 10 |
| D | Cat DEF | 6 | 6 |
| E | Cat DEF | 7 | 6 |
| F | Cat DEF | 8 | 6 |

=SmallIf(Category, Average Price)

SmallIf(Region, Weight, Weight) : Returns the smallest Weight in each Region where the Region matches the current row's value.

SmallIf(Department, Budget, "Finance") : Returns the smallest Budget value for rows in the 'Finance' department.

SmallIf(Category, Amount) : Returns the smallest Amount for each row’s Category.
