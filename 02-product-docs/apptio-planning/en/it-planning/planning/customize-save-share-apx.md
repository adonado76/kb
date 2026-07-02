---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Customize, save, and share table layouts"
breadcrumb: []
source_path: "it-planning/planning/customize-save-share-apx.html"
images:
  - "resources/images/it_planning_images/release-notes/3.78_rn.jpg"
  - "resources/images/it_planning_images/release-notes/378rn-1.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Customize, save, and share table layouts

The Expenses Table in the New View offers enhanced customization capabilities, including the
ability to customize column structure, grouping, filters, and save changes as a layout. Individual
users can create up to 50 private layouts, while admin users can create up to 50 public layouts.
This represents an increase from the previous limit of 30 layouts in both public and private
settings in the Expenses Legacy View.

In a future release later this year, users will also gain the ability to sync existing layouts
from the Expenses Legacy View to the New View, ensuring continuity and ease of transition.

## Customize a table layout

All users can customize up to 50 table layouts. In addition, Admins and budget owners can
customize the Default Layout for all users in their organization.

1. Navigate to **Planning** > **Expenses** from the left navigation
   menu.
2. Select the appropriate plan from the **Plan** dropdown on top left.
3. Select the specific tab where you want to customize the table layout.
4. Optionally perform various supported customization options to customize the table layout such as
   - **Reorder columns**: Select and drag a column heading. As you drag the column, a vertical bar
     appears, indicating the target location.
   - **Show or hide columns**: Select Columns menu from the right table menu, then select the
     checkbox for columns to show or clear the checkbox for columns to hide.
   - **Sort columns**: Columns can be sorted by selecting the column header. A sort indicator
     displays next to the column heading. You can change the sort direction or remove the sort by
     selecting on the column header. Grouped columns are sorted by default.
   - **Group or ungroup column data**: Select Group Column or Group Columns, then select the
     checkbox for columns to group or clear the checkbox for columns to ungroup. Groups can be nested and
     grouped information can be expanded or collapsed. If the data had been previously grouped by another
     dimension, selecting Group Column removes that grouping and applies the new one.
   - **Pin** column on the left or right side of the table.
   - **Apply Filters** on various columns and attributes.

## Save, apply, delete, or share a custom table layout

Save up to 50 custom layouts for reuse. Each layout is unique to the active tab (and if
available, sub-tab). However, custom layouts are not specific to the active plan or Cost Center.

Create Layout
:   1. Customize the table layout as per the requirements, by following instructions from the previous
       section.
    2. Select ![table icon](../../resources/images/it%20planning_images/layout-icon_28x20.png) from the Expenses Table menu.
    3. In the layout menu, select **Add New Layout**.
    4. Enter the layout name.
    5. If you wish to save the applied filters as well into the layout, check the checkbox **Apply
       Filter Selection** and then select **Save**.
    6. The newly created layout will appear under **My Layouts**.
    7. Hover the cursor on the **Layout** button to see the currently selected layout.

Rename Layout
:   1. Select ![table icon](../../resources/images/it%20planning_images/layout-icon_28x20.png) from the Expenses Table menu.
    2. In the My Layouts menu, select the pencil icon for the layout you want to rename.

       ![dashboard](../../resources/images/it%20planning_images/tl-edit.png)
    3. The Rename Layout popup appears.

       ![summary view](../../resources/images/it%20planning_images/tl-edit-1.png)
    4. Update the layout name and select **Save**.

       Note:

       The **Save** icon remains disabled until a change is made to the layout.

Edit Layout
:   1. To customize a layout, select the layout you want to change.
    2. Make the required changes and then select **Save**. A confirmation message "*Success: Save
       my Layouts*" appears and the updated layout is loaded.

       ![save in dashboard](../../resources/images/it%20planning_images/tl-edit-2.png)

Clone Layout
:   Note: This option is available only for Public Layouts. The **Clone** icon remains disabled until
    a change is made to the layout.

    1. Select ![table icon](../../resources/images/it%20planning_images/layout-icon_28x20.png) from the Expenses Table menu.
    2. In the **Public Layouts** menu, select the 'Default Layout' and select the **Clone**
       ![copy icon](../../resources/images/it%20planning_images/tl-cln-icon_20x20.png)icon.

       ![clone layouts](../../resources/images/it%20planning_images/tl-clone.png)
    3. The Copy Layout popup appears. Enter a name for the layout and select **Save**.

       ![new layout](../../resources/images/it%20planning_images/tl-copy.png)
    4. The cloned layout is added to My Layouts section, as shown.

       ![clone](../../resources/images/it%20planning_images/tl-cln-1.png)

## Delete Layout

1. Select ![img](../../resources/images/it%20planning_images/layout-icon_28x20.png) from the Expenses Table menu.
2. In the My Layouts menu, select the **Delete** icon for the layout you want to
   delete.

   ![delete layout](../../resources/images/it%20planning_images/tl-del.png)
3. The layout is deleted.

   Note: Public layouts cannot be deleted.

## Reset Layout Changes

- To reset the complete layout, select the **Reset columns to default layout** option from the
  ![img](../../resources/images/it%20planning_images/layout-icon_28x20.png) menu.

  ![reset layout](../../resources/images/it%20planning_images/tl-reset-default.png)
- To undo the changes made in a particular layout (before saving it), select the ![reset icon](../../resources/images/it%20planning_images/tl-reset-icon_26x22.png) icon for that layout.

  ![reset icon](../../resources/images/it%20planning_images/tl-reset.png)

  An error message appears as shown. Select **Okay** to continue with the
  reset.

  ![warning](../../resources/images/it%20planning_images/tl-rst-error.png)

## Manage Layout Access

The Layout Access is enabled only for Administrators. It allows the Admin to make a layout as
Public, so that it is available to all users within the organization.

1. Select ![img](../../resources/images/it%20planning_images/layout-icon_28x20.png) from the Expenses Table menu.
2. From the dropdown, select the **Layout Access** option. The following popup appears.

   ![layouts](../../resources/images/it%20planning_images/tl-access.png)
3. Switch the toggle for the layout that needs to be made **Public** and then select
   **Apply**.

   ![layouts](../../resources/images/it%20planning_images/tl-toggle.png)
4. The selected layout is removed from **My Layouts** section and will appear in the **Public
   Layout** section. Once the layout is marked 'Public', it cannot be deleted.

   ![clone layouts](../../resources/images/it%20planning_images/tl-publay.png)

   To make the layout as private or delete a public layout, switch the
   toggle again and then select **Apply**.

## Sync Legacy Layouts

Users can now transfer their Expenses Table layouts from the Legacy View to the New View with a
single click, eliminating manual migration and saving time.

To sync layouts, simply click on the Layouts icon in the New View and select "Sync Legacy
Layouts." This will automatically copy your layouts from the Legacy View to the New View. Please
note that you will need to sync layouts for each tab in the Expenses Table individually to complete
the migration from the Legacy View to the New View.

![sync layouts](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.78_rn.jpg)

Layouts migrated from Legacy View to New View will be visible under My Layouts and Public Layouts
for Private and Public layouts respectively. The migrated layout name will be suffixed with
"\_migrated". Please see the reference screenshot below.

![migrated layouts](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/378rn-1.jpg)

If you continue to make updates to layouts in the Legacy View after migrating them to New View,
you need to use Sync Legacy Layouts option in the New View to bring the updates to New View.

Note:

- Layout is consistent across the plans and is specific to a page.
- Layout can save the applied filters, grouping of columns, columns that are visible on
  table.
- Admin and BPO users can edit and save changes to default layout.
- Admins/BPO users can also share their privately saved layouts by making them "Public"
- Non-Admin/BPO users such as CCO users can use Default layout (should show the last saved layout
  changes) defined by Admins but cannot save their layout changes to it. Instead, they can create a
  new private layout and save customization made to public layout.
- Non-Admin/BPO users such as CCO users can create upto 50 private layouts.
- While choosing to save a new private layout, there is a checkbox option to save the layout with
  filters (if applied) and if that option is un-checked then the applied filters are not saved.Plan
  comparisons can be saved into layout.
- Plan comparisons can be saved into layout.
- It is not possible to save the Period picker.
- When user makes some new layout changes but does not save, an asterisk symbol is shown next to
  the currently active layout to let the user know there were some changes made to layout but has not
  been saved. User can either select Revert to discard the recent changes, or select Save to save it
  to the layout the user is currently on. User could also select Clone to save these new changes as a
  new Layout . If none of these options are chosen, the life of the newly made layout changes last
  until the user refreshes the page or logs out. If user attempts to switch to another tab or select
  another layout with unsaved changes in the current layout a warning message will be shown describing
  loss of unsaved changes to the layout.
- If the table is not showing period columns (months, quarters, years) please use following steps
  to make them visible.
- 1. Select Grouping on the table menu.
  2. Ensure Year, Month(s), Quarter(s) is selected.
  3. If the period columns are still not visible, select the Layout button above the table and select
     **Reset columns to default layout**.
  4. Now all period columns should be visible.
  5. Navigate to Layout button > Public Layout > Default Layout and click Save button. This step will
     ensure the changes are saved and period columns become visible by default.

  These steps should make the period columns visible in the table view.
