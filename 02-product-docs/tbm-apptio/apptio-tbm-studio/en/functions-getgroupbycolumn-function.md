---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "GetGroupbyColumn function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "GetGroupbyColumn function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/getgroupbycolumn.html"
images:
  - "03-media/apptio-tbm-studio/aug126.png"
  - "03-media/apptio-tbm-studio/aug128.png"
  - "03-media/apptio-tbm-studio/aug358.png"
  - "03-media/apptio-tbm-studio/aug359.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# GetGroupbyColumn function

*Applies to : TBM Studio 12.0 and later*

The GetGroupbyColumn function is used with tables with one or more filtered columns and a grouped column. It returns the name of the column used for grouping. If you have grouped the table by more than one column, the function returns the names of all grouped columns.

## Where to use

- Formula columns in report tables
- Dynamic Text

## Syntax

GetGroupbyColumn()

## Arguments

There are no arguments for this function.

## Return type

String

## Example

Assume you have the table shown in the following image:

You filter the table for "Seattle" in the Data Center column. The result is shown in the following image:

You then group the table by the Service column. The result is shown in the following image:

Now, you add a column with the formula: =GetGroupbyColumn(). The result is shown in the following image:
