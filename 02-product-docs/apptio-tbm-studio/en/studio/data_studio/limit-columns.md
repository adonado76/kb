---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Limit_Columns"
breadcrumb: []
source_path: "studio/data_studio/limit-columns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Limit_Columns

Determines the columns displayed in a table. You can limit columns using the
**Ribbon**.

## Syntax

`!LIMIT_COLUMNS[{columns to include}][{columns to
add}][{columns to exclude}][options]`

## Arguments

Columns to include
:   A comma-separated list of columns to be included in the table. This is the only required
    argument, but it can be empty. If it is empty, all columns in the table will be included.

    You can use dynamic text to reference a column in a table that is a comma separated list of
    columns. For example: !Limit\_Columns[<%=ABC Aggregation.Columns%>] would insert the list of
    columns in a column called Columns in a table called ABC Aggregation.

Columns to add
:   A comma-separated list of columns to add to the table. The columns must come from the data set
    used to generate the table.

Columns to exclude
:   A comma-separated list of columns to exclude from the table.

## Options

The following options are available:

| Option | Description |
| --- | --- |
| max:# | Sets the maximum number of columns that will be displayed. |
| onlyModeledMetrics | If the table being limited has metric columns, exclude these from the table. Only show modeled metric columns. |
| includePrimaryKey | Always include the Primary Key column regardless of the other settings. |
| showIrrelevant | Overrides the relevant column filter. |

## Example

Assume you have the following table.

![](../../resources/images/it%20planning_images/limit-columns.png)

The data path for the table is:

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Applications/
.Summary/
!LIMIT[0,2147483647]/
!LIMIT_COLUMNS[]/
```

You want to show only the Application, Service Level, and Support Tier columns. You edit
the!LIMIT\_COLUMNS line to look like the following:

`!LIMIT_COLUMNS[{Application},{Service Level},{Support Tier}]/`

## Ribbon

To limit the columns displayed using the **Ribbon**:

1. Select the table to be edited.
2. Select the **Properties** icon from the **Authoring** tab
   on the **Ribbon**.
3. On the **Data** tab of the **Properties** dialog, use the
   **Include** or **Exclude** fields to select the columns
   displayed.

**Parent topic:** [Editable tables: Accommodating user input](../../studio/data_studio/editabletables.html "Applies to: TBM Studio 12.6 and later")
