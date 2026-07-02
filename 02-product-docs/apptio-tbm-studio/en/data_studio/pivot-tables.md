---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Pivot data"
breadcrumb: []
source_path: "data_studio/pivot-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Pivot data

Applies to: TBM Studio 12.0 and later

Line-item data such as a general ledger, trouble ticket information, or CPU utilization can be
summarized using the Pivot feature. For example, you might want to summarize the data by data
center, application, or server type.

To illustrate the power of pivoting data, assume you have a trouble ticket table like the
following:

![](../../resources/images/studio_images/studioimages/studio/stu204.png)

You would like to total the trouble ticket minutes per application by location, where the
applications are the rows in the table, the locations are the columns, and the cells display the
total minutes. When you pivot the table, the application creates a table that looks like the
following:

![](../../resources/images/studio_images/studioimages/studio/stu205.png)

## Pivot a table

1. Check out the table.
2. Add a Pivot step to the transform pipeline.
3. Complete the following:
   - Pivot Row: Select the column in the table that will be used for the values in the first
     column of the pivot table. In the example above, the Application column was selected.
   - Pivot Column: Select the column in the table that will be used for the column headers in
     the columns following the first column. In the example above, the Geography column was
     selected.
   - Pivot Value: Select the column whose values will be added together and displayed in the
     cells of the pivot table. In the example above, the Duration column (not visible) was
     selected.
4. To perform the pivot, click OK.

## Create multiple pivots

If you have data that would benefit from multiple pivots, you can create a new data table for
each pivot. To create a new table, right-click in the Output step in the transform pipeline
and click Create New Table from this Step.
