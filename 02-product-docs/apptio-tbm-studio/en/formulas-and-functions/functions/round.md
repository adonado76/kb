---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Round function"
breadcrumb: []
source_path: "formulas-and-functions/functions/round.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Round function

Applies to: TBM Studio 12.0 and later

Rounds a real number to the specified number of decimal places. The "round-half-up" algorithm is
used. If you are displaying whole numbers, Apptio uses the "round-half-up" algorithm. This means
23.5 rounds to 24, and -23.5 rounds to -23. In effect, the rounding always moves to the right on a
number line.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Round(numeric_expression,digits)`

## Arguments

*numeric\_expression*

> An expression that evaluates to the number to be rounded.

*digits*

> An integer specifying the number of digits to round to.

## Return type

Number

Basic examples:

| Example function | Return value |
| --- | --- |
| =Round(1.23,1) | 1.2 |
| =Round(1.23,0) | 1 |
| =Round(1.57,1) | 1.6 |
| =Round(1.57,0) | 2 |

## Incorporating a Function

Assume you have the following data set:

| A | B |
| --- | --- |
| 3 | 2 |
| 6 | 11 |
| 5 | 7 |
| 4 | 9 |

You want to divide column A by column B and round off to two decimal places, placing the result
in column C. You enter the following in the Value field for column C:

> `=Round((A/B),2)`

The result is the following table:

| A | B | C |
| --- | --- | --- |
| 3 | 2 | 1.5 |
| 6 | 11 | 0.55 |
| 5 | 7 | 0.71 |
| 4 | 9 | 0.44 |

See also:

- [Trunc](trunc.htm "(Opens in a new tab or window)")
- [ApptioOne Precision](../../getting%20started%20with%20tbm%20studio/apptio-one-precision.htm "(Opens in a new tab or window)")
