---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "GetGroupbyColumn function"
breadcrumb: []
source_path: "formulas-and-functions/functions/getgroupbycolumn.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GetGroupbyColumn function

Applies to: TBM Studio 12.0 and later

The GetGroupbyColumn function is used with tables with one or more filtered columns and a grouped
column. It returns the name of the column used for grouping. If you have grouped the table by more
than one column, the function returns the names of all grouped columns.

## Where to use

This function can be used in:

- Formula columns in report tables
- Dynamic Text

## Syntax

`GetGroupbyColumn()`

## Arguments

There are no arguments for this function.

## Return type

String

## Example

Assume you have the table shown in the following image:

![](../../../resources/images/studio_images/studioimages/studio/aug126.png)

You filter the table for "Seattle" in the Data Center column. The result is shown in the
following image:

![](../../../resources/images/studio_images/studioimages/studio/aug128.png)

You then group the table by the Service column. The result is shown in the following
image:

![](../../../resources/images/studio_images/studioimages/studio/aug358.png)

Now, you add a column with the formula: =GetGroupbyColumn(). The result is shown in the following
image:

![](../../../resources/images/studio_images/studioimages/studio/aug359.png)
