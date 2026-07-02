---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "SORT"
breadcrumb: []
source_path: "studio/data_studio/sort.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SORT

Sorts a table on one or more specified columns in the table. You can sort a table using
the Ribbon. The !SORT function can be applied using one, two, or more columns in a
table.

## Syntax

`!SORT[Column1|asc or desc,Column2|asc or desc]`

## Arguments

Column 1
:   The name of the first column that will be used to sort the table.
:   asc or desc
:   asc = ascending
:   desc = descending

Column2
:   The name of the second column that will be used to sort the table.

## Example

Assume you have the following table.

![Example](../../resources/images/it%20planning_images/sort-1.png)

You want to sort the table by Service, then Sub-Service. You modify the data path as shown
below.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
.Summary/
!SORT[{Service}|asc,{SubService}|asc]
```

The result is shown below.

![result ](../../resources/images/it%20planning_images/sort-2.png)

## Ribbon

You can sort a table using the **Ribbon**:

1. Select the table you want to sort
2. Select the **Sort** icon from the **Data** tab on the
   **Ribbon**.
3. Complete the fields and click **Sort**.

For more information on sorting a table from the **Ribbon**, see Sorting rows
in a table in the Apptio Studio Users Guide.

**Parent topic:** [Editable tables: Accommodating user input](../../studio/data_studio/editabletables.html "Applies to: TBM Studio 12.6 and later")
