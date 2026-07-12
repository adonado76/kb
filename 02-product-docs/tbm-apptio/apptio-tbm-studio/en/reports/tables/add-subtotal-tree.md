---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Add a subtotal tree structure to a table"
breadcrumb: []
source_path: "reports/tables/add-subtotal-tree.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add a subtotal tree structure to a table

Applies to: TBM Studio 12.0 and later

If you are creating a hierarchical table, you can create a table with expandable rows. When you
expand a row, rows from the next level down in the hierarchy are displayed below the expanded row.
For example, you might want to drill down by business unit, application, and service. An example is
shown in the following image.

![](../../../resources/images/studio_images/studioimages/reports/rep329.png)

Figure A. An example table with a subtotal tree structure.

## General guidelines

The following guidelines apply to subtotal tree structures:

- You can nest rows to multiple levels.
- You can display all sub-rows or specify the number of sub-rows to display with an Other
  link to display the remaining sub-rows.
- You can use fields from multiple objects if the fields are locked to the objects.
- Slicers still apply to the table.
- Works with object-based tables.

## Create a subtotal tree structure

1. Create a new ad-hoc table.
2. Drag two or more fields into the Rows area of the Component Configuration
   pane.

   If you are adding fields from one or more objects, the fields must be locked to the
   object.
3. Add one or more fields to the Values area of the Ad Hoc Query Configuration
   panel.
4. Click the Data tab.
5. In the Structure group, click the As Tree option.
6. If appropriate, specify the maximum number of children that will be displayed by clicking the
   Max Children option.

   An Other link row is added to the table to display the
   remaining rows.

## Export a tree view table to Excel

You can export a tree view table to Excel. When the table is exported, all parent and child rows
are exported. The first column of each child row is indented by two spaces to indicate the level of
hierarchy that the row is in. The export to Excel will not create a corresponding tree table.
Instead, it will create a flat table. For example, the following table, when exported.

![](../../../resources/images/studio_images/studioimages/reports/rep341.png)

Would look like:

![](../../../resources/images/studio_images/studioimages/reports/rep342.png)
