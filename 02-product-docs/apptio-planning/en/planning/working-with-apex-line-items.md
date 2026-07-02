---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Working with Apex Line Items"
breadcrumb: []
source_path: "planning/working-with-apex-line-items.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Working with Apex Line Items

This topic explains how to manage Apex line items in the application, including adding,
inserting, duplicating, importing, exporting, and deleting line items.

## Before you begin

All the features listed here are available only for the customers who do not have PFP or SDP.
When an Admin or Budget Process Owner enables the Apex Line Item Table feature, users with
non-administrator role can change the table view between `Classic View` and
`New View`.

## Procedure

- Add line items:
  1. Above the line items table, select the (Image of the Plus (+)) icon.
  2. In the `New Line Item` window, select the attributes of the new line.
  3. Select `Add` to add the line item.

     Alternatively, Select `Add Another` to add more line items, and select
     `Add` to add the line items.
  4. To add optional attributes, double-click the cell in the table and enter the details.
- Insert line items:
  1. Right click a row.
  2. Select Insert Row Above or Insert Row Below to
     insert a row.
  3. In the New Line Item window, select the attributes of the new
     line.
  4. Select Add to add the line item.

     Select Add Another to add more line items, and select
     Add to add the line items.
  5. To add optional attributes, double-click the cell in the table and enter the
     details.
- Delete line items:
  1. Right click the line item.
  2. Select Delete option. A confirmation popup appears.
  3. Enter the `LineItem Code` and select Delete.
- Duplicate line items:
  1. Right click the line item.
  2. Select Duplicate Row.
- Import line items:
  1. Above the Expenses table, select the Options
     icon.
  2. To import external line items, select Import external financials.

     Alternatively, to import non-external line items, select Import
     financials.
- Export line items:
  1. Above the Expenses table, select the Options
     icon.
  2. To export an expense type template, select Export financials
     template.

     Alternatively, to export line items, select Export financials.
- Dependent picklist tooltip

  When you select an option in one column, it may restrict the options which can be selected in
  another column, because Planning automatically excludes options which would be incompatible with the
  option you have selected in the first column.

  For example, every project might be using a different set of cost centers. When the Cost center
  in a row is changed, the list of options which can be selected for Project in that row also changes.
  These options might be a subset of all the projects available in the environment.

  Users may find this confusing because they see a different list of options for different rows in
  the same column.

  A tooltip icon is now displayed in the table cell (Add image of the Dependent picklist tooltip
  dep\_tool\_pick.png)

  When you hover over the tooltip, it displays a column-specific message, explaining which column
  is responsible for filtering the list options. (Add image of the Dependent picklist tooltip
  dep\_tool\_pick1.png)

  This feature is only available in Apex line-item tables. It is not available in classic line-item
  tables.

  Line Item Filters are not yet supported in Apex line-item tables. When Apex line-item tables
  support Line Item Filters, columns filtered by the line item filter configuration will use the
  dependent picklist tooltip.
- Bulk delete expenses:
  1. In the navigate menu, select Expenses > New
     View.
  2. Select the lines you want to delete by clicking the check-box or using `SHIFT + down
     arrow` from keyboard to select multiple lines
  3. Select the (Delete Icon Image) icon from the menu bar above the table. Alternatively
     you can also do the same operation from the context menu using mouse right-click.
  4. A delete confirmation dialog appears.
  5. Note: When the expenses view is grouped by one or more columns, the row level operations
     such as add row, copy row, delete row and duplicate row are not available.

     Provide the
     confirmation details in the confirmation input box and select the `Delete`
     button.
