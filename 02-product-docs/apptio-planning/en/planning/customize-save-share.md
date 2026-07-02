---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Customize, save, and share table layouts"
breadcrumb: []
source_path: "planning/customize-save-share.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Customize, save, and share table layouts

You can customize the column structure and grouping of any Apptio planning application's
data-entry table and save up to 20 custom layouts for personal use.

Tip: Admins and Budget Process Owners can also customize the default layout or other
custom layouts seen by all users in their organization. To learn more, see [Manage Custom reference data
(dimensions, lists, and line-item tables](manage-custom-reference.htm "(Opens in a new tab or window)").

Watch this video from Apptio Education Services: [Creating and
Customizing Layouts for Data Entry](https://community.apptio.com/videos/1609 "(Opens in a new tab or window)").

Or see all [Apptio planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)").

## Customize a table layout

All users can customize up to 20 table layouts. In addition, Admins and budget owners can
customize the Default Layout for all users in their organization.

1. In the plan menus at the top right, select a plan, a Cost Object category, and a cost object or
   cost object group.

   [Learn more about
   navigating in Planning](navigate-apptio-planning.htm#Toolbar)

   Note: Cost Center Owners can only edit their assigned Cost Centers.
   See [Manage Cost Object Permissions
   reference data](manage-cost-object.htm "(Opens in a new tab or window)").
2. Select a view from the navigation menu under Planning
3. If your view includes tabs, select a tab.
4. Optionally, reorder columns by selecting and dragging a column heading. As you drag the column,
   a vertical bar appears, indicating the target location.
5. In a column heading, select the drop-down menu indicator to display the column options.
   - Sort columns: Select a Sort option to sort that column. A sort indicator displays next to the
     column heading. Grouped columns are sorted by default and therefore always display a sort order
     indicator.
   - Show or hide columns: Select Show/Hide Columns, then select the checkbox for columns to
     show or clear the checkbox for columns to hide. Select Select All to select all columns. You
     can also select Hide Column to hide a column.
   - Group or ungroup column data: Select Group Column or Group Columns, then select
     the checkbox for columns to group or clear the checkbox for columns to ungroup. Groups can be nested
     and grouped information can be expanded or collapsed. If the data had been previously grouped by
     another dimension, selecting Group Column removes that grouping and applies the new one.
   - Freeze or unfreeze a column on the left side of the table: Select Freeze Column or
     Freeze Columns to freeze one or more columns on the left side of the table. Unfreeze a frozen
     column by clicking that column options button and selecting Unfreeze Column:![](../../resources/planning_images/itp_cost-object_freeze.png)

Note:

- Applying a sort order removes any previous sort order.
- You can sort tables by any single, non-grouped column.
- Select Remove Sort to remove a sort preference for non-grouped columns.
- For grouped column values, the sort order is applied from left to right.
- You cannot freeze and group by more than one column at a time.
- Filter conditions are saved in layouts.
- If a plan comparison is present, a layout must contain at least one grouped column. If none is
  specified, the default grouping is Cost Object and Account.

## Save, apply, delete, or share a custom table layout

Save up to 20 custom layouts for reuse. Each layout is unique to the active tab (and if
available, sub-tab). However, custom layouts are not specific to the active plan or Cost Center.

1. In a line-item view, select Layout.
2. Select the option you want:
   - Apply a saved layout to a table: to apply a saved layout to a table, select the Layout
     tab (see the following image) and select the layout.
   - Save a layout: after customizing a layout, select the Layout tab (see the following
     image) and select Save As.
   - Delete a layout: select the Layout tab (see the following image) and select Manage
     Layouts. Select a layout and select Delete.
   - Share a layout (Budget Process Owner or Admin only): select the Layout tab (see the
     following image) and select Manage Layouts. Select a layout and select
     Public.

     ![](../../resources/planning_images/itp_layout.png)

## Important notes about Layout

- Admin and BPO users can save to default layout.
- Layout is consistent across the plans and is specific to a page.
- Layout can save the applied filters, grouping of columns, columns that are visible on
  table.
- Period picker and plan comparison are not saved under layout.
- Non-Admin/BPO users such as CCO users can use Default layout (should show the last saved layout
  changes) defined by Admins but cannot save their layout changes to it. Instead, it can be saved to a
  private layout.
- Admins/BPO users can also share their privately saved layouts by making them "Public"
- When user makes some new layout changes but does not save, an asterisk symbol is shown next to
  the currently active layout to let the user know there were some changes made to layout but has not
  been saved. User can either click Revert to discard the recent changes, or click Save
  to save it to the ;ayout the user is currently on. User could also select Save As to save
  these new changes as a new Layout . If none of these options are chosen, the life of the newly made
  layout changes last until the user refreshes the page or logs out.
- While choosing to save a new private layout, there is a checkbox option to save the layout with
  filters (if applied) and if that option is un-checked then the applied filters are not saved.
- Different users can have their own private layout(s).
- Layout(s) saved can also be deleted by navigating to Layouts> Manage Layout.
