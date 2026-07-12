---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Pluralize function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Pluralize function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/pluralize.html"
images:
  - "03-media/apptio-tbm-studio/aug063.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Pluralize function

*Applies to : TBM Studio 12.0, 12.1*

Converts singular nouns to their plural forms and capitalizes the first letter in each word.

If you want to convert singular nouns to their plural forms but not capitalize the first letter of each work, use the Plural function .

## Where to use

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

Pluralize(noun[,count])

## Arguments

noun

A singular form of a noun such as "server" and "network." The function handles compound nouns such as "data center" and "operating system."

count

The noun will be made plural only if the value of this argument is greater than one. The argument can be pulled from any numerical column.

## Return type

String

## Example
