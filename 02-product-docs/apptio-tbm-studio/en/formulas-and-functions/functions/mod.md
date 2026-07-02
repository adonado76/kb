---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Mod function"
breadcrumb: []
source_path: "formulas-and-functions/functions/mod.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Mod function

Applies to: TBM Studio 12.0 and later

Takes one number and divides it by a second number, and then returns the remainder.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Mod(number,divisor)`

## Arguments

*number*

> The number that will be divided by the divisor.

*divisor*

> The number used to divide the first number.

## Return type

Number

## Examples

The sign of the result always matches the sign of the first number, not the sign of the
divisor.

| Function | Result |
| --- | --- |
| =Mod(5,3) | 2 |
| =Mod(4,2) | 0 |
| =Mod(7,-3) | 1 |
| =Mod(-7,3) | -1 |
| =Mod(-7,-3) | -1 |
| =Mod(7,2.25) | 0.25 |
