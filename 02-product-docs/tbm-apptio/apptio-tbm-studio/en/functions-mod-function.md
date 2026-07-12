---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Mod function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Mod function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/mod.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Mod function

*Divides one number by another and returns the remainder, preserving the sign of the dividend (first number).*

## Syntax

Mod(number, divisor)

## Parameters

number : The number to be divided. This is the dividend in the modulo operation. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

divisor : The number by which the dividend is divided. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

## Behavior

- Returns the remainder from dividing the first number by the second.
- The sign of the result always matches the sign of the dividend (the first number), regardless of the sign of the divisor.
- Supports decimal values in both dividend and divisor.

## Return type

Number

## Examples

The sign of the result always matches the sign of the first number, not the sign of the divisor.

| Function | Result |
| --- | --- |
| =Mod(5,3) | 2 — 5 divided by 3 is 1 with a remainder of 2. |
| =Mod(4,2) | 0 — 4 divided evenly by 2. |
| =Mod(7,-3) | 1 - sign of result follows the dividend (7). |
| =Mod(-7,3) | -1— sign of result follows the dividend (-7) |
| =Mod(-7,-3) | -1 — both numbers are negative; result keeps the sign of -7. |
| =Mod(7,2.25) | 0.25 — 7 divided by 2.25 is 3 with a remainder of 0.25. |
