---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Min function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Min function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/min.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Min function

*Compares two numeric expressions and returns the lesser value.*

## Syntax

Min(numeric_expression1, numeric_expression2)

## Parameters

numeric_expression 1 and 2

The numeric value or expression to compare. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required. You must enter two, and only two, numeric expressions.

## Behavior

- Evaluates both numeric expressions and returns the smaller of the two.
- Supports nested expressions or functions as input parameters.
- Returns the exact value of the lesser expression without modification.

## Return type

Number

## Example

=Min(42*Hours,Min(3,7)) : Returns the lesser of 42 times the value in {Hours} or 3 (since Min(3, 7) evaluates to 3).

Min(10, 20) : Returns 10 because it is the lesser of the two numbers.

Min({Planned Hours}, {Actual Hours}) : Returns the smaller value between the {Planned Hours} and {Actual Hours} columns for each row.

- Useful for setting lower limits or determining minimum values between two metrics.
- Both parameters must be numeric or resolve to numeric expressions.
- If you want to find the minimum value in a column, use the Small function.
