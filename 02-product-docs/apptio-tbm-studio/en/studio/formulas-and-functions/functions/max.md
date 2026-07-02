---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Max function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/max.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Max function

Compares two expressions and returns the greater value.

## Syntax

`Max(numeric_expression1, numeric_expression2)`

## Arguments

*numeric\_expression*: numeric\_expression1: The first numeric value or expression to
compare. Note: This parameter accepts an expression, meaning you can provide a literal
value, a column reference, or the result of another function. Required

*numeric\_expression2*: The second numeric value or expression to compare. Note: This
parameter accepts an expression, meaning you can provide a literal value, a column
reference, or the result of another function. Required

## Behavior

- Evaluates both numeric expressions and returns the larger of the two.
- Supports nested expressions or functions as input parameters.
- Returns the exact value of the greater expression without modification.

## Return type

Number

## Example

The following example contains complex arguments in a Max function. The first argument is 42
times the value in Hours. The second argument is the larger of 3 and 7, which is 7. So, if Hours is
3, the first argument evaluates to 126, which is greater than 7, so the function returns 126.

`=Max(42*{Hours},Max(3,7))`

`Max(10, 20)`: Returns 20 because it is the greater of the two numbers.

`Max({Planned Hours}, {Actual Hours})`: Returns the larger value between the
{Planned Hours} and {Actual Hours} columns for each row.

Note:

- Useful for setting upper limits or determining peak values between two metrics.
- Both parameters must be numeric or resolve to numeric expressions.
- If you want to find the maximum value in a column, use the Large function.
