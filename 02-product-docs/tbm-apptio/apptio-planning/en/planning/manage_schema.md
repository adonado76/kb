---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Schema"
breadcrumb: []
source_path: "planning/manage_schema.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Schema

The tasks below can only be performed by users assigned to the Admin or Budget Process Owner
roles. For additional information on roles, see Frontdoor permissions and roles.

You can add custom attributes to line-item tables and both built-in and custom dimensions. See
[Edit and publish Reference
Data tables](edit-publish-reference.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.") and [Manage
custom reference data (dimensions, lists, and line-item tables)](manage-custom-reference.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles."). Custom attributes contain
supplemental information about dimensions that enhance your analysis and reporting capabilities.
When a dimension is viewed as a table, the additional custom attributes appear as additional columns
in the table.

Some built-in dimensions include additional details (for example, Name and Parent Code for the
Account dimension). Others just require the unique identifier. You can add up to 30 attributes (one
per column) to built-in or custom dimensions.

## Example

You create a custom dimension named Projects. When you group or sort filter plan details by
Project, it may be useful to have access to closely related details (or attributes) about your
projects.

| Project | Program | WBS Code | Status |
| --- | --- | --- | --- |
| Value A | Value A1 | Value A2 | Value An |
| Value B | Value B1 | Value B2 | Value Bn |

Custom attributes are maintained as reference data that reside in the same reference data tables
as your built-in and custom dimensions. You can edit a dimension's reference data schema by editing
that dimension’s columns.

## Create a new reference data table column (Add custom attribute)

1. Navigate to Planning > Configuration > Schema.
2. In the top menu, select the group which contains the dimension or line item which needs a new
   reference data table column.
3. Click the specific line item or the dimension.

   The Available Attributes dialog
   opens.
4. Click the Add button to add a new custom attribute.

   The Add Custom Attribute
   dialog opens.

   ![](../../resources/images/it%20planning_images/add_custom_attribute.png)
5. Enter a Field Name for the custom attribute.
6. In the Data Type cell, select from one of the following data types:

   | Data Type | Description | Example |
   | --- | --- | --- |
   | String | Text strings up to 255 characters | Name |
   | Date | Date and time values | 1/1/2020 |
   | Integer | A whole number | 5 |
   | Number | Numeric value with fixed precision | 1,000,500.325 |
   | Percentage | Rate or proportion of a whole value (not a percentage) | .50 |
   | Memo | Unstructured alphanumeric content (up to 600 characters) | Memo1 |
   | List | Set of named values or enumerations defined in a custom list (see [Manage Custom reference data (dimensions, lists, and line-item tables)](manage-custom-reference.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.")) | No, Maybe, Yes, Red, Yellow, Green |
   | User | Enhanced Access Administration user name (user must have access to current environment) | someone@somewhere.com |
   | Boolean | Logical value: true or false | Checkbox, where checked = true or cleared = false |
   | Lookup | Refer a custom dimension related to the data (applicable only for line items) | Custom dimension name |
7. Add a Default Data Value for the attribute (optional). If the selected data type is a
   List, select the Custom List applicable, and then enter a default value. If the
   selected data type is Lookup, select the Reference Dimension applicable.
8. Select the Mandatory for Data Entry checkbox if you wish to make the custom attribute
   mandatory for the user when entering data.
9. Select the Sensitive Data checkbox if you require the line item to be classified as
   sensitive data (applicable only for Labor line items)

   Note: You can select either Sensitive
   Data or Mandatory for Data Entry checkbox when creating a custom line item column. For
   more information on sensitive data, see [FAQ: Hide Sensitive Labor Data](faq-senslabdat.html "This is a list of frequently asked questions about the Hide Sensitive Labor Data functions, which was introduced in Planning release 2.81.").
10. Click Add.

For instruction on exporting, populating, and then importing templates, see [Enter or import line item data](enter-import-line.html "After a budget plan or forecast has been opened, budget owners receive an email notification and can begin to enter line-item data and submit plans. Department Owners, Service Owners, and Project Owners can enter or import their line-item data and submit their plans."). If
you intend to export a template to use to populate your dimensions, ensure you match data format
options.

## Edit a reference data table column

You can rename a reference data table column by editing the column.

1. Navigate to Planning > Configuration > Schema
2. In the top menu, select the group which contains the dimension or the line item with the
   reference data table column to be updated
3. Click the specific line item or the dimension.

   The Available Attributes dialog
   opens.
4. Click the attribute name that needs to be updated. Alternatively, right-click and select
   Edit.

   ![](../../resources/images/it_planning_images/3.88-1.jpg)
5. Select the Restricted Access checkbox if you wish to authorize specific
   users to modify the dimension. This option is available only for Admins or users with the new
   EditRestrictedDimensions permission.
6. Note that only the names of custom attributes can be edited. You may be able to set/change the
   default data values for certain system/custom attributes.
7. Change the name of the attribute.
8. Click Save.

## Delete a reference data table column

You can delete only the custom attributes for dimensions or line items.

1. Navigate to Planning > Configuration > Schema
2. In the top menu, select the group which contains the dimension or the line item with the
   reference data table column to be updated
3. Click the specific line item or the dimension.

   The Available Attributes dialog
   opens.
4. Right-click the custom attribute you wish to delete and select Delete.
5. Click Delete when the second prompt to confirm the deletion is displayed.

## Manage line-item tables

You can alter the schema of line item tables. You can, for example, create a picklist for an
attribute you want to track per dimension, and then add that list to a line item table. Customizing
line item tables can help speed up and standardize data entry by Cost Object Owners when they work
in line item tables.
