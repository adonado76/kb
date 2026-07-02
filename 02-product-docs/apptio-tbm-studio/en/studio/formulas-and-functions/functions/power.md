---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Power function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/power.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Power function

Raises a specified base number to the power of a specified exponent, performing
exponential calculation.

## Syntax

`Power(base, exponent)`

## Parameters

*base*: The numeric base value to be raised to a power. Note: This parameter accepts an
expression, meaning you can provide a literal value, a column reference, or the result of
another function. Required

*exponent*: The numeric exponent to which the base will be raised. Note: This parameter
accepts an expression, meaning you can provide a literal value, a column reference, or the
result of another function. Required

## Behavior

- Raises the base to the power of the exponent (i.e., base^exponent).
- Handles both positive and negative exponents, including fractional values.
- Returns a decimal (double) result regardless of whether inputs are integers or floats.

## Return type

Number

## Example

The following example raises 2 to the 3rd power, which returns 8.:
`=Power(2,3)`

`Power(5, 0)`: Returns 1 because any number raised to the 0th power is
1.

`Power({CPU Count}, 2)`: Squares the value in the {CPU Count} column.

Note: A base of 0 with a negative exponent is undefined and will result in an error.
