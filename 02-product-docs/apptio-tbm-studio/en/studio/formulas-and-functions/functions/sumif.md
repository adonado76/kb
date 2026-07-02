---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "SumIf function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/sumif.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SumIf function

Returns the sum of values in a column, including only the rows that match the specified
criteria. Useful for calculating grouped totals based on conditional logic.

## Syntax

`SumIf(key_column, criteria, sum_range)`

## Parameters

*key\_column*: The column used to assign values for summation. It groups data and determines
how the results are structured. Required

*criteria*: The value or column used to filter rows for summation. It determines which rows
from the sum\_range are included. Note: This parameter accepts an expression, meaning you can
provide a literal value, a column reference, or the result of another function. Required

*sum\_range*: The column containing the values to be summed. Note: This parameter accepts an
expression, meaning you can provide a literal value, a column reference, or the result of
another function. Required

## Return type

Number

**Notes**:

When using the SumIf function in a filtered transform, it will include filtered values in its
sum. The workaround is to filter your table, create a transform off of it, then build the SumIf
function in the new table.

## Examples

SumIf(Region, Region, Weight): Sums the Weight values for each region and displays them in
a third column.

Assume you have the following table:

| Region | Weight |
| --- | --- |
| Americas | 10 |
| Americas | 20 |
| Europe | 30 |
| Americas | 40 |
| Australia | 50 |
| Australia | 60 |

You want to sum the values for each of the regions and display them in a third column as
shown below:

To do this, you would add the Sum column to the table transform and enter the following
equation in the Value field:

SumIf(Region, Region, Weight)

Entering "Region" for the criteria argument tells the application to evaluate all entries
in the Region column.

| Region | Weight | Sum |
| --- | --- | --- |
| Americas | 10 | 70 |
| Americas | 20 | 70 |
| Europe | 30 | 30 |
| Americas | 40 | 70 |
| Australia | 50 | 110 |
| Australia | 60 | 110 |

`SumIf(Region, "Americas", Weight)`

Adds only the values for the Americas.

Now, suppose you want to add only the values for the Americas. You would use the following
equation:

SumIf(Region, "Americas", Weight)

The result:

| Region | Weight | Sum |
| --- | --- | --- |
| Americas | 10 | 70 |
| Americas | 20 | 70 |
| Europe | 30 | 70 |
| Americas | 40 | 70 |
| Australia | 50 | 70 |
| Australia | 60 | 70 |
