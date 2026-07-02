---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "The Component Configuration panel"
breadcrumb: []
source_path: "reports/tables/component-config-panel.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# The Component Configuration panel

Applies to: TBM Studio 12.0 and later

The Component Configuration panel is displayed when you insert a table or chart in a
report. It includes a table selector and areas where you drag fields to build tables and charts:

![](../../../resources/images/studio_images/studioimages/studio/stu537.png)

There are two versions of the Component Configuration panel: Power User and Analyst. The
version a user sees is controlled by the role assigned to the user. The two versions are described below:

- Power User - Sees all features in the configuration panel and can create custom
  perspectives available to the analyst. This view is available to users assigned the Admin role or
  equivalent. The role must have the Edit Models permission.
- Analyst - Sees only the custom perspectives, Time perspective, and the
  Component Configuration panel. This view is available to users assigned the Business User
  role or equivalent.

When you insert a report component and select a model table from the drop-down list, the selected
table determines the fields available in the perspectives in the Project Explorer. All data
sets and metrics linked to the selected table through the inference engine will be available.

The sections in the Project Explorer organize the fields that can be dragged into the
configuration areas to build a table. The standard dimensions are described below:

- Tables - Displays the names of the tables that are linked by the **Apptio Inference
  Engine** to the selected object.
- Metrics - Displays modeled and calculated metrics.
- Time - Displays available time periods.
- Perspectives - To augment the standard sections, you can create custom perspectives in
  the Perspectives section. Custom perspectives contain selected fields from the other sections
  you want to make available to analysts. For more information on perspectives, see [Creating custom
  perspectives](../creating-custom-perspectives.htm "(Opens in a new tab or window)").

To build a table, drag fields from the Project Explorer into the areas at the bottom of
the Component Configuration pane. Multiple fields can be added to all areas except the
Columns area. If a field cannot be applied to an area, a warning message is displayed.

To remove a field from an area, drag it out of the area or right-click on the field and select
Remove.

The four areas are described below.

- Rows - Provides entries for the first column in the table. If there are duplicate entries
  in the source, the entries are grouped and a single entry for each unique value is displayed. If you
  add more than one field to the area, sub-groups are created in the first column of the table.
- Columns - Provides column headers for the table. Drag one field here from a perspective.
  Only one field can be put in the Columns area.
- Values - Provides the data displayed in the body of the table. You can hide a value by
  right-clicking the value and selecting Hide.
- Filters - Filters the entries in a column in the table. Drag fields here from
  perspectives and other areas. If you use a metric, you can right-click on the metric and set the
  number range.

## Show/hide .pk column

Applies to: R12.11.2 and later

The Apptio Admin can now show (and hide) the .pk column for raw editable tables in an editable
table report component and also sort the values by it. The .pk column will be included by default in
included columns as soon as user drags any column to included columns but will be hidden by default.
User can show/hide pk column on a report by hovering the cursor on .PK column and <right-click>
to popup the Add to Filters menu. Verify that .PK column is hidden by default and Show button is
enabled. On selecting "Show" the .PK column will appear, and it can be moved to any desired
column order.

![](../../../resources/images/studio_images/show-pk.png)

If .pk column is visible on report and a new row is added, its value will not be visible until
the row is saved. This has been done to keep the pk index pattern hidden from user. The end user can
use this feature to support consistent multi-cell, copy/paste, sort PK column on-line/excel sheet,
and to copy/paste starting with correct range.

![](../../../resources/images/studio_images/show-pk-column.png)​

## Show/hide .Username and .EditDate columns

**Applies to**: 12.11.11 and later

The Apptio Admin can now show (and hide) the .Username and .EditDate columns in an editable table
report component and also sort the values by it. The .Username column will show who made the last
change and .EditDate will show when the last change was made. Both these columns will be included by
default in included columns as soon as user drags any column to included columns.

![](../../../resources/images/studio_images/new-column.jpg)

The user can show/hide these columns on a report by hovering the cursor on it, <right-click>
to popup the **Add to Filters** menu. On selecting "**Show**" the columns will appear, and it
can be moved to any desired column order. Both these columns are read-only and no changes can be
made on them.

![](../../../resources/images/studio_images/nc-shoiw.jpg)

## Change the order of fields in area boxes

To change the order of fields in an area box, drag the fields up or down in the list. The order
of the fields determines the order of the corresponding columns in the table.

## Clear all fields

To clear all fields from the areas, click the Clear button at the bottom of the pane.

## Defer updates

By default, changes you make in the Ad Hoc Query Configuration pane immediately affect the
data displayed in the table. If you are working with large data sets, it may take time for the data
to update in the table. To avoid delays, you can switch to manual updates by clearing the **Update
Results Immediately** option at the bottom of the dialog. When this option is not selected,
updates are made only when you click the Update button.

## Minimize the pane

To minimize the Configuration pane, click the arrow in the upper-right corner.

## Filter fields in a section

If there is a long list of fields in a section, you can filter the list by entering text in the
auto-filter box at the top of the section. As you enter characters, the list is filtered:

![](../../../resources/images/studio_images/studioimages/studio/stu536.png)
