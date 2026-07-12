---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Trunc function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Trunc function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/trunc.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Trunc function

*Truncates a real number by removing its fractional part.*

## Syntax

Trunc(value)

## Parameters

value : The numeric value to be truncated. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

## Return type

Number

## Examples

| Example function | Return value |
| --- | --- |
| =Trunc(1.23) | 1 |
| =Trunc(1.985) | 1 |
| Trunc(-2.75) | -2, truncating toward zero. |
| Trunc({Usage Hours}) | Truncates the values in the {Usage Hours} column to their integer part. |
