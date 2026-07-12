---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Percentile function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Percentile function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/percentile.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Percentile function

*Returns the specified percentile value for a given numeric column. A percentile represents the value below which a given percentage of the data falls.*

Returns a specified percentile for a specified column.

For a given set of numbers, a percentile is the value below which a certain percentage of the numbers fall. For example, for a column containing 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9, the 30th percentile is 2.3, which is the value below which 30 percent of the numbers fall (0,1,2). The decimal point value .3 in the result is derived by taking the value that is 30% of the way between 2 and 3.

## Syntax

Percentile([rollup_operator]column,percentage)

## Arguments

rollup_operator

@, SOURCE, ~, or TARGET. This argument is optional and used only with metrics. See Rollup Operators .

column : The numeric column from which to evaluate the percentile. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

percentage : A numeric value representing the percentile threshold (e.g., 50 for the median, 90 for the 90th percentile). Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

## Behavior

Returns the value below which the specified percentage of data falls. Interpolates between values when the exact percentile position falls between two data points.

## Return type

Number

## Example

The following example returns the 50th percentile for the values contributing to the rollup in the column Servers. If Servers in the source table contains: 500, 600, 700, and 1200, this example returns 650.

=Percentile(Servers,50) : Returns the median (50th percentile) of the values in the {Servers} column.

=Percentile(Sales,90) : Returns the 90th percentile value from the {Sales} column.
