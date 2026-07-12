---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "NumberFormat function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/numberformat.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# NumberFormat function

Formats a numeric value into a label (string) using custom patterns for positive and
negative numbers, durations, or data size formatting. This function is designed for use in
Label-type columns.

## Syntax

`NumberFormat(number, pattern, [options])`

## Parameters

- number: The numeric value to be formatted. Note: This parameter accepts an expression,
  meaning you can provide a literal value, a column reference, or the result of another
  function. Required
- pattern: A string that specifies the format for positive numbers, and optionally for
  negative numbers separated by a semicolon (e.g., "#,###.#;(#,###.#)"). Optional
- options: Optional named arguments that control additional formatting behavior. Supported
  options include:
  - `compact`: Apply shorthand formatting (see Compact Notation Reference
    section below for supported values)
  - `negSymbol`: Use `dash`, `parens`,
    `none`, or `default` for how negative numbers are
    displayed
  - `posColor`, `negColor`: Set font colors using HTML hex
    codes (e.g., `#FF0000`)
  - `posBold`, `negBold`: Apply bold styling
    (`true`, `false`)
  - `posItalic`, `negItalic`: Apply italic styling
    (`true`, `false`)
  - `posUnderline`, `negUnderline`: Apply underline
    styling (`true`, `false`)
  - `posPrefix`, `negPrefix`: Add HTML/text before the
    number
  - `posSuffix`, `negSuffix`: Add HTML/text after the
    number Optional

## Behavior

- Converts a numeric input into a string formatted according to the provided pattern(s).
- Supports rounding, currency symbols, percentages, exponential notation, and byte/bit
  shorthands.
- Can convert durations (in seconds) into formatted strings like '2 hours, 2 minutes'.
- Provides binary formatting for data sizes using codes like XA, XK, etc.
- Applies Half-Up rounding: values ending in 1–4 round down, 5–9 round up.
- When no pattern is provided, numbers are rounded to whole integers and displayed with
  commas.

## Examples

`NumberFormat({Revenue}, "$#,##0.00")`: Formats the {Revenue} column as
currency with two decimals, e.g., "$1,234.56".

`NumberFormat(7322, "s")`: Converts 7322 seconds into a formatted duration
string: "2 hours, 2 minutes, and 2 seconds".

`NumberFormat(922, "MB")`: Formats 922 MB into a human-readable string like
"0.9 GB".

`NumberFormat(Percent, "00%")`: Formats a percentage with two digits, e.g.,
0.42 becomes "42%".

`NumberFormat($_, "#,###.#B", compact="XA")`: Formats a data value using
binary shorthand, e.g., "1.0 GB".

`NumberFormat(-62619000.185, "#,###.#B;(#,###.##)")`: Formats the negative
number -62,619,000.185 using the positive pattern `#,###.#B` and the negative
pattern `(#,###.##)`, resulting in `(62,619,000.19)`.

`NumberFormat({NetIncome}, "$#,##0.00", compact="M", negColor="#FF0000",
posBold=true)`: Formats the {NetIncome} column as currency in millions. Negative
numbers appear in red, and positive numbers are bolded.

## Notes

- Use this function only in Label-type columns or in the format formula of
  metric/reporting new columns.
- Formatting is ignored in numeric columns.
- If neither pattern nor negativePattern is provided, values are rounded to the nearest
  integer with thousands separator.
- When formatting includes HTML, make sure prefix/suffix tags are balanced and valid.

## Compact Notation Reference

The following tables show the supported compact notation values. In the tables, the Code
column shows the values you can put after the compact= optional parameter. The Pattern for
Charts column shows additions you can put at the end of the format pattern.

## Standard Shorthand Notations

The following standard shorthand notations are supported. The symbols displayed for each
standard shorthand format are locale-specific, and are reconfigurable in the project
settings dialog. So, for example, this number format function would use all standard
shorthand notations:

=NumberFormat($\_, "#.#", compact=A)

| Code | Pattern for Charts | Description | Example |
| --- | --- | --- | --- |
| K | {@K} | This will always summarize numbers in terms of "thousands." | 100,000 is displayed as 100K |
| M | {@M} | This will always summarize numbers in terms of "millions." | 10,000,000 is displayed as 10M |
| B | {@B} | This will always summarize numbers in terms of "billions." | 10,000,000,000 is displayed as 10B |
| T | {@T} | This will always summarize numbers in terms of "trillions." | 10,000,000,000,000 is displayed as 10T |
| A | {@A} | This will summarize numbers using all standard notations. For a given number, the highest order-of-magnitude notation possible will be used such that the displayed number is greater than or equal to 1.0. That is, {@A} will display 964,999 as 9.65K not as 0.96M since 0.96 is less than 1.0. If in doubt, this is often the best shorthand format to use. | All of the above examples are true. |

## Binary Shorthand Notations

The following binary shorthand notations are also supported:

When you use binary shorthands, you will most often be summarizing a number of bytes. In
this case, use this as your NumberFormat statement:

=NumberFormat($\_, "#,###.#B", compact="XA")

Similarly, to display this in a chart, enter this as the Chart Number Format:
#,###.#B{@Xa}

| Code | Pattern for Charts | Description | Example |
| --- | --- | --- | --- |
| XK | {@XK} | This will always summarize numbers in terms of "binary thousands" (divide by 1024). | 1025 is displayed as 1k |
| XM | {@XM} | This will always summarize numbers in terms of "binary millions" (divide by 1024^2). | 1048577 is displayed as 1M |
| XG | {@XG} | This will always summarize numbers in terms of "binary billions" (divide by 1024^3). | 1,073,741,825 is displayed as 1G |
| XT | {@XT} | This will always summarize numbers in terms of "binary trillions" (divide by 1024^4). | 1,099,511,627,777 is displayed as 1T |
| XP | {@XP} | This will always summarize numbers in terms of "binary quadrillions" (divide by 1024^5). | 1,125,899,906,842,625 is displayed as 1P |
| XE | {@XE} | This will always summarize numbers in terms of "binary quintillions" (divide by 1024^6). | 1,152,921,504,606,846,977 is displayed as 1e |
| XA | {@XA} | This will summarize numbers using all binary notations. For a given number, the highest order-of-magnitude notation possible will be used such that the displayed number is greater than or equal to 1.0. If in doubt, this is often the best shorthand format to use. | All of the above examples are true. |

## Return type

String
