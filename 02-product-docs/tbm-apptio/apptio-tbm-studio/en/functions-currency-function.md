---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Currency function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Currency function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/currency.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Currency function

*Formats numeric values as currency strings, adding the appropriate currency symbol based on the locale. By default, negative values are displayed in red.*

## Syntax

Currency(sourceColumn, [pattern], [options])

## Arguments

source column : A numeric column or expression containing the values to be formatted as currency. Enclose column names in curly brackets { }. Required

pattern : An optional string that specifies a custom formatting pattern. Optional

options : Optional named arguments that control additional formatting behavior. Optional

- compact : Apply shorthand formatting (see Compact Notation Reference section below for supported values)
- negSymbol : Use dash , parens , none , or default for how negative numbers are displayed
- minFractPrecision : Minimum number of digits after the decimal point (whole number >= 0)
- maxFractPrecision : Maximum number of digits after the decimal point (whole number >= 0)
- localeprecisionoverride : Override locale defaults for decimal precision ( true , false )
- minIntPrecision : Minimum number of digits before the decimal point (whole number >= 0)
- maxIntPrecision : Maximum number of digits before the decimal point (whole number >= 0)
- thousandSep : Show thousands separator ( true , false , default )
- posColor : Set font color for positive numbers using HTML hex codes (e.g., #FF0000 )
- negColor : Set font color for negative numbers using HTML hex codes (e.g., #FF0000 )
- posBold : Apply bold styling to positive numbers ( true , false , default )
- negBold : Apply bold styling to negative numbers ( true , false , default )
- posItalic : Apply italic styling to positive numbers ( true , false , default )
- negItalic : Apply italic styling to negative numbers ( true , false , default )
- posUnderline : Apply underline styling to positive numbers ( true , false , default )
- negUnderline : Apply underline styling to negative numbers ( true , false , default )
- posPrefix : Add HTML/text before positive numbers
- negPrefix : Add HTML/text before negative numbers
- posSuffix : Add HTML/text after positive numbers
- negSuffix : Add HTML/text after negative numbers

## Behavior

- Adds a currency symbol appropriate to the current locale to the numeric value.
- Formats the number according to the specified pattern if provided.
- Applies optional styling options such as color, bold, italics, and compact number formats.
- Displays negative values in red by default unless overridden with options.

## Examples

Currency({Cost}): Formats the values in the {Cost} column as currency based on the locale, showing negative numbers in red.

Currency({Revenue}, "#,##0.00 ¤"): Formats {Revenue} with a custom pattern, ensuring two decimal places and a currency symbol.

Currency({Profit}, "#,##0", compact="K", posColor="green", negColor="red"): Formats {Profit} using compact notation (e.g., 1,000 → 1K), with positive numbers shown in green and negative numbers in red.

- Best practice recommends converting all financial values to a common currency before using them in drivers or reporting.
- The 'pattern' and 'options' parameters allow fine-tuning of the output for different styling and reporting needs.
- Using 'compact=A' automatically selects the best unit for large numbers (e.g., K, M, B, T).
- Color and font style options help customize the appearance of positive and negative numbers independently.

## Compact Notation Reference

The following standard shorthand notations are supported. In this table, the Code column is the values you can put after the compact= optional parameter. The Pattern for Charts column shows additions you can put at the end of the format pattern to format a chart:

| Code | Pattern for charts | Description | Example |
| --- | --- | --- | --- |
| K | {@K} | This will always summarize numbers in terms of "thousands" | 100,000 is displayed as 100K |
| M | {@M} | This will always summarize numbers in terms of "millions" | 10,000,000 is displayed as 10M |
| B | {@B} | This will always summarize numbers in terms of "billions" | 10,000,000,000 is displayed as 10B |
| T | {@T} | This will always summarize numbers in terms of "trillions" | 10,000,000,000,000 is displayed as 10T |
| A | {@A} | This will summarize numbers using all standard notations. For a given number the highest order-of-magnitude notation possible will be used such that the displayed number is greater than or equal to 1.0. IE, {@A} will display 964,999 as 9.65K not as 0.96M since 0.96 is less than 1.0. If uncertain, this is often the best shorthand format to use. | All of the above examples are true. |
