---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Set table properties"
breadcrumb: []
source_path: "studio/reports/tables/set-table-properties.html"
images:
  - "resources/images/studio_images/properties.png"
  - "resources/images/studio_images/studioimages/icons/edit_21x21_icon.png"
  - "resources/images/studio_images/studioimages/icons/hydration_warning_15x15icon.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Set table properties

**Applies to**: TBM Studio 12.0 and later

There are a wide range of properties available for tables that control the look and feel of a
table. Many of the properties are available from the Ribbon. Others are available from the **Table
Properties** dialog.

See also [How To: Create a Generated Table](https://community.apptio.com/docs/DOC-8377 "(Opens in a new tab or window)")

## Open the Properties dialog

Right-click the Total bar of the table and select **Properties**.

The Properties dialog is displayed.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/properties.png)

The Properties dialog organizes table properties in the following tabs:

- Data
- General
- Advanced

To preview changes, select **Apply**. To save changes, select
**OK**.

Note: Some tables will have a subset of these fields. Fields marked with
an asterisk ( \* ) apply only to legacy tables.

## Data properties

| **Field** | **Description** |
| --- | --- |
| **Maximum Rows** | Specifies the page size for the paging table. For example, if you set **Maximum Rows** to 20 for a table with 15 rows, there would be no paging bar, just a scroll bar. |
| **Hide Paging Bar** | Hides the paging bar for multi-page tables. If hidden, only the number of rows designated in the **Maximum Rows** field are displayed. The user cannot display additional rows. Use this option when you want only an x number of rows displayed in a table. For example, the top 10 most-used routers. |
| **Include Columns** | Open the drop-down list and select the columns to include in the table. When using this feature, you must select all columns you want to display in the table, including the currently displayed columns. |
| **Exclude Columns** | Open the drop-down list and select the columns to exclude from the table. |
| **Auto Search Filter** | This option adds search fields below each column header as shown below. You can type search text into the fields.    When you enter text in a field, the table will display only rows that contain the text. The filter is not case sensitive. For numeric columns, you can use the standard operators: <, <=, >, >=. For Label columns, "=" is supported for case-sensitive exact matches. For example, =Billing will include Billing but exclude Billing Extract. |
| **Show rows for which all metric values are 0\*** | By default, if a row in the table has zeros in all metric columns, the row is not displayed. You can display the row by checking this option. |
| **Column to resize** | Allows you to automatically adjust selected table columns to fit the available space in the report.  Enter the column names separated by a comma, for example Project Name,Vendor ID. |

## General properties

| **Field** | **Description** |
| --- | --- |
| **Name** | Enter a name to be displayed in the table header above the component. The name is displayed when the **Show Header** option is selected. |
| **Caption** | Enter additional information about the table. The information is displayed based on the setting of the **Caption Position** field. You can use HTML code in the field, but the HTML code cannot include links. The restriction on the HTML code is for security reasons. |
| **Caption Position** | From the list, select a caption position relative to the table: **Top**, **Bottom**, **Left**, or **Right**. To hide the caption, select **Hide**. |
| **Show Header** | The component header displays the contents of the **Name** field. Select this option to make the table header visible. When in Edit mode, you can display a hidden header by pausing the mouse pointer over the table. |
| **Show Border** | Select this option to display a border around the table. When in Edit mode, you can display a hidden border by pausing the cursor over the table. |
| **Wrap Title** | Wraps the text entered in the **Name** field to accommodate the width of the table. |

## Advanced properties

| **Field** | **Description** |
| --- | --- |
| **Data URL\*** | Displays the path to the table that supplies the data for this report. You can enter a table function in this field by clicking the **Edit Data Path** icon  to the right of the field. The application displays the **Edit Path** dialog. **Warning**: do not edit the path if you are not thoroughly familiar with data paths. |
| **Auto Refresh When Calculations Finish** | When the application displays a table, it displays it with the calculated data that is currently available. In many cases, the application may be calculating new values in the background. If you want the results displayed when the calculations are complete, check this option. The option applies only to the currently selected table.  The option is relevant only when the **Calculation Policy** (in the **Project Calculation** dialog) for a project is set to **Dynamic Publishing**. |
| **Enable/Disable Upload** | Enables the **Upload** button for an editable table. |
| **Append data upon upload** | Admins use this option to set the table upload behaviour to either 'append' or 'overwrite'. |
| **Suppress initial data request** | Suppresses the report data for the first time. |
| **Add Checkbox Column** | Enables the checkbox column in the editable tables. |
| **Dated Edits** | This option allows the carry forward of values. On enabling, any modification made in a numeric column will carry forward to all the subsequent numeric columns on its right. |
| **Allow Delete All Rows** | Enables the **Delete All Rows** button for an editable table. |
| **Data Time Period** | Determines the data displayed in the table. The default option, **Current Project Date**, displays data for the currently selected time period.  **Start of Current Project** ensures data is entered into the starting month of the project.  If you select an option other than **Current Project Date**, the application displays a small lock icon in the lower-right corner of the table. The icon indicates that data entered in a table will be applied to the selected time period. |
| **Hide Time Lock Warning** | If you have set the **Data Time Period** field to a value other than **Current Project Time**, a lock icon is displayed in the lower-right corner of the table. Checking this option hides the icon. |
| **Hide Hydration Warning** | In Edit mode, if you place a component on an object report that is based on a different unit than the report itself, the application displays a warning  icon and a text message in the lower-right corner of the component. These are not displayed in View mode. If you select this option, the warnings will not be displayed in Edit mode.  For example, assume you have a Business Units object and you drill down to a Business Unit A report with a chart and table that display data about Business Unit A. In the same report, you want to display information about Business Unit B for comparison purposes. You add a table to the report to display the information. Because you did this intentionally, you do not want the application to display the hydration warning, so you select the **Hide Hydration Warning** option. |
| **Auto Shorten New Dotted Column Names** | Displays only the part of a column name that follows the "." dot. For example, if the column name is Data Center Costs.Data Center Hosting Cost, the name would be displayed as Data Center Hosting Cost. |
| **Lines Per Row** | Sets the number of lines for each row in the table. The default is zero which allows the contents of the cell to wrap. If you enter a value in this field, all rows in the table will display with that number of lines. Text that does not fit in the cell is truncated. |
| **Max. Columns to Display** | Limits the number of columns that can be displayed in a table. Note that a table with many columns can impact performance. |
| **Include PK Column** | Will include the default column in the chart/table, whether or not it is specified in the normal ‘columns to include’ list. In ungrouped tables, this is typically the identifier of the object backing the report component. For grouped tables, it is typically the column used for the grouping. |
| **Pivot Row Col** | The column in the source table that provides the values for the first column in the pivoted table. |
| **Pivot Col Col** | The column in the source table that provides the headings for the data columns in the pivoted table. |
| **Pivot Val Col** | The column in the source table that provides the values for the cells in the pivoted table. |
| **Use Column Aliases** | In circumstances where you have two objects with the same columns displayed in the same table, such as Consumer.Master Table.L0 Name and Provider.Master Table.L0 Name, checking this option makes is possible to correctly configure the columns in the table. **Recommendation**: leave this option selected. |
