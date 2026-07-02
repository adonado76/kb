---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Pluralize function"
breadcrumb: []
source_path: "formulas-and-functions/functions/pluralize.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Pluralize function

Applies to: TBM Studio 12.0, 12.1

Converts singular nouns to their plural forms and capitalizes the first letter in each word.

If you want to convert singular nouns to their plural forms but not capitalize the first letter
of each work, use the [Plural
function](plural.htm "(Opens in a new tab or window)").

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Pluralize(noun[,count])`

## Arguments

*noun*

> A singular form of a noun such as "server" and "network." The function handles compound nouns
> such as "data center" and "operating system."

*count*

> The noun will be made plural only if the value of this argument is greater than one. The argument
> can be pulled from any numerical column.

## Return type

String

## Example

![](../../../resources/images/studio_images/studioimages/studio/aug063.png)
