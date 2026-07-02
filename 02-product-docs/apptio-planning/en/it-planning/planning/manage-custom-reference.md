---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Custom Dimensions"
breadcrumb: []
source_path: "it-planning/planning/manage-custom-reference.html"
images:
  - "resources/images/icons/3-dots.png"
  - "resources/planning_images/itp-expenses-menu-bar.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Custom Dimensions

The tasks below can only be performed by users assigned to the Admin or Budget Process
Owner roles. For additional information on roles, see Frontdoor permissions and roles.

Apptio Planning applications support custom dimensions, custom lists, and editing the schema of
line-item tables. You can do the following:

- Create up to 13 custom dimensions to extend built-in dimensions (see [Planning applications: Manage
  reference data](manage-reference-data.html)). Use custom dimensions to define the data category sets that extend and
  enhance your financial planning and analysis. For example, create a custom dimension to associate
  multiple attributes like Business Initiative with WBS Code.
- Create custom lists to define a single attribute's allowable values. For example, you can create
  a Status list with values such as Screened, Interviewed, and Hired to be added to the Labor
  line-item table. See [Custom Lists](custom-lists.html)
  for more information.
- Customize the line-item tables' schema that map to tabs of the Expenses view:

  ![image](../../../../../03-media/apptio-planning/resources/planning_images/itp-expenses-menu-bar.png)

To access custom dimensions and custom data:

In the navigation menu, select Configuration > Schema.

## What is the difference between Custom Dimensions and Custom Lists?

| Custom Dimensions | Custom Lists |
| --- | --- |
| Use custom dimensions to define the data category sets that extend and enhance your financial planning and analysis. | Use custom lists to define a single attribute's allowable values. |
| Custom dimensions can include custom attributes, which contain supplemental information which are closely related to the dimension. | Custom lists do not include custom attributes. |
| To create a custom dimension you can import values using Costing Standard integration. | To create a custom list you must enter the values manually. |
| You can rename columns in Reference Data.  [Learn more about renaming a column](manage_schema.html "Schemas define the structure of data in Apptio Planning. They specify the tables, fields, and relationships that determine how information is stored, linked, and surfaced across Expense tabs such as Labor, Contracts, Assets, and Financials.").  • When the column is renamed, users see the new name in line-item table column headers. | You cannot rename the column in custom lists. |
| You can filter a custom dimension on a line-item table. | You cannot filter a custom list on a line-item table. |
| You can create a maximum of 13 custom dimensions. | You can create an unlimited number of custom lists. |

Note: Data from deleted custom dimensions is removed from all plans and cannot be recovered.

## Manage custom dimensions

Tip: To create a new custom dimension or add an attribute to a dimension, see [Add and manage custom attributes of
dimensions](manage_schema.html "Schemas define the structure of data in Apptio Planning. They specify the tables, fields, and relationships that determine how information is stored, linked, and surfaced across Expense tabs such as Labor, Contracts, Assets, and Financials.").

## Download and populate custom dimension table templates

You can import reference data from Costing Standard. When you import
reference data, Planning imports the most recent reference dataset
regardless of the active date setting in Costing Standard. See [Integrate with Cost Transparency](integrate-ct.html "If your organization runs both Apptio Costing Standard and an Apptio Planning application, you can integrate them to share data.").

1. In the navigation menu, select Configuration > Reference Data.
2. Select Custom Dimensions tab.
3. Select a table, and then select ![more icon](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png)>Export.
4. In the Export file window, under Format options, you can change the format of the exported
   data.
5. Select Export. The reference data is exported as a .csv file.
6. Open the downloaded .csv template file, then add the additional attributes you want.

   NOTE: Do not change the column headings or structure of this template, as it represents a
   required data structure.
7. Save the template in .csv format for import into your Apptio Planning application.

## Create, import, and publish a new custom dimension

After you've created the .csv file with the dimension values you want, you can create the custom
dimension, and then upload the values from your .csv file into the dimension.

1. To create new custom dimension, see [Add and manage custom attributes of dimensions](manage_schema.html "Schemas define the structure of data in Apptio Planning. They specify the tables, fields, and relationships that determine how information is stored, linked, and surfaced across Expense tabs such as Labor, Contracts, Assets, and Financials.").
2. Next to the new custom dimension, click Import New.
3. Follow the on-screen instructions to complete the data import process. Examine and verify your
   imported data:
   - If your data looks correct and you want to make it available in plans, click
     Publish.
   - If you see problems with your data and need to troubleshoot before publishing, click
     Revert.

## Delete a custom dimension

To delete a custom dimension, see [Delete a reference data table column](manage_schema.html "Schemas define the structure of data in Apptio Planning. They specify the tables, fields, and relationships that determine how information is stored, linked, and surfaced across Expense tabs such as Labor, Contracts, Assets, and Financials.")

CAUTION:

Data from deleted custom dimensions is removed from all plans and cannot be
recovered.

**Parent topic:** [Reference Data Overview](../../it-planning/planning/edit-publish-reference.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.")
