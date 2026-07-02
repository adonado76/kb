---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "NumberFormat function"
breadcrumb: []
source_path: "formulas-and-functions/functions/numberformat.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# NumberFormat function

Applies to: TBM Studio 12.0, 12.1

The NumberFormat function converts numbers in Label columns to a specified format. The
value for the specified column is resolved and formatted before it is applied to the rest of the
formula. This function can be used in Label type columns only.

TIP: To format numbers as currency, use the [Currency](currency.htm "(Opens in a new tab or window)") function.

## Where to use

The NumberFormat function can be used in:

- The Formulas step of the Table Transform Pipeline (Label-type columns only) [not
  recommended]
- Calculated metrics (in the format formula only)
- Formula columns in report tables (in the format formula only)
- Dynamic text

Notes

- This function can be used in Label type columns in data sets only.
- The function cannot be used in Numeric columns because all formatting will be ignored.
- As a best practice, use the NumberFormat function only with calculated metrics and reporting new
  columns format formulas. If you are using it in a table's formula step, or in a value formula, be
  sure it is necessary.

## Syntax

> ```
> NumberFormat({column}[,"pattern[;negative_pattern]"][,negSymbol,minFractPrecision,maxFractPrecision,minIntPrecision,maxIntPrecision,localeprecisionoverride,thousandSep,posColor,negColor,posBold,
>           negBold,posItalics,negItalics,posUnderline,negUnderline,posPrefix,negPrefix,
>           posSuffix,negSuffix])
> ```

## Arguments

*{*
*column*
*}*

> A column containing numerical values to be formatted. In the application, it is best practice to
> enclose all column names in curly brackets { }.

*"*
*pattern*
*"*

> A string that specifies the format for positive numbers.
>
> The syntax for the *pattern* and *negative\_pattern* arguments is the same:
>
> `"[prefix]integer[.decimal][suffix][shorthand]"`

Note: The entire pattern must be enclosed in double quotes ( " " ).

*"negative\_pattern"*

> A string that specifies the format for negative numbers. If you specify the *pattern*
> argument but do not specify the *negative-pattern* argument, the *pattern* argument will
> be used for both positive and negative numbers.

> The syntax for the *pattern* and *negative\_pattern* arguments is the same:
>
> `"[prefix]integer[.decimal][suffix][shorthand]"`

Note: The entire pattern must be enclosed in double quotes ( " " ).

*prefix*

> Can contain characters that typically come before numerical values, such as a dollar sign ( $ )
> or other currency symbol.
>
> The *prefix* can also include any valid HTML formatting commands (for example, <font
> color='blue'>), provided the suffix supplies the corresponding closing commands (for example,
> </font>). The *prefix* can contain any characters in the Unicode set from number 0000 to
> FFFD, inclusive. Special characters must be enclosed in single quotes. For more information, see
> [Special Characters in prefix and suffix Arguments](#NumberFormatfunction__SpecialChar).

*integer*

> Specifies the format for the integer portion of a real number using the symbols in the following
> table.
>
> | Symbol | Description |
> | --- | --- |
> | 0 | A digit. Use this if you want currency displayed with value to the right of the decimal place. For example, $756.00 will be displayed as $756.00. |
> | # | A digit. If the digit is zero, it is not displayed. For example, $756.00 will be displayed as $756. |
> | , | Placeholder for grouping separator. |

*decimal*

> Specifies the format for the decimal portion of a real number, using the symbols in the following
> table.
>
> | Symbol | Description |
> | --- | --- |
> | 0 | A digit. Use this if you want currency displayed with value to the right of the decimal place. For example, $756.00 will be displayed as $756.00. |
> | # | A digit. If the digit is zero, it is not displayed. For example, $756.00 will be displayed as $756. |

*suffix*

> Can contain character strings that might follow a numeric value, such as net or gross. Can also
> contain closing HTML commands corresponding to HTML formatting commands in the prefix (for example,
> </font>) The suffix can contain any characters in the unicode set from number 0000 to FFFD,
> inclusive. Special characters must be enclosed in single quotes.
>
> | Symbol | Description |
> | --- | --- |
> | E | Separates mantissa and exponent for exponential formats |
> | % | Multiply by 100 and show as percentage |
> | %o | (Per mille sign, unicode \u2030)Multiply by 1000 and show as per mille |
> | %o | (Per mille sign, unicode \u2030)Multiply by 1000 and show as per mille |

> Special characters in prefix and suffix arguments
>
> The following special characters have symbolic meanings for the NumberFormat function, as
> described elsewhere in this topic. To have these special characters appear in the *prefix* or
> *suffix* arguments, you must enclose them in single quotes ( ' ).
>
> | Symbol | Name |
> | --- | --- |
> | 0 | Zero |
> | # | Pound sign |
> | , | Comma |
> | . | Period |
> | - | Minus sign |
> | ; | Semicolon |
> | E | E |
> | % | Percent sign |
> | %o | (Per mille sign, Unicode \u2030) |
> | ' | Single quote.  Used to quote special characters in a prefix or suffix, for example, "'#'#" formats 123 to "#123." To create a single quote itself, use two in a row: "# o''clock."  NOTE: Unlike the other special characters in this table, a literal single quote requires only a single quote before (as in ''). It is not necessary to enclose it in single quotes. |

## Named Arguments

After the pattern argument, one or more name=<value> pairs can be specified for numerous
operations. Following are the names, what they do, and the allowed values.

*compact [applies to release 12.3.4+]*

Specifies that large numbers are displayed using a shorthand notation. While not recommended,
shorthand notations can also be applied within the pattern argument. This should only be used with
charts. If you want a chart to use all shorthands, paste the following into its pattern:

> `"#.#{@A}"`

The default is to not apply any shorthand notation.

## Values

The following standard shorthand notations are supported. In this table, the Code column shows
the values you can put after the compact= optional parameter. The Pattern for Charts column shows
additions you can put at the end of the format pattern:

| Code | Pattern for Charts | Description | Example |
| --- | --- | --- | --- |
| K | {@K} | This will always summarize numbers in terms of "thousands." | 100,000 is displayed as 100K |
| M | {@M} | This will always summarize numbers in terms of "millions." | 10,000,000 is displayed as 10M |
| B | {@B} | This will always summarize numbers in terms of "billions." | 10,000,000,000 is displayed as 10B |
| T | {@T} | This will always summarize numbers in terms of "trillions." | 10,000,000,000,000 is displayed as 10T |
| A | {@A} | This will summarize numbers using all standard notations. For a given number, the highest order-of-magnitude notation possible will be used such that the displayed number is greater than or equal to 1.0. That is, {@A} will display 964,999 as 9.65K not as 0.96M since 0.96 is less than 1.0.  NOTE: If in doubt, this is often the best shorthand format to use. | All of the above examples are true. |

The symbols displayed for each standard shorthand format are locale-specific, and are
reconfigurable in the project settings dialog. So, for example, this number format function would
use all standard shorthand notations:

> `=NumberFormat($_,"#.#",compact=A)`

The following binary shorthand notations are also supported:

| Code | Pattern for Charts | Description | Example |
| --- | --- | --- | --- |
| XK | {@XK} | This will always summarize numbers in terms of "binary thousands" (divide by 1024). | 1025 is displayed as 1k |
| XM | {@XM} | This will always summarize numbers in terms of "binary millions" (divide by 1024^2). | 1048577 is displayed as 1M |
| XG | {@XG} | This will always summarize numbers in terms of "binary billions" (divide by 1024^3). | 1,073,741,825 is displayed as 1G |
| XT | {@XT} | This will always summarize numbers in terms of "binary trillions' (divide by 1024^4). | 1,099,511,627,777 is displayed as 1T |
| XP | {@XP} | This will always summarize numbers in terms of "binary quadrillions" (divide by 1024^5). | 1,125,899,906,842,625 is displayed as 1P |
| XE | {@XE} | This will always summarize numbers in terms of "binary quintillions" (divide by 1024^6). | 1,152,921,504,606,846,977 is displayed as 1e |
| XA | {@XA} | This will summarize numbers using all binary notations. For a given number, the highest order-of-magnitude notation possible will be used such that the displayed number is greater than or equal to 1.0.  NOTE: If in doubt, this is often the best shorthand format to use. | All of the above examples are true. |

When you use binary shorthands, you will most often be summarizing a number of bytes. In this
case, use this as your Numberformat statement:

> `=NumberFormat($_,"#,###.#B",compact="XA")`

Similarly, to display this in a chart, enter this as the Chart Number Format:

> `#,###.#B{@Xa}`

*negSymbol*

> Specifies the symbol to use for negative numbers.
>
> Values: dash, parens, none, default
>
> The default is to use the format specified by the locale.

*posColor*

> Specifies the color for positive numbers.
>
> Values: Any valid HTML color code. For example: #CCAABB.

*negColor*

> Specifies the color for negative numbers.
>
> Values: Any valid HTML color code. For example: #CCAABB.

*posBold*

> Applies a bold font (HTML <b>) when the number is positive.
>
> Values: true, false, negative

*negBold*

> Applies a bold font (HTML <b>) when the number is negative.
>
> Values: true, false, default
>
> The default is to use the format specified by the locale.

*posItalic*

> Applies an italic font (HTML <i>) when the number is positive.
>
> Values: true, false, default
>
> The default is to use the format specified by the locale.

*negItalic*

> Applies an italic font (HTML <i>) when the number is negative.
>
> Values: true, false, default
>
> The default is to use the format specified by the locale.

*posUnderline*

> Applies an underline to the font (HTML <u>) when the number is positive.
>
> Value: true, false, default
>
> The default is to use the format specified by the locale.

*negUnderline*

> Applies an underline to the font (HTML <u>) when the number is negative.
>
> Value: true, false, default
>
> The default is to use the format specified by the locale.

*posPrefix*

> Applies custom HTML formatting before the number when the number is positive. This parameter is
> used in conjunction with the posSuffix parameter.
>
> Value: custom HTML code

*negPrefix*

> Applies custom HTML formatting before the number when the number is negative. This parameter is
> used in conjunction with the negSuffixparameter.
>
> Value: custom HTML code

*posSuffix*

> Applies custom HTML formatting after the number when the number is positive. This parameter is
> used in conjunction with the posPrefix parameter.
>
> Value: custom HTML code

*negSuffix*

> Applies custom HTML formatting after the number when the number is negative. This parameter is
> used in conjunction with the negPrefix parameter.
>
> Value: custom HTML code

## Return type

String

## Remarks

If neither "pattern" nor "negative\_pattern" are supplied, the function rounds the value to the
nearest integer, adds a thousand separator comma, and adds a negative sign prefix for negative
numbers. Numbers that are => 0.5 are rounded up. Numbers that are < 0.5 are rounded down.

This function outputs a formatted number, which is a label. Therefore, use this function only in
the format formula of numeric columns (metrics and reporting new columns), and in table transform
columns of type label.

## Negative numbers

If a Currency function (or a NumberFormat function with currency marker) does not provide a
custom negative format (that is, a format string with positive and negative formats separated by a
semicolon), negative numbers will be displayed in a red font and use the same precision and
separator treatment as the positive numbers. However, beginning with v.11.8.1, if you specify a
custom negative format, it will take precedence. Use a custom negative format when you want to
override the default red font format, but you want the number format to conform to the locale.

## Time durations

You can also use the NumberFormat function to convert seconds into hours, minutes, and seconds.
For example, the following would return the value "2 hours, 2 minutes, and 2 seconds."

> `=NumberFormat(7322,"s")`

The following would return the value "2 hours."

> `=NumberFormat(7322,"s1")`

The following would return the value "2 hours and 2 minutes."

> `=NumberFormat(7322,"s2")`

## Displaying bytes

You can also use the NumberFormat function to convert and format bytes as KB, MB, GB, and TB.
This can be used with custom number formats as specified in the shorthand section. However, we also
have a shorthand that applies all shorthands, and supports deltas.

For example, the following would return the value "0.9 GB":

> `=NumberFormat(922,"MB")`

The following would return the value +0.9 GB:

> `=NumberFormat(922,"+MB")`

The following would return the value -0.9 GB:

> `=NumberFormat(-922,"+MB")`

## Precision

You can control how NumberFormat rounds numbers. The general syntax is as follows:

> `NumberFormat(number,"%%")`

If the number value is less than 9.8% or between 99% and 100% exclusive, then the number is
formatted with up to two digits of precision past the decimal. Otherwise, the number is formatted
with 0 digits past the decimal.

See the following examples:

| Formula | Value | Result |
| --- | --- | --- |
| `=NumberFormat(Number,"#.###")` | 23.536798 | 23.537 |
| `=NumberFormat(Percent,"#%")` | 0.42 | 42% |
| 4 | 400% |
| `=NumberFormat(Percent,"#") + "%"` | 0.42 | 0.42% |
| 4 | 4% |
| `=NumberFormat(Percent,"00%")` | 0.42 | 42% |
| 0.04 | 04% |

## Rounding

All numbers are rounded using the Half-Up rounding algorithm. All numbers ending in 1-4 are
rounded down. All numbers ending in 5-9 are rounded up.

See the following examples:

| Number | Rounded number |
| --- | --- |
| 1.4 | 1 |
| 1.5 | 2 |
| 1.47 | 1.5 |
| 6.12 | 6.1 |

See also:

- [Currency function](currency.htm "(Opens in a new tab or window)")
- [ApptioOne Precision.](../../getting%20started%20with%20tbm%20studio/apptio-one-precision.htm "(Opens in a new tab or window)")
