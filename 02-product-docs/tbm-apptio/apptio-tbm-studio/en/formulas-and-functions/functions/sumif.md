---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "SumIf function"
breadcrumb: []
source_path: "formulas-and-functions/functions/sumif.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SumIf function

Applies to: TBM Studio 12.0 and later

The SumIf function adds the values associated with specific entries in a table that match a set
of criteria.

## Where to use

This function can be used in:

- Data sets
- Formula columns in report tables

## Syntax

`SumIf(key_column,criteria,sum_range)`

## Arguments

*key\_column*

> The column containing the entries that the sums will be assigned to.

*criteria*

> The values in the key\_column that will be evaluated.

`sum_range`

> The column containing the values that will be summed.

## Return type

Number

Notes:

When using the SumIf function in a filtered transform, it will include filtered values in its
sum. The workaround is to filter your table, create a transform off of it, then build the SumIf
function in the new table.

## Examples

Assume you have the following table:

![](../../../resources/images/studio_images/studioimages/studio/aug344.png)

You want to sum the values for each of the regions and display them in a third column as shown
below:

![](../../../resources/images/studio_images/studioimages/studio/aug345.png)

To do this, you would add the Sum column to the table transform and enter the following equation
in the Value field:

> `SumIf(Region,Region,Weight)`

Entering "Region" for the criteria argument tells the application to evaluate all entries in the
Region column.

Now, suppose you want to add only the values for the Americas. You would use the following
equation:

> `SumIf(Region,"Americas",Weight)`

The result:

![](../../../resources/images/studio_images/studioimages/studio/aug343.png)
