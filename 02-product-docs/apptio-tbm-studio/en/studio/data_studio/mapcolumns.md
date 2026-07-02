---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Map Columns"
breadcrumb: []
source_path: "studio/data_studio/mapcolumns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Map Columns

**Applies to**: TBM Studio 12.7 and later. Applications available in
TBM Studio require aligning data to master data sets. A new pipeline step **Map
Columns** is available to all customers with version 12.7.

**Map Columns** can be added to a checked-out table other than master
data sets themselves. After adding the step, a destination is requested. Any mapped information is
added to the destination table in a new "Mapped Tables" step on master data sets. Master data sets
are the only valid destinations.

Tip: After you upload a source data table and
transform it, if necessary, you can map it to a master data table. If you are running TBM Studio
12.7 or later, Apptio recommends you use the Map Columns feature, described here, to map data
(except for Cloud). If Map Columns is not an option for you, see the alternative methods described
here: [Map data to a master data table](../../cost-transparency/configuration/maptomaster.html "(Opens in a new tab or window)") and [Cloud
mapping](../../cost-transparency/configuration/cloudmapping.html "(Opens in a new tab or window)").

**Prerequisites**

- Components must be installed in order to map to their master data sets.
- Master data sets must be in content versions 104 or later.

## Add the Map Columns pipeline step and choose a destination

1. Create or check out a table and add data into the table. Also, you can apply transformative
   pipeline steps, such as Date Partition.
2. Hover over the pipeline steps, then click **+** to add a new pipeline step.
   **Map Columns** becomes available unless there is a Model step added.![](../../resources/images/studio_images/studioimages/studio_add%20step_map%20columns.png)

   Note: If
   the table was reverted and the data upload was not, the step will not be available until you add any
   other step and then add Map Columns.
3. Click **Map Columns**, then select a destination. If you don't see the master
   data set you were expecting, go to **Components** and install the necessary
   component.![](../../resources/images/studio_images/studioimages/studio_map%20columns_destination.png)

## Map to a master data set column

1. Review the Destination Columns. These are the columns in the master data sets that can be mapped
   to. Some may already be mapped because a column header in your table matches an expected value in
   the destination.
2. Select **Choose source** in the Source Column, or to change a mapping, select
   one of the other values in that column.![](../../resources/images/studio_images/studioimages/studio_map%20columns_cost%20center.png)
3. Choose one of the column names in the drop-down list. This list shows all columns in the table
   with a matching column type to the destination.

   Note: The following preview table will not be updated
   until the change is saved.

   Tip: If you don't see the columns you want in the
   drop-down list, then they might not be of the right matching type for the destination. Go to the
   Import step and change the Type Override option as necessary. If the expected column was created in
   the transform pipeline, use or change the Formulas step.
4. To enter a string or number for all rows, choose **Enter a fixed value for all
   rows**. As a result, every row in the table shows the same value for that column. This
   option does not evaluate formulas. To use a formula, add the **Formulas** step,
   then map the resulting additional column.
5. Enter the value, then click **OK**.You have now mapped two additional columns
   to the master data set by choosing a column from your table and by entering a value.

## Add a custom column to the master data set

1. To add a column that does not exist in the master data set, click **Add Custom
   Column**. These additions will be maintained between upgrades without any special
   actions.
2. Enter the name of the column you want to add, then choose the type. Select a source for that
   column, either by choosing another column in the table or a fixed value.
3. Click **OK**. Added columns are always optional. Save the table to see the
   column in the preview.

## Use Join to map columns

1. Use the **Join** step to map columns where another data set has additional
   information that can be matched to data in the mapped table. To use this feature, click
   **Join**.
2. Click **Add Link**, then choose the table to which you want to join or drag
   the table from the **Tables** section of the **Project
   Explorer** and draw a line to it. **From Column** and **To
   Column** represent a key relationship where the values are expected to match.![](../../resources/images/studio_images/studioimages/studio_map%20columns_add%20link.png)
3. Select the appropriate columns, then click **OK**.

   Note: The preview will not
   update until you click **Save**.
4. Click **Map Columns**, then select a column you want to map. The newly mapped
   columns appear in the drop-down list with the name of the table, “.", then the name of the column.
   The columns also appear in the **Unmapped Columns** tab:![](../../resources/images/studio_images/studioimages/studio_map%20columns_chart%20of%20accounts%20master%20data.png)
5. Select the intended column, then save to update the preview table.

## Navigate in Map Columns

1. At the upper right, use **Search All Fields** to search the Destination
   Column, Source Column, and Description Column.
2. Click each column header to sort the order of each column or reverse the sort order of each
   column.
3. The preview table shows the results of column mapping when at least one column is mapped or the
   unmapped table if nothing is mapped. When some but not all columns are mapped, the default tab shows
   what has been mapped, and "Unmapped Columns" is available in tabs.

## View Mapped Tables in master data sets

- To view all the tables that are sending data to the master data set, navigate to the appropriate
  master data set, then choose **Mapped Tables**.![](../../resources/images/studio_images/studioimages/studio_cost%20source%20master%20data_mapped%20tables.png)
- In the Preview table, the **Source Table** column identifies which table the
  row came from. Use the **Autosearch Filter** to see all the rows from one
  source.![](../../resources/images/studio_images/studioimages/studio_mapped%20tables_source%20table.png)
- Use the table in Mapped Tables to navigate to the source table and show the following information:
  - Name of the table that contains the matching Map Columns step.
  - The last time the table was changed.
  - The row count from the mapped table.
  - The number of columns marked as Required that were added.
  - The number of columns in the master data set that were mapped overall.
  - The number of columns that were added to the master data set.
  - The description of the table added to the master data set. Adding a description to your tables
    will ensure easier maintenance and is highly recommended for any tables to be mapped to a master
    data set with more than one mapped table.

## Application upgrades and Map Columns

When new application content is released, you can upgrade projects to receive the changes. For
more information, see [About upgrading Cost Transparency](../../cost-transparency/configuration%20-%20additional/aboutupgradingct.htm "(Opens in a new tab or window)").

Map Columns always shows information for the same application content version as the master data
set. If the component was updated but the master data set is customized, no changes will occur.
Minor updates, such as column descriptions, may occur at any time.

To update a master data set, go to Components and choose the Component containing that master
data set. Scroll to **Customized Elements**. In the list, find the name of the
master data set, then click the **arrow** to the left.

![](../../resources/images/studio_images/studioimages/studio_comp_app%20dev.png)
