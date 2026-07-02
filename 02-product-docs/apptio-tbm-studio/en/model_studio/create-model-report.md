---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "model_studio"
title: "Create a model report"
breadcrumb: []
source_path: "model_studio/create-model-report.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create a model report

Applies to: TBM Studio 12.0 and later

When you want to view a selected set of the tables in a model and their drivers and allocations,
create a model report. An example model report is shown in the following image. The tiers in the
report can contain a single column from a table, or one or more tables. Use a single column when you
want the model report to focus on a specific element, such as cost pools. Use a table when you want
the user to be able to customize the model report by selecting a column from the table. For example,
you might include the Cost Source table, which includes cost pools but also other
columns such as cost centers, benchmark towers, and project names.

![](../../resources/images/studio_images/studioimages/studio/stu582.png)

Watch this demo video from Apptio Education Services: [Using Model
Reports](https://community.apptio.com/videos/1583 "(Opens in a new tab or window)"). Or, browse [all Apptio videos](https://community.apptio.com/docs/DOC-7714 "(Opens in a new tab or window)").

## View drivers and allocations

To view the drivers and allocations for a table, click the table in the report. In the preceding
image, the Cost Source Actuals table has been selected. The allocations to the cost pool
tables are displayed.

If you want to see more detail about the elements in a table, click the menu and click **Drill
Down** as shown in the following image. You can then select a column from the table. In the
following example, if you select Vendor Name, the report model will look like the following
image:

![](../../resources/images/studio_images/studioimages/studio/stu584_sui.png)

You can click a Vendor Name to see the allocations to the cost pools.

To return to the table view, click the ![](../../resources/images/studio_images/studioimages/studio/stu586_up__arrow_icon_37x30.png)
icon.

![](../../resources/images/studio_images/studioimages/studio/stu585.png)

## Use tiers to control the layout

A tier can contain a single column from a table, or one or more tables. It cannot contain both a
column and a table. You can create multiple tiers using columns from the same table.

In a model report, tiers control the layout of the tables. In the first image, there are four tiers:

- Financials
- Resources
- Infrastructure
- Services

To build a report, you define the tiers and then drag tables from the Project Explorer
into the tiers. You define the tiers using the Tier Editor shown in the following image:

![](../../resources/images/studio_images/studioimages/studio/stu587_sui.png)

To display the Tier Editor, click the View menu on
the Home tab, and click Show Tier Editor. To edit the
tier, check out the model report. These are the common tasks you perform in the Tier
Editor:

- Add a tier - Click the Add Tier icon ![](../../resources/images/studio_images/studioimages/icons/add%20tier.png).
- Delete a tier - Click the Delete Tier icon ![](../../resources/images/studio_images/studioimages/icons/delete%20tier.png).
- Change the order of the tiers - Click the Rearrange icon ![](../../resources/images/studio_images/studioimages/icons/rearrange.png) in the header of the
  tier and drag the tier to a new location.
- Add a table to a tier - Click the table in the Project
  Explorer and drag it to the tier. You can add only modeled tables. You can add more than
  one table to a tier, but if you have added a table to a tier, you cannot add a column.
- Add a column from a table - Expand the table in the Project
  Explorer and drag a column to the tier. If you add a column to a tier, you will not be
  able to add any other elements to the tier.
- Change the order of the tables in a tier - Click in the table and drag it
  to the new position in the tier.
- Name a tier - Click in the Name field at the top
  of the tier and enter a name.
- Return to viewing the report - Click the View menu
  on the Home tab and click Show Document.

## Assign a model report to a collection

Beginning with v12.2.2, you can assign a model report to a report collection. When a user opens
the report collection, the report will be displayed along with the other reports in the collection.
Adding a model report to a report collection makes it easy for users to access the report.

To assign a model report to a report collection:

1. Click the Modeling tab.
2. Click Assign to Collection.
3. Open the drop-down list and click the name of the report collection.
4. Save the report.

   ![](../../resources/images/studio_images/studioimages/studio_modeling_benchmarking_sui.png)
