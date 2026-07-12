---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Round function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Round function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/round.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Round function

*Rounds a real number to a specified number of decimal places using the 'round-half-up' algorithm. This means that values ending in .5 are rounded away from zero.*

## Syntax

Round(numeric_expression, digits)

## Arguments

numeric_expression : An expression that evaluates to the number to be rounded. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

digits : An integer expression that specifies the number of decimal places to round to. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

## Behavior

- Rounds the input value to the specified number of decimal places.
- Uses the 'round-half-up' algorithm: values ending in .5 are rounded away from zero.
- If digits is zero, the value is rounded to the nearest whole number.

## Return type

Number

Basic examples :

| Example function | Return value |
| --- | --- |
| =Round(1.23,1) | 1.2 |
| =Round(1.23,0) | 1 |
| =Round(1.57,1) | 1.6 |
| =Round(1.452,0) | 1 |
| Round(-23.5, 0) | -23 since rounding moves away from zero for .5 values. |

## Incorporating a Function

Assume you have the following data set:

| A | B |
| --- | --- |
| 3 | 2 |
| 6 | 11 |
| 5 | 7 |
| 4 | 9 |

You want to divide column A by column B and round off to two decimal places, placing the result in column C. You enter the following in the Value field for column C:

=Round((A/B),2)

The result is the following table:

| A | B | C |
| --- | --- | --- |
| 3 | 2 | 1.5 |
| 6 | 11 | 0.55 |
| 5 | 7 | 0.71 |
| 4 | 9 | 0.44 |
