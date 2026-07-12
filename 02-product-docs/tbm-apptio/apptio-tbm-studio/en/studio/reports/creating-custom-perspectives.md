---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Create custom perspectives"
breadcrumb: []
source_path: "studio/reports/creating-custom-perspectives.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu555.png"
  - "resources/images/studio_images/studioimages/studio/stu609.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create custom perspectives

**Applies to**: TBM Studio 12.0 and later

To augment the standard sections in the **Project Explorer**, you can create
custom perspectives. In the following image, there is one custom perspective: **ABC Company
Analytics**. A custom perspective contains selected fields from the other perspectives you
want to make available to business users.

![Project Explorer](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu555.png)

To create a custom perspective and add fields to the perspective:

1. Right-click in the **Perspectives** section of **Project
   Explorer** and select **Add New Perspective**.
2. In the **Create Perspective** dialog, enter the name of the perspective and
   click **OK**.

Analysts see only the custom perspectives and the **Time** perspective in the
**Project Explorer**. All analysts see all custom perspectives. You cannot create different sets
of custom perspectives for different groups of analysts. Custom perspectives are listed in
alphabetical order at the top of the **Perspectives** area.

## Add a field to a custom perspective

To add a field to a custom perspective:

1. Perform one of the following actions:
2. Drag a field from the **Tables**, **Metrics**, or
   **Time** sections onto the title bar of the **Perspectives**
   section in the **Project Explorer**.
3. Drag a field from an area in the **Component Configuration** panel to the
   title bar of the **Perspectives** section in the **Project
   Explorer**.
4. Right-click a field in the **Component Configuration** panel and select **Publish**.![Publish Field](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu609.png)
5. Complete the fields and click **Publish**. The fields are described
   below:

## **Field descriptions**

- **Name** - The name of the field. You can accept the default name or change
  the name.
- **Data Type** - Select a data type from the list. The type controls the basic
  formatting of the data.
- **Represents a hierarchy code** - Applies only to slicers. When checked, and
  the published field is used to define a slicer, it finds all values that begin with the search
  characters entered by the user plus one additional character and creates a slicer group for each.
  For example, if the user types "ab," then the filter will find "aba," "abc," and "abd" and will
  create groups for each. For a more detailed discussion of this option, see [Represent a hierarchy code in
  perspectives](hierarchy-codes-perspectives.html "Applies to: TBM Studio 12.0 and later").
- **Show all rows in time-based query** - When checked in, if a table or chart
  is time-based (e.g.: months, quarters, etc.), all rows will be displayed in all periods even if one
  or more periods contain rows with zeros in all fields. For a more detailed discussion of this
  option, see [Show all rows in time-based query option](#Createcustomperspectives__Showallrowsintimebasedqueryoption) below.
- **Description** - The text entered in the field is displayed as a tool tip
  when a user hovers the mouse pointer over the field. Use this field to provide information to
  analysts about the data represented by the field. This is important because the analysts may not be
  familiar with the data sets in the project and the name of the field may not convey the contents.
  Entering a complete explanation of the data will help analysts use the field effectively when
  building tables and charts.
- **Notes** - Information for other Power Users that may edit the field. The
  information is available only in this dialog.
- **Filter** - This field is displayed if you are publishing a field from the
  **Filter** area. This is a non-editable field.
- **Formula** - This field is displayed if there is a formula associated with
  the field. You can edit the formula.

## Show all rows in time-based query option

Some time-based tables may have one or more rows that do not have values for one or more time
periods. By default, rows without values are not displayed. To ensure that all rows will be
displayed in all periods, check the **Show all rows in time-based query**
option.

For example, assume you have the following data:

**Jan FY2011**

| Column A | Column B |
| --- | --- |
| X | 1 |
| Y | 2 |
| Z | 3 |

**Feb FY2011**

| Column A | Column B |
| --- | --- |
| X | 4 |
| Z | 3 |

You have two calculated metrics: Cost and YearToDate(Cost). You add Cost and YTD columns to the
table to display the metrics.

During February, there will be no row Y displayed:

| Column A | Cost | YTD |
| --- | --- | --- |
| X | $4 | 5 |
| Z | $3 | 6 |

However, if you have checked the option, row Y will be displayed:

| Column A | Cost | YTD |
| --- | --- | --- |
| X | $4 | 5 |
| Z | $3 | 6 |
| Y |  | 2 |

## Rename a custom perspective

To change the name of a custom perspective, right-click the custom perspective and click
Rename.

## Create field groups

You can group fields in a custom perspective.

1. Right-click in a custom perspective and select **Add New Group**.
2. Drag fields from an area onto the group.

To remove a field from a group, drag it into a blank area of a custom perspective.

## Delete a field

To delete a field from a custom perspective, right-click the field and click **Delete
Field**.

## Delete a perspective

To delete a perspective, right-click the Perspective title bar and select Delete.

## Create an Admin-only perspectives

If you are assigned to an Admin role, you can create perspectives that are visible only to other
users with Admin roles. This is useful for creating a place where you can store frequently used
fields you do not want analysts to access.

To create an Admin-only perspective, put parentheses around the perspective's name.
