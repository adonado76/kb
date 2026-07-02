---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Use the performance review component"
breadcrumb: []
source_path: "studio/admin/use_the_performance_review.html"
images:
  - "resources/images/ai_images/analyze-performance.png"
  - "resources/images/studio_images/revert-project-setting.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Use the performance review component

Applies to: Apptio TBM Studio 12.5 and later. The Performance Review component is an
in-application utility that creates reports that an Apptio TBM Studio Administrator can use to gain
insight into the impact their current project configuration has on application performance. This
component is available in R12.5 and later and was part of the v.105 content payload.

This document provides an overview of the reports that are installed by the Performance Review component.

- For installation instructions, see [Install the Performance Review component](install-performance-review.html "Applies to: Apptio Costing Standard on TBM Studio 12.5 and later. The Performance Review component is an in-application utility that creates reports that an Apptio TBM Studio Admin can use to gain insight into the impact their current project configuration has on application performance.")
- For more detailed information on configuration performance tuning, see [Improving performance in your R12 projects](https://community.apptio.com/viewdocument/improving-performance-in-your-r12-p "(Opens in a new tab or window)")

## Upgrade the Performance Review component

Follow these instructions if the performance review component is already installed. If it is not,
you need to install the component. For more information, visit [Install the Performance Review
component](install-performance-review.html "Applies to: Apptio Costing Standard on TBM Studio 12.5 and later. The Performance Review component is an in-application utility that creates reports that an Apptio TBM Studio Admin can use to gain insight into the impact their current project configuration has on application performance.").

1. On the Project tab in the Project Setup group, select **Project
   Settings**.
2. In the Components Version drop-down list, select **Version 110** (or the
   latest), then click **Save**.
3. On the Project tab, in the Project Data group, select **Components**. You
   should now see the Performance Review component.
4. Select **Performance Review**.
5. If, at this point, you see messages indicating that there have been customizations, you need to
   **Revert** those. To revert, scroll to the bottom of the **Analyze
   Performance Component** page. If there are customizations present, select the revert arrow
   next to the customized component entry to revert. After reverting any component customizations,
   select the **Upgrade** button.
6. Now, the latest Analyze Performance appear in the Project Explorer under **Report > Service
   Costing > Analyze Performance**.
7. At this point, you may choose to revert the change to the Components Version, so that all the
   components are not shown as having upgrades. To do this, revert the **Project
   Settings** as follows:
   1. On the Home tab in the Document group, select **Revert Changes**.
   2. In the revert dialog, select only **Project Settings** and select **Revert Check
      Out**.

      ![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/revert-project-setting.png)

## Navigate to the Performance Review Component Reports

Installing the Performance Review component creates a report that is accessible throughApptio TBM Studio. This report is available to users with the ADMIN role. For more information, see Manage user
permissions and roles. The report is located in the Project Explorer under Reports > Service Costing
> Analyze Performance.

![Graphical user interface, text, application, email Description automatically generated](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_2_sui.png)

The report has three main tabs:

- Overview
- Model Detail
- Project Information

  ![image](../../../../../03-media/apptio-tbm-studio/resources/images/ai_images/analyze-performance.png)

The Model Detail and Project Information tabs have sub-tabs containing the reporting discussed in
this document.

**New Features in 12.9.3 / Content v109**

- Supports analysis of changes in a user’s workspace.
- Supports comparison of workspace relative to stage.
- Support for changing the metric the analyzer examines.
- Support for identifying path count issues.
- Support for custom “focus drills”.
- Support for changing the small rows threshold.
- Small rows table accuracy improvements.

## Important Tips

Click the ToolTip icon ![image](../../resources/images/use%20the%20performance%20review%20component/use%20the%20performance%20review_3.png)for any given table for information on the table contents. In
some cases, the content of the tabs may not initially render. If a table doesn’t load, righ-
click and select update data.

## Overview Tab

This tab contains basic information about the Performance Review component and contains links to
supplementary R12 project performance information on the TBM Connect community site.

## Model Detail Tab

Under the Model Detail tab, you can observe the model metric which the report is currently
configured to examine. In the following screenshot the Cost model is configured for analysis.

## Changing the Model and/or Bottom Object

To examine a different model, you can modify the Performance Review Config table by clicking on
the link in the report.

![Graphical user interface, text, application, email Description automatically generated](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_4_sui.png)

To analyze a different model, you can edit the Performance Review Config table’s Metric value.
You can also specify a different Bottom Object for situations like custom models with a bottom
object other than Cost Source. When you change this in your workspace, the changes will be reflected
in the Analyze Performance reports in your workspace.

![image](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_5_sui.png)

## Model Detail: Allocation Information

This tab shows all of the model objects that have allocation relationships and shows the size of
the Allocation Relationship tables for each allocation. This allows for quick identification of the
largest allocations that may be contributing to increased model calculation times. To see the
largest relationships, select Row Count > Sort Descending.

![Graphical user interface Description automatically generated](../../resources/images/use%20the%20performance%20review%20component/use%20the%20performance%20review_6.png)

## Model Detail: Drill and Identifier Information

The Drill and Identifier Information tab contains information about table granularity and the
efficiency of allocations among tables. The table uses conditional formatting to help identify areas
where object identifiers and data relationships between related tables may be reaching thresholds
that could negatively impact project performance and overall calculation times.

## AR Rows

To view the largest assignment ratios tables for all objects in the model relative to the bottom
object, select AR rows > Sort Descending. Select the ToolTip icon ![image](../../resources/images/use%20the%20performance%20review%20component/use%20the%20performance%20review_3.png)in the report for more information.

![Graphical user interface, table Description automatically generated](../../resources/images/use%20the%20performance%20review%20component/use%20the%20performance%20review_7.png)

## Sparseness

The “Sparseness” column can be sorted descending to view how close AR tables are to the
theoretical worst case. The theoretical worst case is an even spread of everything in the bottom
object to the top object.

![Graphical user interface, text, application, email Description automatically generated](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_8_sui.png)

## Identifier Health Score

The “Identifier Health Score” column displays the estimated health of identifiers as measured by
identifier variation over the year. The scores are on a scale from 1 (worst) to 100 (best).

One way to think of this is that in an ideal world your object identifier would be the same
across all time periods. Therefore, if there 10 unique identifiers in all periods, then there would
be 120 total for the year or exactly a 1:12 ratio. If the ratio is larger, that indicates more
variation over time. Lots of identifier variation means that the system has to calculate a larger
table to report on time aggregates (e.g. year to date or trends).

Running this report can cause significant load depending on your configuration. Be mindful of
this when working with a suspect configuration.

![image](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_10_sui.png)

## Model Detail: Model Granularity

This tab focuses on the intersection between model object granularity and the units allocated per
row by identifying areas of the model where low-dollar allocations may be contributing to long model
calculation times. In the following example the Storage object which has a total row count of 71,787
rows and a total value of $19,233,756 has 57,787 rows, or 80% of its total row count, representing a
total of $3,115.57. This suggests an opportunity for optimization of the small rows.

![Graphical user interface Description automatically generated](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_11_sui.png)

## Model Detail: Focus Drills

Sometimes configuration will lead to large drills between two objects which have nothing to do
with Cost Source. If this happens, the Focus Drills table can be used to add custom drills for
problematic data relationships in a model. Use this as a means to complement the Drill and
Identifier Information table for specific drills in specific models that need extra attention. You
should not use it as a substitute for the Drill and Identifier Information table.

To customize the table, click on the Performance Review Focus Drills link to navigate to the
associated table.

Check out and edit the table appropriately to add or remove custom drills:

![Graphical user interface, application, table, Excel Description automatically generated](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_13_sui.png)

View results in the report:

![Graphical user interface, application Description automatically generated](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_14_sui.png)

To view the Model column:

1. Right click on the table header.
2. Select Show/Hide Columns.
3. Check the Model box.
4. Click OK
5. Move the Model column if desired.

   ![Graphical user interface, application, Word Description automatically generated](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_15_sui.png)

## Model Detail: Comparison by Environment

The Comparison by Environment tab displays AR table sizes, identifier sizes, worst case drills,
and sparseness in your workspace relative to the latest Stage build. This allows you to assess if
your workspace contains configuration which might have a negative effect on performance before you
check the config in. Filter the various “change” columns using “!BLANK” and sorting to view the
changes and their magnitude. Running this report can cause significant load depending on your
configuration. Be mindful of this when working with a suspect configuration.

![Table Description automatically generated](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_16_sui.png)

## Model Detail: Model Paths

The Model Paths tab measures complexity of your model. When Apptio prepares to calculate drills
in support of reporting, it first has to determine all the paths which allocations can take. In some
cases, model path calculation can become significant, which increases calculation times. If the
“Paths to Bottom” value becomes larger than one million, then model complexity may be impacting your
calculation times. Consult with your TAM or Apptio Support for guidance on how to reduce path
count.

![Table Description automatically generated](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_17_sui.png)

## Project Information Tab

The Product Information tab contains information which can be hard to come by in any other
way.

## Project Information: Report Information

The Report uses the following fields:

| Field | Description |
| --- | --- |
| Report ID | Report identification number used by the platform |
| Title | Actual name of the report  If the report has an aliased name, it will not display the alias in this column. |
| Preload | The report configured to pre-calculated. This is a setting in the report ribbon |
| Customized | This column shows if an Out of the Box report has been modify by a user in TBM Studio |
| Last Mod Date | The date of the last save of this report in the UI |
| Last Mod By | This username of last editor to make a save of this report |
| Access | Which TBM Studio roles have access to this report  If this field is blank, the report can be accessed by all roles that have access to the project. |
| Full Path | The URL path to this report as shown in the address bar of a web browser |

## Project Information: Dataset Sizes

The Dataset Sizes tab shows information about all of the datasets that are part of the
project:

| Field | Description |
| --- | --- |
| Name | This column contains the name of the table as it appears in the TBM Studio Project Explorer. |
| Source | The name of the source file, in the case where the system generated the file, you may see Master or System Generated as the source. |
| Type | This column shows the source of the dataset.  - Master - This dataset is a Master Dataset that is system created by the Application content - Transform - This dataset is a transform of another dataset - System Created Data - This is data that is created by the Application but is not a Master   Dataset - API Data - Data that is uploaded by Datalink or a manual API call - Editable Table - A table of source Editable - Generated Table - A table of source Generated - Upload - Files that are uploaded by a user through the UI |
| Category | The value in the Category field. This is defined by the user at upload. |
| Hidden from View | Tables that will not show in the Project Explorer unless explicitly selected in the the field filter |
| Hidden from Inference | These are tables that came into TBM Studio R12 from an R11 platform upgrade  This is a legacy setting. |
| Copy Forward | A legacy setting from projects that came into R12 from and R11 platform upgrade |
| Customization State | This shows if an Out of the Box table has been modified by a user through the UI |
| Row Count | This is the row count of the table after all Transform Pipeline steps have been processed |

## Project Information: Transform Versions

This tab tells you when a transform was versioned.

![image](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_19_sui.png)

## Project Information: Size Trends

This tab is helpful for viewing table row size growth over time and isolating spikes which may be
associated with performance issues.

![Table Description automatically generated](../../resources/images/use%20the%20performance%20review%20component/use_the_performance_review_20_sui.png)
