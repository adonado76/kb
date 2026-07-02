---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Append data"
breadcrumb: []
source_path: "studio/data_studio/append-data.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu001.png"
  - "resources/images/studio_images/studioimages/studio/stu005.png"
  - "resources/images/studio_images/studioimages/studio/stu006.png"
  - "resources/images/studio_images/studioimages/studio/stu007.png"
  - "resources/images/studio_images/studioimages/studio/stu008.png"
  - "resources/images/studio_images/studioimages/studio/stu010.png"
  - "resources/images/studio_images/studioimages/studio/stu011.png"
  - "resources/images/studio_images/studioimages/studio/stu511.png"
  - "resources/images/studio_images/studioimages/studio/stu512.png"
  - "resources/images/studio_images/studioimages/studio/stu660.png"
  - "resources/images/studio_images/studioimages/studio/stu661.png"
  - "resources/images/studio_images/studioimages/studio/stu662.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Append data

**Applies to**: TBM Studio 12.0 and later

You can add data from one or more source tables to a target table using the
**Append** data transform step. The **Append** step always
adds rows from the source table to the target table.

When you append data:

- When data is appended to the target table, the appended data is added as new rows in the target
  table. Rows from the source and target tables are never combined. To combine rows, use a
  **Join** data transform step.
- Columns in a source table can be mapped to existing columns in the target table.
- Columns in a source table can be added to the target table as new columns.
- Appends apply to the current version of the table. When a period outside of the
  versioned-table-date span is selected, the append is locked.

If you want to merge data in tables without creating new rows, you should use a [Join](join-data.htm "(Opens in a new tab or window)") step. Also, you can create new
columns in the target table and pull data from the source tables using the
**Lookup** function. For more information, see [Lookup and Lookup\_Wild functions](../formulas-and-functions/functions/lookupandlookup_wild.htm "(Opens in a new tab or window)").

## Example

Assume you have the following two tables that have matching columns:

Table 1

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu660.png)

Table 2

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu661.png)

If you append Table 2 to Table 1, you will get the following table:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu662.png)

The general steps to perform an append are described below:

- Check out the target table.
- Add the **Append** step to the data transform.
- Select a source table.
- Map columns in the source table to columns in the target table or use formulas.
- Optionally, add columns from the source table.

## Check out the target table

The target table will accept data from one or more source tables. The target table must be a
transform table.

To check out the target data set:

1. In the **Tables** section of the **Project Explorer**,
   click the target table.
2. Add the **Append** step to the transform pipeline.

## Select a source data set

1. Click **Append Data Source**.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu511.png)
2. Click the name of the source table and then click **Next**.The
   **Append** dialog box is displayed as shown in the following image:

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu005.png)

## Map columns

The key elements in the mapping dialog shown in the preceding image are described below:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu006.png)

The column on the left displays the target columns. Icons and colors indicate the column type:
key, label, date, numeric. An asterisk indicates that the column has been marked as required. In
this context, *required* means that the column is needed to fully light up models and reports
based on the data. However, you can perform the append without mapping the column.

A green check mark indicates that the column has been mapped.

You can filter the column on the left by selecting a column type from the legend in the
upper-right corner of the dialog. By default, all columns are displayed.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu007.png)

The column on the right displays columns from the source table. If a column name in the source
table matches a column name in the target table, the name of the target column is displayed.
Matching is not case sensitive.

The column on the right contains drop-down lists for selecting source columns. The columns
displayed in the list are based on the target column type. For example, if the list is for a key
column, only key columns in the source data set will be listed:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu008.png)

You can enter formulas in the drop-down fields, beginning with =. You may want to use a formula
if the column you want to map in the source table does not match the column type in the target
table. If you enter a column with a name that includes special characters, enclose the column name
in curly brackets { }.

To help you match columns, the target and source tables are displayed at the bottom of the dialog
in separate tabs:

![](../../resources/images/studio_images/studioimages/studio_append%20data_acme%20gl.png)

To map a column:

1. If there are many columns in the table and you want to limit the columns displayed, select a
   column type from the key in the upper-right corner of the dialog.
2. Open the drop-down list in the column on the right and select a source column.If the column you
   want to map in the source table does not match the column type in the target table, enter a
   formula.

   **Examples**:`={column name}`

   ```
   =If({Cost
                   Pool} IN ("FTE Labor","Depreciation"),"Fixed","Variable")
   ```

   ```
   =Lookup(ACCOUNT,Chart of Accounts,ACCOUNT,Cost
                 Pool)
   ```

   You can map key columns to label columns and vice versa.

To add one or more source columns to the target table:

1. Click the **Select additional source column** link below the target and
   source columns.
2. In the **Select Columns** dialog, select the columns you want to add and
   click **OK**.

## Review data sources

After you append one or more source data sets to a target table, they are listed in the step
pane. The pane displays information about the appended data sets, including the number of required
columns in the source data set that have been mapped to the target data set. If there are no
required columns, the **Required Columns** column will not be displayed. In the
image below, there are no required columns:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu512.png)

There are several actions you can perform from the pane:

- **Edit** - Edit the append mapping
- **Remove** - Remove the appended data set
- **Append data source** - Append another data source

## Append example 1

Assume you have the following two tables that have matching columns:

Table 1

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu660.png)

Table 2

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu661.png)

If you append Table 2 to Table 1, you get the following table:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu662.png)

## Append example 2

Assume you have the two tables shown below. You want to combine them into a single third table
called **Machine CMDB**, preserving the **RAM** column in the
Virtual Machines data set. Also, you want to map the **Virtual ID** column to the
**Asset Tag** column.

Virtual machines

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu010.png)

Physical machines

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu001.png)

When you are done, you want the appended data set to look like the following:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu011.png)

To perform the append:

1. Make a copy of the **Virtual Machines** table to create the
   **Machine CMDB** table.
2. Check out the **Machine CMDB** table and add an **Edit
   Columns** transform step.
3. Set all columns to **Label** accept the **Hostname**
   column. The **Hostname** column should be **Key**.
4. Add an **Append** step to the transform after the **Edit
   Columns** step.
5. Click **Append Data Source** and click the Physical Machines data set and
   click **Next**. Note, the **Hostname** and **Virtual
   Type** columns are mapped automatically.
6. The **Asset Tag** column in the **Physical Machines**
   table is *numeric*, but the **Virtual ID** field in the **Machine
   CMDB** data set is *label*. **Asset Tag** will not be listed in
   the drop-down list because it is a different column type than the **Virtual ID**
   field. To map the **Asset Tag** column to the **Virtual ID**
   column in the **Machine CMDB** data set, add the pm- prefix by entering the
   following formula in the drop-down list field: `="pm-"&{Asset Tag}`
7. Click **Save**.
