---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Currency function"
breadcrumb: []
source_path: "formulas-and-functions/functions/currency.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Currency function

Applies to: TBM Studio 12.0 and later

Use the Currency function to format numbers as currency. This function adds the appropriate
currency sign to the beginning of the return value based on the locale. By default, Currency
displays negative return values in red.

## Where to use

The Currency function can be used in the following:

- Formulas step of Table Transform Pipeline (Label type columns only) [not recommended]
- Calculated metrics (in the format formula only)
- Formula columns in report tables (in the format formula only)
- Dynamic text

Note: When using the Currency function in a table, the column Type field must be set to
Label to accommodate the currency symbol ($, €, £) added to the number (the position of the
currency symbol is determined by the user's locale). If you are going to perform mathematical
calculations on the data, set the column type to Number, perform the calculations on the
column, create a new column of type Label based on the original column, and then use the
Currency function on the new column. Use the new column for displaying the data in reports.

As a best practice, the Currency function should be used only in calculated metrics and reporting
new columns format formulas.

If you are using the Currency function in a formula step of a table, or in a value formula, be
sure it is necessary.

## Rounding

All numbers are rounded using the Half-Up rounding algorithm. All numbers ending in 1-4 are
rounded down. All numbers ending in 5-9 are rounded up. See the following examples.

## Currencies that do not use decimals

If a currency does not use decimals, for example the Japanese Yen or South Korean Won, currencies
will, by default, be displayed without decimals even if a custom format has been created that
specifies decimals. The default behavior can be overridden using the *localeprecisionoverride*
argument described in the Arguments section below.

Currencies that do *not* use decimals are as follows:

- "ADP", // Andoran Peseta
- "AFA", // Afghani Afghani
- "BEF", // Belgian franc (obsolete)
- "BIF", // Burundi franc
- "BYB", // Belarusian New Ruble (1994-1999)
- "BYR", // Belorussian rubel (new)
- "CLF", // Chilean Unit of Account (UF)
- "CLP", // Chilean peso
- "COP", // Colombian peso
- "DJF", // Djibouti franc
- "ECS", // Ecuadorian sucre (not Java currency, as USD is the official currency of Ecuador)
- "ESP", // Spanish peseta (obsolete)
- "GNF", // Guinea franc
- "GRD", // Greek drachma (obsolete)
- "HUF", // Hungarian forint
- "IDR", // Indonesian rupiah
- "ISK", // Icelandic Króna (obsolete)
- "ITL", // Italian Lira (obsolete)
- "JPY", // Japanese yen
- "KMF", // Comoros franc
- "KRW", // South Korean won
- "LAK", // Laos new kip
- "LUF", // Luxembourgian Franc (obsolete)
- "MGF", // Madagascan franc
- "MZM", // Mozambique metical
- "PTE", // Portuguese Escudo (obsolete)
- "PYG", // Paraguay guarani
- "RWF", // Rwanda franc
- "TJR", // Tadzhikistani rubel (not Java currency)
- "TMM", // Turkmenistani manat
- "TPE", // Timor escudo
- "TRL", // Turkish lira (obsolete - new Turkish Lira is TRY)
- "TWD", // New Taiwan dollar
- "UGX", // Uganda shilling
- "UYI", // added for JDK 1.8\_77
- "VND", // Vietnamese dong
- "VUV", // Vanuata vatu
- "XAF", // CFA Franc BEAC
- "XOF", // CFA Franc BCEAO
- "XPF", // CFP Franc

## Multiple currencies

If you are working with multiple currencies, best practice recommends converting all cost figures
to a common currency before using them as drivers for objects in a model or for reporting. Perform
the conversion using a transform column on the data set.

## Syntax

> ```
> Currency({column}[,negSymbol,minFractPrecision,maxFractPrecision,minIntPrecision,maxIntPrecision,localeprecisionoverride,thousandSep,posColor,negColor,posBold,
> negBold,posItalics,negItalics,posUnderline,negUnderline,posPrefix,negPrefix,
> posSuffix,negSuffix])
> ```

## Arguments

*{*
*column*
*}*

> A column containing numeric values to be formatted. In the application, it is a best practice to
> enclose all column names in curly brackets { }.

*compact*

> Specifies how to shorten large numbers. The default is not to apply any shorthand notation.

## Values

The following standard shorthand notations are supported. In this table, the Code column is the
values you can put after the compact= optional parameter. The Pattern for Charts column shows
additions you can put at the end of the format pattern to format a chart:

| Code | Pattern for charts | Description | Example |
| --- | --- | --- | --- |
| K | {@K} | This will always summarize numbers in terms of "thousands" | 100,000 is displayed as 100K |
| M | {@M} | This will always summarize numbers in terms of "millions" | 10,000,000 is displayed as 10M |
| B | {@B} | This will always summarize numbers in terms of "billions" | 10,000,000,000 is displayed as 10B |
| T | {@T} | This will always summarize numbers in terms of "trillions" | 10,000,000,000,000 is displayed as 10T |
| A | {@A} | This will summarize numbers using all standard notations. For a given number the highest order-of-magnitude notation possible will be used such that the displayed number is greater than or equal to 1.0. IE, {@A} will display 964,999 as 9.65K not as 0.96M since 0.96 is less than 1.0.  NOTE: If uncertain, this is often the best shorthand format to use. | All of the above examples are true. |

The symbols displayed for each standard shorthand format are locale-specific and are
reconfigurable in the project settings dialog.

The binary shorthand notations documented in the NumberFormat function are also supported,
however, using them with the Currency function is not recommended.

*negSymbol*

> Specifies the symbol to use for negative numbers.

> Values: dash,parens,none,default
>
> The default is to use the format specified by the locale.

*minFractPrecision*

> Specifies the minimum number of digits to display after the decimal point.
>
> Format: a whole number => 0

*maxFractPrecision*

> Specifies the maximum number of digits to display after the decimal point.
>
> Format: a whole number => 0

*localeprecisionoverride*

> Overrides the default behavior of showing currencies that do not use decimals as numbers without
> decimals even if a custom format has been created using the minFractPrecision and maxFractPrecision
> arguments (described above).
>
> Values: true, false.
>
> If not specified, the default behavior will be applied.

*minIntPrecision*

> Specifies the minimum number of digits to show before the decimal point.
>
> Format: a whole number => 0

*maxIntPrecision*

> Specifies the maximum number of digits to show before the decimal point.
>
> Format: a whole number => 0

*thousandSep*

> Specifies if the thousands separator should appear.
>
> Values: true, false, default
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

> Applies a bold font (html <b>) when the number is positive.
>
> Values: true, false, negative

*negBold*

> Applies a bold font (html <b>) when the number is negative.
>
> Values: true, false, default
>
> Default will use the format specified by the locale.

*posItalic*

> Applies an italic font (html <i>) when the number is positive.
>
> Values: true, false, default
>
> The default is to use the format specified by the locale.

*negItalic*

> Applies an italic font (html <i>) when the number is negative.
>
> Values: true, false, default
>
> The default is to use the format specified by the locale.

*posUnderline*

> Applies an underline to the font (html <u>) when the number is positive.
>
> Value: true, false, default
>
> Default will use the format specified by the locale.

*negUnderline*

> Applies an underline to the font (html <u>) when the number is negative.
>
> Value: true, false, default
>
> The default is to use the format specified by the locale.

*posPrefix*

> Applies custom html formatting before the number when the number is positive. This parameter is
> used in conjunction with the posSuffix parameter.
>
> Value: custom html code

*negPrefix*

> Applies custom html formatting before the number when the number is negative. This parameter is
> used in conjunction with the negSuffix parameter.
>
> Value: custom html code

*posSuffix*

> Applies custom html formatting after the number when the number is positive. This parameter is
> used in conjunction with the posPrefix parameter.
>
> Value: custom html code

*negSuffix*

> Applies custom html formatting after the number when the number is negative. This parameter is
> used in conjunction with the negPrefix parameter.
>
> Value: custom html code

> You can hardcode the parameters as parameter=value or as an expression where the expression
> resolves to the format "parameter=value."

## Formats supported

In reports, the Apptio application supports currency formats for the following countries. The
format is determined by the locale selected for the project.

- Australia
- Austria
- Belgium, Dutch
- Belgium, French
- Czech Republic
- Denmark
- Finland
- France
- Germany
- Ireland, English & Irish
- Italy
- Luxembourg, French
- Luxembourg, German
- Netherlands
- Norway, Bokmal
- Norway, Nynorsk
- Peru
- Portugal
- Slovakia
- Spain, Catalan
- Spain, Spanish
- Sweden
- Switzerland, French
- Switzerland, German
- Switzerland, Italian
- United Kingdom
- United States
