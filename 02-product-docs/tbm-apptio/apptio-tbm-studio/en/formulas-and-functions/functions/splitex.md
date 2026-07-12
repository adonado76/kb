---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "SplitEx function"
breadcrumb: []
source_path: "formulas-and-functions/functions/splitex.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SplitEx function

Applies to: TBM Studio 12.0 and later

If a column in your data contains multiple values separated by a character such as a comma, and
you want to generate a separate row for each value, use the SplitEx function. For example, assume
you have the table shown below:

![](../../../resources/images/studio_images/studioimages/studio_splitex_state%20and%20city.png)

You want to generate a separate row for each city as shown below:

![](../../../resources/images/studio_images/studioimages/studio_splitex-function_separate-row.png)

Enter the formula shown below for the City column:

![](../../../resources/images/studio_images/studioimages/studio_splitex_formulas.png)

## Where to use

This function can be used in:

- Data sets
- Dynamic text
- Calculated metrics

## Syntax

`Split(column,delimiter)`

## Arguments

*column*

> The column in a table to be split.

*delimiter*

> A character or characters that will be used as the delimiter(s) in the string. You can enter
> multiple delimiter characters. For example: ";>/" represents three delimiters: semicolon, greater
> than, and forward slash. The delimiter(s) must be enclosed in quotes. To represent a blank, use " ."
> If this argument is not specified, it defaults to /- (slash and hyphen).

## Return type

String
