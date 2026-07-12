---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Abs function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Abs function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/abs-function.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Abs function

*Returns the absolute value of a number or expression, removing any negative sign.*

## Syntax

Abs(expression)

## Parameters

expression : A numeric value or a formula that evaluates to a number. Can include variables, constants, or other functions. Optional

## Return type

Number

If the result of the expression is negative, Abs converts it to a positive number. If the result is positive, it remains unchanged.

## Examples

Returns 5

Abs(Sum(Budget) - Sum(Cost))

Returns the absolute difference between total budget and cost

Abs(Price * Quantity)

Returns the absolute value of the product of price and quantity
