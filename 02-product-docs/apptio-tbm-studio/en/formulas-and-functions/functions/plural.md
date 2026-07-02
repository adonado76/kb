---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Plural function"
breadcrumb: []
source_path: "formulas-and-functions/functions/plural.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Plural function

Applies to: TBM Studio 12.2 and later

Converts singular nouns to their plural forms.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Plural(noun[,count])`

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

![](../../../resources/images/studio_images/studioimages/studio/stu689.png)
