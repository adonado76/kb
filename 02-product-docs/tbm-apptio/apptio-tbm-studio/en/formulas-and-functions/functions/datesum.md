---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "DateSum function"
breadcrumb: []
source_path: "formulas-and-functions/functions/datesum.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DateSum function

Applies to: TBM Studio 12.0 and later

Returns the sum of all values in columns with column names that conform to the standard
application date formats.

The DateSum function is useful if you have tables with columns that have numerical data in date
columns as well as other columns. The function sums only the columns with date headers.

## Where to use

This function can be used in data sets.

## Syntax

=`Datesum()`

## Arguments

There are no arguments for this function.

## Return type

A number.

## Example

The table below shows a simple example of the DateSum function. The function adds the 2nd,3rd and
5th columns, which are columns with date as their headers, but ignores the 1st,4th and 5th column.
And difference between Datesum and Total sum can be seen in below example

![](../../../resources/images/studio_images/datesum-1.png)

Example screenshot with syntax

![](../../../resources/images/studio_images/datesum-2.png)

Example Syntax

`= Datesum()`
