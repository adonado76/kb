---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Add a calculated column to a table"
breadcrumb: []
source_path: "reports/tables/add-calculated-column.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add a calculated column to a table

Applies to: TBM Studio 12.0 and later

If you have added fields to the Values area of the Component
Configuration pane, you can add calculated columns to the table based on the values.
There are three types of calculated columns:

- Values - These are calculated values based on an existing column in the
  table. Examples include Count, Percent, and Sum. The calculations available will depend on the
  column you select.
- Comparison - Compares values in a column to the same values from another
  project. This is useful for year-over-year comparisons.
- Variance - Displays the difference between two columns in the table.

## Add a values column

1. Select the table.
2. In the Component Configuration pane, right-click on a field in the
   Values area and click Value Field Settings. The
   application displays the Value Field Settings dialog shown in the following
   image:

   ![](../../../resources/images/studio_images/studioimages/reports/rep183.png)
3. Select the type of calculation. For a description of the types of calculations, see *Types of
   calculations* below.
4. If you wish to replace an existing column with the calculated values, clear the **Add a new
   value field** option.

## Types of calculations

The calculations available depend on the value selected. Several of the most common types of
calculations are described below. To see a pop-up description of a calculation in the product, hover
the mouse pointer over the name of the calculation.

- Count - Returns the number of entries represented by a row. In ungrouped
  tables, the value will be 1. In grouped tables, this will be the number of entries represented by a
  various () entry in the source column. An example is shown in the following image.

  ![](../../../resources/images/studio_images/studioimages/studio/stu613.png)
- Percent - Adds a column to the table that displays the percent each entry
  in a column contributes to the total value of the column. The default name of the column will be the
  name of the original column followed by the % sign. An example is shown in the following
  image.

  ![](../../../resources/images/studio_images/studioimages/studio/aug436.png)
- Threshold Icons - Displays red and green icons based on a threshold
  value. A red icon is displayed for values below the threshold. A green icon is displayed for values
  above the threshold. An example is shown below. The default name of the column will be the name of
  the original column followed by the letter T:

  ![](../../../resources/images/studio_images/studioimages/studio/aug435.png)
- Zero Arrows - Displays an up arrow for values greater than zero, a
  sideways arrow for values equal to zero, and a down arrow for values less than zero.

  ![](../../../resources/images/studio_images/studioimages/studio/aug457.png)
- Sparkline Trend - Displays a small trend graph that covers the last six
  months. An example is shown in the following image.

  ![](../../../resources/images/studio_images/studioimages/studio/aug456.png)

## Add a cross-project comparison column

To compare figures across projects, add a cross-project comparison column to the table. For
example, you might want to compare server costs from the current project with server costs from the
previous year. Comparison columns must be based on a metric.

To add a comparison column:

1. Select a column in the table and click the Comparison icon in the
   Formulastab, or right-click in a column heading and select Add
   Comparison Column from the pop-up menu. The application displays the dialog shown in the
   following image

   ![](../../../resources/images/studio_images/studioimages/studio/stu614.png)
2. Enter a name for the new column.
3. Select the source project from the drop-down list.
4. Select the display option: source value or difference.You can add both a source and a difference
   column in the same table.
5. Click OK.

## Add a variance column

A variance column calculates the difference between two columns in a table. For example, if you
have a budget column and an actuals column in a table, you can add a variance column to show the
difference.

To add a variance column:

1. Hold down Ctrl and select the two columns in the table. The second column
   you select will be subtracted from the first column you select.
2. Click the Variance icon on the Formulas tab. The
   application displays the Create New Column dialog shown in the following
   image. It subtracts the value of the second column from the first column from the first
   column.

   ![](../../../resources/images/studio_images/studioimages/reports/rep217.png)
3. Enter a name for the column.
4. Review the formula and modify it if appropriate.
5. Select the format for the column. The Grouping Separator is the character
   that sets off "thousands."
6. Select a type.
   - Automatic: The application picks a format based on the contents of the
     column.
   - Numeric: Integer or real number.
   - Label: Text. You cannot perform mathematical operations on Label
     columns.
   - Date: Date information.
7. If appropriate, check the Summable option. When checked, this specifies
   that the column can be safely summed when being grouped or totaled. Normally, values are
   recalculated. This allows a global lookup (that references the key being used to group the data) to
   properly total. Do not select this option if the value formula performs calculations, or the result
   will be incorrect. If you plan to add subtotals to the table, and you do not want subtotals
   displayed for the column, leave this field unchecked.

## Add a spacer column

If you want to insert a blank Spacer column in a table for aesthetic
reasons, select the table, click the Data tab, and click Insert
Spacer Column from the Insert icon menu.
