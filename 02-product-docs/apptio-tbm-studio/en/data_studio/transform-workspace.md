---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "The data transform workspace"
breadcrumb: []
source_path: "data_studio/transform-workspace.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# The data transform workspace

Applies to: TBM Studio 12.0 and later. Use the data transform
workspace to import data and modify it to meet your data requirements.

The data transform workspace is divided into three panes.

- Project Explorer pane: Use to select a table you want to transform.
- Transform Steps pane: Use to add transform steps.
- Transform Step Details/Data Preview pane: Displays details about a
  transform step or displays the table after the current step is applied. The tabs running across the
  bottom of the Transform Steps and Transform Step Details panes are documents you have selected from
  the Project Explorer.

  ![](../../resources/images/studio_images/studioimages/studio_data_studio_transform_workspace_sui.png)

## Project Explorer

The Project Explorer pane displays the documents that are available. The
document types are:

- Tables
- Editable Tables
- Metrics
- Perspectives
- Published Tables
- Reports
- Time

When working with data, you will be focused on the Tables section.

To display the Project Explorer pane:

- In TBM Studio v12.1 and earlier, click the TBM Studio mode icon ![](../../resources/images/studio_images/studioimages/icons/studio%20mode.png) at the right side
  of the Global header.
- In TBM Studio v12.2+, open the Applications/Projects menu and click **TBM Studio**.

To change the width of the Explorer pane, drag the right border handle. To
minimize the Explorer panel, click the minimize arrow in the upper-right
corner of the panel.

## Expanding Filtered folders – Project Explorer

Applies to: 12.11.2 and later​

This feature allows you to filter and see which folder a table, editable table, perspective, or
report belongs. To enable this feature, navigate to Projects tab >
Enable Features, and then select Show Grouped Results in Project
Explorer checkbox.

![](../../resources/images/studio_images/en-feat.jpg)

To find a document in the Project Explorer, enter the search term in the
Project Explorer search bar, or select a pre-defined filter in the drop down. The search results
will be shown within their associated folder in an expanded view. The expanded folder view is not
applicable to Metrics and Time Section.

![](../../resources/images/studio_images/pe-expand-filter.png)

![](../../resources/images/studio_images/pe-filter.png)

Clearing the search term in the search Bar will automatically return to “All” view in the drop
down. ​

Note: The blue triangle ![](../../resources/images/studio_images/blue-ind.png)indicates that the system is querying the back end and results are yet to be returned.

## Tables section

The tables are grouped by category. By default, there is a General
category. There also will be other categories based on the application you are using, and custom
categories created by other users. You can create new categories when you create a new table.

To limit the tables displayed, use the filter shown below:

![](../../resources/images/studio_images/studioimages/studio_data_studio_transform_workspace_tables_sui.png)

## Table columns

To display the columns in a table, click the arrow to the left of the table name. In the example
below, the table is Servers Master Data.

The columns are Actual Units, Age, etc.

![](../../resources/images/studio_images/studioimages/studio_project_explorer_servers_master_data.png)

The symbol in front of a column name indicates the column type:

- (![](../../resources/images/studio_images/studioimages/icons/column%20type%20key.png))
  Key
- (![](../../resources/images/studio_images/studioimages/icons/column%20type%20label.png))
  Label
- (![](../../resources/images/studio_images/studioimages/icons/column%20type%20numeric.png)) Numeric
- (![](../../resources/images/studio_images/studioimages/icons/column%20type%20date.png))
  Date

The status of a document is indicated by the font:

- Plain: Checked in
- *Italics*: Checked out by another person
- Orange Bold: Checked out by you

## Table errors

(Applies to: TBM Studio v12.1, v12.2+.4)

When working with tables and the transform pipeline, a wide range of errors can occur. Some of
the typical errors are listed below.

- An appended table is missing
- A transform step references a missing column in a table

If a table has one or more errors, in the Project Explorer, a number is displayed to the right of
the table name indicating the number of errors. In the example below, the All Business Services
table has one error and the Cloud Service Provider table has four errors. When you display the table
pipeline, a number is displayed to the right of the step name, indicating the number of errors. When
you point to the number with the mouse cursor, a tooltip displays the error message:

![](../../resources/images/studio_images/studioimages/studio_project_explorer_errors_sui.png)

## Transform Steps pipeline

Add steps to the Transform Steps pipeline as needed.

- To display the Transform Steps pane, select a table from the
  Tables section of the Project Explorer.
- To add a step, move the cursor to the line dividing two existing steps and then click the plus
  sign at the right edge of the Transform Steps panel. Click the type of step
  you want to add. Some types of steps can be used only once in a pipeline, for example
  Data Partition. If the step already has been added to the pipeline, a banner
  will be displayed in the lower-left corner of the step option.

  ![](../../resources/images/studio_images/studioimages/studio_data_trans_add_step_sui.png)
- To change where a step occurs in a pipeline, drag the step to a new position in the pipeline.
  The following steps cannot be reordered: Source, Upload, Import, Table, Model.
- To minimize the Steps pane, click the arrow in the upper-right corner of
  the pane.
- To adjust the width of the Project Explorer pane, drag the divider handle
  on the right border.
- To save the transform steps, click the Home tab, and then click
  Save.
