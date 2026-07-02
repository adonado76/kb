---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Editable tables: Accommodating user input"
breadcrumb: []
source_path: "studio/data_studio/editabletables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Editable tables: Accommodating user input

**Applies to**: TBM Studio 12.6 and later

Tables are a useful way to present data and are a common element in reports. There are two types
of tables:

- **Transform** - A transform table is a table that can complete potentially
  time-intensive calculations. These tables go through the Apptio calculation process, and can receive
  data from editable tables. They are visible under the **Tables** section of the
  **Project Explorer**.
- **Editable** - Editable tables let users enter data in tables. An editable
  table is used for entering data that is maintained directly within the Apptio project database. The
  table is generally used to support the manual entry of data for which there is not another source
  system. For example, to map other cost pools to IT Resource Towers.

  [Learn more about editable
  tables](enter-data-manually.html "Applies to: TBM Studio R12.0 and later")

The information below describes editable tables. For details on transform tables, see [Data Studio: acquire and transform
data](about-data-transforms.html "Applies to: TBM Studio 12.0 and later").

## Copy and paste data between Excel and the application tables

You can copy and paste data between Excel and an editable table. Specifically, you can:

- Copy cells from an editable table and paste them into Excel.
- Copy cells from Excel and paste them into an editable table.

The format of the cells is ignored. Cells can be pasted anywhere in an editable
table.

Note: Whether you start in Excel or in a table in Apptio, the cells you copy must be in a
contiguous range. If you attempt to copy nonadjacent cells or an incomplete block of cells, you will
get a message stating that the selection is not valid.

## Copy data from tables to Excel

To copy data from an editable table to Excel:

1. Select the cells you want.
2. Copy the cells to the clipboard. On a Windows PC, press Control+C. On a Mac, press ⌘+C.
3. In Excel, paste the cells into the workbook.

## Copy cells from Excel to an editable table

To copy data from Excel to a raw data set, or to an editable table on a report:

1. In Excel, copy the cells.
2. Display the target report or data set.
3. Do one of the following:
   - To paste new data rows, select **Add Row**, and then select the leftmost cell
     in the new row.
   - To replace existing data, click to select the top-left cell in the range to be pasted.
4. Paste the data.

Note: There is no limit to the number of rows that can be copied or pasted. If there are too many
lookups present in a report, or formatting is applied to many columns when trying to paste more than
100 records, then an error may occur. In this case, it is recommended to use [file upload with append](https://help.apptio.com/en-us/studio/reports/table-report-upload-component.dita "(Opens in a new tab or window)") feature.

## View data set properties

Editable tables have unique properties controlling the editing behavior of each column. To edit
table properties:

1. Select the table.
2. Click the columns portion of the pipeline.
3. Click on the column that you wish to modify.

   Note: The **.PK** column is a
   system-generated primary key column and has a different set of properties that are specific to it.
   Additionally, on a generated table, many properties are not available for columns that are included
   from the base table.

The following image shows the data set properties displayed in the **Configure Columns** step.
The tab is displayed when you select an editable table from the **Project Explorer.**

![](../../resources/images/studio_images/studioimages/studio_configure%20columns_benchmark%20sub-tower.png)

## Column properties

This table describes the data set properties on the **Configure Columns** step.

| Column | Description |
| --- | --- |
| **Unique ID Pattern** | This property exists only when viewing the system-generated **.PK** column. The input is a numeric pattern with which the unique row ID will be displayed. A value of word-0000 will result in the PK values being of the form word-00001 and word-00002. Numeric Patterns support 2 special symbols to represent the row number.  - **0** - A digit. Use this if you want currency displayed with digits even if   it is 0. So, 0000 can be used to always display 4 digits, with leading zeros. - **#** - A digit. If the digit is zero, it is not displayed. |
| **Name** | The name of the column. |
| **Description** | Enter notes about this column and why it exists. |
| **Type** | Select the type of data expected in the column cells. Select one of the following from the drop-down:  - **Label** - plain text data - **Date** - data in date format. Selecting this will pop a dialog prompting   the entry of the desired date format. Refer [DateFormat   function](../formulas-and-functions/functions/dateformat.html "Converts a date expression to a specified date format.") for a list of allowed formats. Note: The date format string should not be enclosed in   quotes. - **Numeric** - numeric data which supports numeric entries in the project   locale |
| **Date Format** | Activated only when the Type field is selected as Date. Once selected, you can change the format by updating to an allowed format. Refer [DateFormat function](../formulas-and-functions/functions/dateformat.html "Converts a date expression to a specified date format.") for a list of applicable formats. |
| **Possible Values** | Used for configuring dropdowns in a column. This can be configured in either of these ways:  - A comma-delimited list of values will create a list from the typed values. - A formula with the syntax %tablename /TableFunction[ ]. - The new line characters “\n” is not supported.  [Learn more about the Possible Values settings.](table-functions.html "Applies to: TBM Studio 12.0 and later") |
| **Possible Values Context** | Provides context for using dynamic text within a possible values formula. This allows configuration of advanced features such as dependent dropdowns. If in doubt, set this to **Current row**. |
| **Allow Values Not In Possible Values List** | If checked, the user will be able to type in a value that is not in the possible values list and save the table. In unchecked, they must pick a value from the dropdown. |
| **Disallow Edit In Possible Values Cell** | If checked, users will not be able to type in the column. Being able to type is useful as it allows filtering the drop-down. |
| **Default Value** | If specified, this value will be automatically entered for any new rows added to the table. |
| **Value Required** | If checked, the user will be unable to save edits to this table if a row has not specified a value for this column. |
| **Allow Unique Values only** | If checked, the user will be unable to save edits to this table if this column contains duplicate values. |

Refer to [Set Up Table Update
Schedule](table-update-schedule.html "Applies to: TBM Studio 12.6 and later") to publish info from Editable Table to a Standard Table.

- **[Table Functions](../../studio/data_studio/table-functions.html)**  
  **Applies to**: TBM Studio 12.0 and later
- **[GROUPBY](../../studio/data_studio/groupby.html)**
- **[Limit\_Columns](../../studio/data_studio/limit-columns.html)**  
  Determines the columns displayed in a table. You can limit columns using the **Ribbon**.
- **[SORT](../../studio/data_studio/sort.html)**  
  Sorts a table on one or more specified columns in the table. You can sort a table using the Ribbon. The !SORT function can be applied using one, two, or more columns in a table.
- **[Set up table-update schedule](../../studio/data_studio/table-update-schedule.html)**  
  **Applies to**: TBM Studio 12.6 and later
