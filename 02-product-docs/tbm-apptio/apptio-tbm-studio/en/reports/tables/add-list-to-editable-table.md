---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Add a list to an editable table"
breadcrumb: []
source_path: "reports/tables/add-list-to-editable-table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add a list to an editable table

Applies to: TBM Studio 12.0 and later

If you want users to be able to select a value for a cell in an editable table, you can add a
list to the cell as shown in the following image. The values in the list are pulled from a table
column defined in the data set.

![](../../../resources/images/studio_images/studioimages/studio/reports-editable-table-drop-down-list-example.png)

In a list, the application displays the first 15 unique values in the source data. If the list
contains more than 15 values, a Find button is displayed at the bottom of the list. Clicking
the Find button displays a dialog where the user can select from the entire list of values.

## Create a basic list

1. From the Data tab, select the data set that is the source of the editable table.
2. In the Edit Columns tab, select the column that will supply the values for the drop-down
   list displayed in the cells.
3. In the Possible Values field in the Column Details pane, enter a list of
   comma-separated values, or enter the following formula to use a list of values from a column in a table:
   - Enter a selection statement:`%tablename /TableFunction[ ]`For the examples shown
     in the preceding image, the selection statement
     is:

     ```
     %Data Center Costs/!LIMIT_COLUMNS[Data
                   Center]
     ```
   - The selection statement uses values from the raw table shown below. The !LIMIT\_COLUMNS part of
     the statement tells the application to display only the Data Center column.

     ![](../../../resources/images/studio_images/studioimages/studio/reports-editable-table-drop-down-list-raw-table.png)
   - To provide additional context for users, you can enter any number of columns separated by
     commas. The first column in the list will be the value entered into the editable table.For
     example:

     ```
     %Data Center
                   Costs/!LIMIT_COLUMNS[Data Center,Remote Hands Cost, Data Center Power Cost,Data
                   Center Leasing Cost]
     ```
   - In the above example, a user can click Find… to see four columns in a pop-up selection dialog,
     although only the Data Center value will be stored in the editable table.
   - Also, you can use dynamic text in the Possible Values field to make the values displayed
     in the list dependent on the value in a column in the row. For more information, see [Generate a list with dynamic text](#Addalisttoaneditabletable__Generatealistwithdynamictext).
4. In the Possible Values Context field, select Report.
5. In the Column Details pane on the Edit Columns tab, select the Primary Key
   option. If you do not want to use the primary key of the lookup data table, you can use the !GROUPBY
   function in the Possible Values selection statement. The syntax is:`%tablename
   /!GROUPBY[column name]`

## Allow users to edit a list

If you want users to be able to edit the values in a list, create a data set with the default
values, and then copy and paste the raw data set table into a report. The table on the report will
be editable, and the users can add, edit, and delete entries in the table. Reference the data set in
the Possible Values field when you create the list.

## Generate a list with dynamic text

A list can contain values based on the value in another column in the table. For example, assume
you want users to be able to enter new data center names along with the state and city in which the
data centers are located. When a user clicks Add Row, they can enter a name for the data
center, select a state from a drop-down list, and then select a city within the selected state. Only
cities in the state selected are displayed. The three steps are shown below:

![](../../../resources/images/studio_images/studioimages/studio/aug257.png)

![](../../../resources/images/studio_images/studioimages/studio/aug258.png)

![](../../../resources/images/studio_images/studioimages/studio/aug259.png)

To create the lists:

1. Create a data set that includes the states and cities as shown in the following image:

   ![](../../../resources/images/studio_images/studioimages/reports/rep289.png)

   In our example,
   the data set is named States-Cities.
2. Open the data set that will incorporate the lists and select the Edit Columns tab.
3. Select the State column and enter the following in the Possible Values
   field:`%States-Cities/!LIMIT_COLUMNS[State]`This displays the values in the State
   column when a user clicks a cell in the column.
4. Leave the Possible Values Context field set to Report.
5. Select the City column and enter the following in the Possible Values
   field:`%States-Cities/!FILTER[State="<%=State%>"]/!LIMIT_COLUMNS[City]`The
   `!FILTER[State="<%=State%>]` part of the statement tells the application to look
   at the value in the State column and display only the cities that match the state.
6. In the Possible Values Context field, select Current Row.
