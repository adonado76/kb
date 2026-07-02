---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Unpivot data"
breadcrumb: []
source_path: "studio/data_studio/unpivot-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Unpivot data

**Applies to**: TBM Studio 12.0 and later

Sometimes it is useful to convert values in columns to additional rows. Use the **Unpivot**
pipeline step in a table to do this.

For example, the following table has columns for city, state, the population from the 2023
census, and the population from the 2020 census.

| City | State | 2023 | 2020 |
| --- | --- | --- | --- |
| New York | NY | 8258035 | 8804190 |
| Los Angeles | CA | 3820914 | 3898747 |
| Chicago | IL | 2664452 | 2746388 |

To convert the columns with the census values into rows:

1. **[Check
   out](../admin/navigate-tbm-studio.html#FindyourwayaroundTBMStudio__Checkoutandcheckin)** the table.
2. Add an **Unpivot** step to the table’s pipeline. For more information see [Transform Steps pipeline](transform-workspace.html#Thedatatransformworkspace__TransformStepspipeline).
3. Click **Configure Columns** and choose the columns you **do not** want converted to rows.
   In this example, we would choose "City" and "State".
4. Click **Save** in the ribbon.

This results in an output table with two columns: *Collapse Column* and *Collapse
Value*.

- **Collapse Column:** Includes values corresponding to the columns you did not choose.
- **Collapse Value:** Includes values from the columns that were converted to rows.

That output table looks like this:

| Collapse Column | Collapse Value | City | State |
| --- | --- | --- | --- |
| 2023 | 8258035 | New York | NY |
| 2020 | 8804190 | New York | NY |
| 2023 | 3820914 | Los Angeles | CA |
| 2020 | 3898747 | Los Angeles | CA |
| 2023 | 2664452 | Chicago | IL |
| 2020 | 2746388 | Chicago | IL |

## Important notes

**Avoid mixing column types**

If the columns which are not selected include columns of both numeric and label types the
resulting “Collapse Value” column will be mixed numeric and label values. This can lead to issues
later in the table’s pipeline or in other tables based upon the one with the Unpivot step.

Examples of the types of issues which can occur include a column being unavailable to choose in a
Model step's identifier, or numeric values in the column not being summable.

If you need a column with mixed numeric and label values, we recommend you insert a Formula step
after the Unpivot step and edit the existing column to override the column type to be a label.
Please see the [Edit a column](add-edit-columns.html#Addandeditcolumns__Editacolumn) documentation for
more information.

**Avoid excessive row expansion**

Using the Unpivot step expands row count by an amount equal to the number of rows before the
Unpivot step times the number of columns being converted to rows. For example, if the row count
before Unpivot is 10 rows, and you Unpivot 2 columns, then the row count after Unpivot will be: 10 +
(2 \* 10) = 30.

Because the Unpivot step lets you specify the columns which should *not* be converted to
rows, if the data source changes to include additional columns, this can result in unexpected row
expansion depending on the properties of the data. This can lead to performance challenges like
slowness to load in TBM Studio, or longer calculation times for the project the table is in. The
degree of the performance impact varies with the number of rows resulting from the pivot, and how
the table is used downstream.
