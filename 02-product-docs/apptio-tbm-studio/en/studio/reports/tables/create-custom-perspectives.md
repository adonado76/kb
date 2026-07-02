---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Create custom perspectives in reports"
breadcrumb: []
source_path: "studio/reports/tables/create-custom-perspectives.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu626.png"
  - "resources/images/studio_images/studioimages/studio/stu627.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create custom perspectives in reports

**Applies to**: TBM Studio 11.0

To augment the standard **Tables**, **Metrics**, and **Time** perspectives, you can
create custom perspectives. In the illustration below, there is one custom perspective: ABC Company
Analytics. A custom perspective contains selected fields from the other perspectives that you want
to make available to business users. An advantage of custom perspectives is that you can add fields
from several different tables and lock the fields to the table. This makes it possible to build
reports that contain data from several tables at different levels in a model. In addition, it is
best to use only fields locked to tables in your production reports.

![custom perspectives](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu626.png)

Watch these demo videos from Apptio Education Services:

- [Create a
  Custom Perspective](https://community.apptio.com/videos/1892 "(Opens in a new tab or window)")
- [Add a Rate
  Column](https://community.apptio.com/videos/1893 "(Opens in a new tab or window)")

Or, browse [all Apptio videos](https://community.apptio.com/docs/DOC-7714 "(Opens in a new tab or window)").

## Create a custom perspective

To create a custom perspective and add fields to the perspective:

1. Right-click in the **Perspectives** section of **Project
   Explorer** and click **Add New Perspective**.
2. In the Create Perspective dialog, enter the name of the perspective and click OK.

## Add a field to a custom perspective

To add a field to a custom perspective:

1. Drag a field from the **Tables**, **Metrics**, or
   **Time** sections in the **Project Explorer** to the
   **Perspectives** header in the **Project Explorer**.
2. When prompted, select a perspective and click **OK**.
3. Complete fields in the Publish Field dialog box.![Publish Field](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu627.png)
4. Complete the fields and click **Publish**. The fields are described
   below.

**Field descriptions:**

- **Name** - The name of the field. You can accept the default name or change
  the name. If you will be locking the object, a best practice is to include the name of the object in
  the field name.
- **Data Type** - Select a data type from the list. The type controls the basic
  formatting of the data.
- **Lock to object** - This field is displayed when you publish a Data field.
  When checked, it ensures the field will be applied only to the object selected when it was added to
  the perspective. If you do not check this option, the field will apply to the currently selected
  object report.
- **Represents a hierarchy code** - Applies only to slicers. When checked, and
  the published field is used to define a slicer, it finds all values that begin with the search
  characters entered by the user plus one additional character, and creates a slicer group for each.
  For example, if the user types "ab", then the filter will find "aba", "abc", and "abd" and create
  groups for each. For a more detailed discussion of this option, see [Representing hierarchy
  codes in perspectives](../hierarchy-codes-perspectives.htm "(Opens in a new tab or window)").
- **Show all rows in time-based query** - When checked, if a table or chart
  that is time-based (e.g.: months, quarters, etc.), all rows will be displayed in all periods even if
  one or more periods contain rows with zeros in all fields.You must check this option on all
  calculations that include a function that pulls data from other time periods. For example,
  PreviousYear and YearToDate. For a more detailed discussion of this option, see [Show all rows in time-based query](#Createcustomperspectivesinreports__Showallrowsintimebasedqueryoption).
- **Description** - The text entered in the field is displayed as a tool tip
  when a user hovers the mouse pointer over the field. Use this field to provide information to
  analysts about the data represented by the field. This is important because the analysts may not be
  familiar with the data sets in the project and the name of the field may not convey the contents.
  Entering a complete explanation of the data will help analysts use the field effectively when
  building tables and charts.
- **Notes** - Information for other power users that may edit the field.
- **Filter** - This field is displayed if you are publishing a field from the
  **Filter** area. This is a non-editable field.
- **Formula** - This field is displayed if there is a formula associated with
  the field. You can edit the formula.

## Show all rows in time-based query option

Some time-based tables may have one or more rows that do not have values for one or more time
periods. By default, rows without values are not displayed. To ensure that all rows will be
displayed in all periods, check the **Show all rows in time-based query** option.

For example, assume you have a table backed with the following data in January and February:

Jan FY2016

| **Column A** | **Column B** |
| --- | --- |
| X | 1 |
| Y | 2 |
| Z | 3 |

Feb FY2016

| **Column A** | **Column B** |
| --- | --- |
| X | 4 |
| Z | 3 |

You have two calculated metrics: Cost and YearToDate(Cost). You add Cost and YTD columns to the
table to display the metrics.

When you are in February, there will be no row Y displayed.

| **Column A** | **Cost** | **YTD** |
| --- | --- | --- |
| X | $4 | 5 |
| Z | $3 | 6 |

However, if you have checked the option, row Y will be displayed.

| **Column A** | **Cost** | **YTD** |
| --- | --- | --- |
| X | $4 | 5 |
| Z | $3 | 6 |
| Y |  | 2 |

In addition, you must check this option on all calculations that include a function that pulls
data from other time periods. For example, PreviousYear and YearToDate.

## Rename a custom perspective

To change the name of a custom perspective, right-click the perspective name and click the
**Rename** option.

## Create a dimension

You can group fields in a custom perspective.

To create a field group and add dimensions to the group:

1. Right click a custom perspective and click Add New Group.
2. Drag dimensions from an area into the group.

## Delete a dimension

To delete a dimension from a custom perspective, right-click and click **Delete Field**.

## Delete a perspective

To delete, right-click the perspective title bar and select Delete.

## Create an Admin-only perspective

If you are assigned to an Admin role, you can create perspectives that are visible only to other
users with admin roles. This is useful for creating a place where you can store frequently used
dimensions that you do not want analysts to access.

To create an Admin-only perspective, put parentheses around the perspective name.
