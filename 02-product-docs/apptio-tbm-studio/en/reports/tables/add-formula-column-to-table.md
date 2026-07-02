---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Add a formula column to a table"
breadcrumb: []
source_path: "reports/tables/add-formula-column-to-table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add a formula column to a table

**Applies to**: TBM Studio 12.0 and later

You can add a formula column to a table. The column can be based on a custom formula, the columns
in the data set backing the table, or a modeled value. For example, you might want to perform some
complex calculations based on two or more columns in the table. When referring to columns in a
table, be sure to use the table.column format for column names.

## Add a formula column

A formula column gets value from other columns in the table and from calculations. When referring
to columns in a table, be sure to use the table.column format for column names.

To add a formula column to a table:

1. Select the table.
2. On the **Data** tab, open the **Insert** menu and then click **Insert Formula Column**.
   The **Create New Column** dialog is displayed as shown in the following image:![](../../../resources/images/studio_images/studioimages/reports/rep164.png)

   Note: If you click
   **Insert** on the **Data** instead of opening the menu, a blank column named
   **MyNewColumn** is added to the table. To add a formula to the column, click the column name to
   highlight it, and then click **Edit** on the **Data** tab.
3. Complete the fields using the information provided in the table below.
   - **Name** - Accepts all standard alpha numeric characters.
   - **Enter Formula** - Any formula that follows the report formula syntax. When using columns in
     formulas, be sure to use the *table.column* format for the name of a column. As you begin
     typing in the field, the application will display a list of values that match what you have typed.
     For information on syntax, see [../../formulas-and-functions/formulas%20and%20functions%20guide%20title.htm](../../formulas-and-functions/formulas%20and%20functions%20guide%20title.htm "(Opens in a new tab or window)")[Syntax
     for formulas and functions](../../formulas-and-functions/syntax-for-formulas-and-functions.htm#top). Note that, Enriched Editable table will support selection of
     Formula column as Primary Key.
   - **Text Value** - Select this option to use data from a text column in the table.
   - **Numeric Value** - Select this option to use data from a number column in the
     table.**Modeled Value** - Select this option to use data from a driver. This option is available
     only for tables in auto-generated object reports.**Format** - Select the appropriate format. If
     you select **Advanced**, you can enter a formula that sets the format.
   - **Format** - Select the appropriate format. If you select **Advanced**, you can enter a
     formula that sets the format.
   - **Type** - Select one of the four column types:
     - **Automatic** - The application picks a format based on the contents of the column.
     - **Numeric** - Integer or real number.
     - **Label** - Text. You cannot perform mathematical operations on Label columns
     - **Date** - Date information.
   - **Summable** - When checked, specifies that the column can be safely summed when being
     grouped or totaled. Normally values are recalculated. This allows a global lookup (that references
     the key being used to group the data) to properly total. Do not select this option if the value
     formula performs calculations, or the result will be incorrect.If you plan to add subtotals to the
     table, and you do not want subtotals displayed for the column, leave this field unchecked.

## Edit a formula column

If you have added a formula column to a table, you can edit the column by selecting the column
and clicking **Edit** on the **Data** tab. The application displays the **Edit Column**
dialog which is identical to the **Create New Column** dialog shown in Figure A above. Note that
for numeric, currency, and percent columns, you can set the number of decimal places. The **Use
Grouping Separator** option adds the appropriate "thousands" separator (comma, period, or space)
to the number based on the locale set for the project.

## Edit a formula

You can edit the formula for a column using the Formula bar in the report edit pane as shown in
the following image. As you edit the formula, you will be prompted with a list of available
functions, object names, tables, and columns. Select an entry in the list with the mouse or arrow to
the entry and press the Tab key. To save a formula, click the save icon ![](../../../resources/images/studio_images/studioimages/icons/formula-save.png) to the left of
the Formula bar.

![](../../../resources/images/studio_images/studioimages/reports/rep340.png)

## Hide a formula column

You can hide a formula column that you have added to a table. To hide a column, right-click on
the column in the **Rows** or **Values** area of the **Competent Configuration** panel and
select **Hide**.

## Delete a formula column

1. Select the table.
2. In the **Component Configuration** dialog, drag the column name out of the **Values**area.
