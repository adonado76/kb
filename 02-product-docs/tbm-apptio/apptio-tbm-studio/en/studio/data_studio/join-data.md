---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Join data"
breadcrumb: []
source_path: "studio/data_studio/join-data.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu544.png"
  - "resources/images/studio_images/studioimages/studio/stu545.png"
  - "resources/images/studio_images/studioimages/studio/stu690.png"
  - "resources/images/studio_images/studioimages/studio_join-data_data-centers-info.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Join data

**Applies to**: TBM Studio 12.0 and later

The **Join** step links the current table to other tables by matching values in a column in
the current table with values in a column in another table. This can be useful for reporting
purposes and for adding information to a table that will serve as a unit driver in a model. The
intent of the **Join** step is to produce a single table with all the data you need for
reporting.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu544.png)

The **Join** diagram displays the table of interest on the left and related tables to the
right. The percentages indicate the degree of match. The higher the percentage, the more entries in
the two tables that match.

The **Join** step in a transform pipeline comes after the **Table** step as shown below.
The **Table** step will not reflect the results of the join. However, all of the joined columns
will be displayed in **Project Explorer**:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu690.png)

## Join vs Append

A **Join** data transform step combines data from two or more tables into the same rows based
on common values in one or more columns. If you do not want to combine data into the same rows, use
the **Append** data transform step. An **Append** step adds rows to the table.

## Display table column details

To see column details for a table, click the **plus** sign. The table expands and shows the
match percentages for each column.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu545.png)

## View link details

To see the details for a link, click the link. Line items are displayed in **Unmatched**,
**Matched**, and **Reference** columns in a table below the diagram. The **Reference**
column refers to line items.

## Add a link

To add a link between two tables, click the **Add Link** button and complete the fields in the
**Add Link** dialog.

## Example

Assume you have the following two tables: **Data Centers Info** and **Data Centers
Hosting**. They both contain information about data centers, but the information is different in
each table. You want to combine them into a single table. They have one column with the same values:
Data Center. This column will be used to match the data in the two tables.

Data Centers Info

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_join-data_data-centers-info.png)

Data Centers Hosting

![](../../resources/images/studio_images/studioimages/studio_data%20centers%20hosting_table.png)

To join the two tables:

1. Open the **Data Centers Info** table in **Project
   Explorer** and add a **Join** step to the pipeline as shown
   below:

   ![](../../resources/images/studio_images/studioimages/studio_data%20centers%20info_join.png)
2. In the data relationship diagram, note there is a join between the **Data Centers
   Info** table and the **Data Centers Hosting** table, showing a 100%
   match.
3. Add a **Model** step to the Data Center Info table. The Data Centers Info
   table in Project Explorer now shows all the joined columns, including the Data Centers Hosting
   columns. You now can use the joined columns in a report table:

   ![](../../resources/images/studio_images/studioimages/studio_data%20centers%20hosting_model.png)

Note: In the pipeline, the **Table** step will not show the joined
columns.
