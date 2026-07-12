---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "Overview"
breadcrumb:
  - "Working with Tables"
  - "Overview"
source_path: "SSVWBC/cloud-financial-planning/admin/working-with-tables.html"
images:
  - "03-media/apptio-financial-planning/cfp-working-with-tables.png"
  - "03-media/apptio-financial-planning/cfp-column-menu.png"
  - "03-media/apptio-financial-planning/cfp-collumn-grouping-tool.png"
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# Overview

*All tables in Cloudability Financial Planning utilize the same underlying table control for us to provide a consistent user experience when working with tabular data. Note that certain tables may not expose every table interaction and operation.*

The following table describes the index of numbers in the previous screen:

| # | Name | Description |
| --- | --- | --- |
| 1 | (Row) Group | You can drag/ drop a dimension (non-metric) column into the (row) Group bar to summarize rows by the dimension. Grouped dimensions are displayed in a single column pinned to the left of the table, Rows containing the same dimension value will be summarized into a group row that can be expanded to show the individual rows comprising the group. Multiple dimensions can be grouped and are displayed as nested groupings. |
| 2 | Row detail dimensions | You can show/ hide dimensions using the Columns menu or the column tool in the side bar. |
| 3 | Column grouping | Similar to row groups, the column grouping feature apply to columns. Column groups apply only to time-series metrics. Clicking on the chevron will collapse or expand the column group to show in the individual periods being summarized. Use Grouping in the side bar to show/ hide period groups. |
| 4 | Summary row | You can choose to group by a dimension in order to see summary rows. Click to expand to see row details. |
| 5 | Column menu | You can use this for common column actions like autosizing, quick grouping, and others like setting a column filter and select additional columns to show/ hide. You can access it by hovering over a column header in the table to expose the column menu icon (3 stacked bars - aka "hamburger" icon) and then clicking it. |
| 6 | Sorting | You can click the column header once to sort in ascending order. Click it again to change to descending order, and then a 3rd time to clear the sorting. |
| 7 | Column reordering and resizing | You can drag/ drop a column header to re-order it in the table. Click and drag the column separator to resize columns. |
| 8 | Side bar | This is your quick access to show/ hide columns, column filters, and column grouping tools. Click the tool in the sidebar to bring up the associated tool panel. Click the sidebar again to close it. |

## Column Menu

The column menu is your quick access to common column actions and tools.

## Column Grouping tool

The side bar Grouping tool allows you to control which period groups to show or hide. For example, you can hide a quarter which would show months summarized into years, or hide a month to display only the quarters summarized into years, or hide quarters and even years to show only the month.

![collumn grouping screenshot](../../resources/images/cloudability_images/cfp-collumn-grouping-tool.png)
