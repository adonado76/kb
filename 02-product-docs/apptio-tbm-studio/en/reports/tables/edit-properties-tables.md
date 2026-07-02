---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Edit properties for tables"
breadcrumb: []
source_path: "reports/tables/edit-properties-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Edit properties for tables

Applies to: TBM Studio 12.0 and later

You control how users interact with editable tables with the Editing properties. Note that these
properties apply to generated tables as well. To learn more about the Editing properties, see [Set table properties](set-table-properties.dita "(Opens in a new tab or window)").

You can also control how users interact with editable tables with the Editing properties from the
TBM Studio ribbon bar. Note that these properties apply to generated tables as well:

![](../../../resources/images/studio_images/properties-1.png)

## Upload

You can upload an editable table in one of the ways:

- Select Upload from the Editable Tables ribbon.
- Select the Upload button at the bottom of the table. This button appears only when you enable
  the Enable/Disable Upload option in the [Advanced Properties](set-table-properties.dita "(Opens in a new tab or window)") popup.

To know more about upload options, see [Table Upload component.](../table-report-upload-component.dita "(Opens in a new tab or window)")

## Download

This button is available by default for all editable tables. On selecting this button, the
following popup appears.

![](../../../resources/images/studio_images/export-et.png)

Make the appropriate choice and select Export button.

## Enable Add Row Dialog

Select Enable Add Row Dialog button configure and add new row with
pre-filled data.

Click Add Row button to see the dialog box that has column and data, and
then select the row to add in the current report.

## Disable Edits

This field takes a dynamic text expression. If the expression evaluates to true, editing will be
disabled for the table. In the example below, user ddavis will not be able to edit the table.

> `{$CurrentUser:Users.ID}="ddavis@ABCCompany.com"`

For more information on dynamic text, see [Insert context-dependent text into the HTML](../html.dita "(Opens in a new tab or window)").

From 12.11.6, the Delete All Rows button will appear even when the
expression is 'true'.

![](../../../resources/images/studio_images/disable-edits.png)

## Uneditable Columns

Applies to 12.10.10 and later

This field allows you to make a column as non-editable. Expand the Uneditable
Tables option to see the list of columns that can be made non-editable.

![](../../../resources/images/studio_images/fr-uneditablecolumn.png)

## Script

ApptioScript is the scripting language that is used to build the interactive business
applications on top of the Apptio Platform.

ApptioScript can be used to perform many operations, such as edit tables, send email, transition
states in work flow, or script what happens when the user clicks a button. See [About ApptioScript](../../apptioscript/about.dita "(Opens in a new tab or window)") and
[ApptioScript examples](../../apptioscript/apptioscript%20examples.dita "(Opens in a new tab or window)").

## Validate Total

Total Column Validator
:   Used to validate row totals. For example, you may want a row of numbers to add to 100. Or, you
    can check for values that fall between a low and a high value. When this feature is used, a Totals
    column is added to the right side of the table. Values that fall outside of the parameters are
    highlighted in red.

    To define the validators, click the icon at the right of the field. The **Total Column
    Validator** dialog is displayed as shown below. Select Total in the first
    field, select a qualifier in the second field, and enter a value in the third field. You can add
    multiple entries to specify minimum and maximum values. To add a second entry, click the + sign
    below the first entry.

    ![](../../../resources/images/studio_images/studioimages/reports/rep169.png)

Total Row Validator
:   Used to validate row totals. For example, you may want a column of percentages to add to 100%.
    Or, you can check for values that fall between a low and a high value. When this feature is used, a
    Totals row is added to the bottom of the table. Values that fall outside of
    the parameters are highlighted in red.

    To define the validators, click the icon at the right of the field. The **Total Row
    Validator** dialog is displayed as shown below. Select Total in the first
    field, select a qualifier in the second field, and enter a value in the third field. You can add
    multiple entries to specify minimum and maximum values. To add a second entry, click the + sign
    below the first entry.

    ![](../../../resources/images/studio_images/studioimages/reports/rep170.png)

## Permissions

This section allows you to grant/deny permissions for the following actions on a row. The default
permission for Delete All Rows Permission is *admin and partner*, while
rest of the permissions have *everyone* as the default value.

![](../../../resources/images/studio_images/r-notes/et-permission_232x359.png)

## Add Row Permission

Specifies the roles that will be able to add rows to the table. The options are *Everyone*
and *Selected Roles*. To specify the roles, click the Select roles icon
choose the role(s) from the dropdown.

![](../../../resources/images/studio_images/permission-dialog.png)

## Duplicate Row Permission

Specify the roles that will be able to duplicate the rows in a table.

## Delete Row Permission

Specify the roles that will be able to delete rows from the table.

## Publish Row Permission

Specify the roles that will be able to publish rows to the table.

## Edit Row Permission

Specify the roles that will be able to edit rows in the table.

## Download Permission

Specify the roles that will be able to download the table.

## Upload Permission

Specify the roles that will be able to upload the table.

## Show History Permissions

Specifies the roles that will be able to see history of changes made in the table.

![](../../../resources/images/studio_images/r-notes/et-export_907x507.png)

## Delete All Rows Permission

Specify the roles that will be able to delete all rows from an editable table.

## Delete All Rows

This button appears only when you enable the Delete All Rows option in the
[Advanced Properties](set-table-properties.dita "(Opens in a new tab or window)")
popup. On selecting this button, the warning popup appears as shown.

![](../../../resources/images/studio_images/delete-all-rows-popup.png)

Enter 'delete' and then select OK button. The table is blank, but all the
changes are captured in Show Changes section.

Note: If you enter any value other than 'delete', the OK button will remain
disabled.

If all cells in the filtered set of viewable rows are locked, then all buttons (Add Row, Delete
Row, and Duplicate Row) will be disabled but the Delete All Rows button will remain enabled. ​

## Enable Checkbox Column

12.11.5 and later: The select checkbox column appears only when you enable
the Enable Checkbox Column option in the [Advanced Properties](set-table-properties.dita "(Opens in a new tab or window)") popup. Filter for specific values, and then use the
ApptioScript button to edit the cell value or delete the row.

![](../../../resources/images/studio_images/sel-chkbox-et.png)

Select or drag the cursor across multiple rows. right-click and then select Delete
Row option.

![](../../../resources/images/studio_images/checkbox-del-row.png)

From 12.11.6 onwards, you can do the following:

- From a filtered values, select a specific row(s) and edit the cell value or delete that row(s)
  using the ApptioScript button.

## Publish

Select this button to publish the data of generated tables to the parent tables. For more
information, see [Manually publish changes in the reporting surface](../../data_studio/table-update-schedule.dita "(Opens in a new tab or window)").

## Supress

This feature allows you to supress/hide data in lengthy and large editable tables.

12.11.5 and later: The editable table report is suppressed only when you
enable the Suppress initial data request option in the [Advanced Properties](set-table-properties.dita "(Opens in a new tab or window)") popup.

If the Suppress initial data request option is selected, then all data
will be hidden in the table. A message appears "*Please select your preferred filter to retrieve
the data. Note: Automatic loading of the report has been disabled.*".

![](../../../resources/images/studio_images/suppress-et.png)

To see data of your choice, you must apply [compact slicers](../compact-slicers.dita "(Opens in a new tab or window)") or row filters.

![](../../../resources/images/studio_images/default-slicer.png)

![](../../../resources/images/studio_images/apply-filters.png)

![](../../../resources/images/studio_images/row-slicer.png)

Alternatively, you can refresh data manually, automatically, or by selecting Update
Data in the right click menu.
