---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Custom Lists"
breadcrumb: []
source_path: "planning/custom-lists.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Custom Lists

The tasks below can only be performed by users assigned to the Admin or Budget Process Owner
roles. For additional information on roles, see Frontdoor permissions and roles.

Apptio planning applications support the concept of custom lists. Custom lists can be created to
define a single attribute's allowable values. For example, you can create a Status list with values
such as Screened, Interviewed, and Hired to be added to the Labor line-item table.

Custom lists are different from custom dimensions. For more information on custom dimensions and
the differences with them, see [What is
the difference between Custom Dimensions and Custom Lists?](manage-custom-reference.htm#What)

To access custom lists:

- In the left navigation menu, select Configuration > Custom Lists.

  ![](../../resources/images/it%20planning_images/custom_lists.png)

## Create a custom list

Create custom lists to be used when customizing line-item tables.

1. Starting with the Configuration > Custom Lists page, select the Add (![](../../resources/images/icons/icon-add.png)) button at the top-right area.

   The Add
   Custom List dialog opens.

   ![](../../resources/images/it%20planning_images/add_custom_list.png)
2. Enter the desired name for the list.

   Once created, custom lists cannot be renamed.
3. Under Values section, click the Add button (![](../../resources/images/icons/icon-add.png)).
4. Enter the first value you would like to provide, and then click the Add (![](../../resources/images/icons/icon-add.png)) button again.
5. Continue until you have entered all the values required for the list.
   - Select the Arrange button (![](../../resources/images/icons/icon-arrange.png)) to the
     left of a value and drag up/down to order it correctly in the list.
   - Select the Delete button (![](../../resources/images/icons/icon-delete.png)) to the
     right of a value to remove it from the list.
6. Once updated, select Add to finish creating the list. No further publish is required.

   Note:
   - When you add a list to a line-item table (see the following section), you can set a default
     value.
   - You cannot filter a custom list.

## Edit a custom list

You can edit the values associated with a custom list, but not the list name.

1. Starting with the Configuration > Custom Lists page, select the custom list which you
   want to edit.

   The Edit Custom List dialog opens.

   ![](../../resources/images/it%20planning_images/edit_custom_list.png)
2. Add new values, update the values, delete values, or/and rearrange the values as desired.
   - Export the values in a list - Select the Export icon (![](../../resources/images/icons/icon_export.png)) and use the formatting options to export the
     values to a CSV file.
   - Import values to a list - Select the Import icon (![](../../resources/images/icons/icon_import.png)) and import a CSV file to populate the values
     in a custom list.
   - Delete the list - Select Delete List to delete the list being edited. A confirmation
     dialog will be displayed prompting your confirmation for the deletion.
3. Select Save.

You can alter the schema of line item tables to use custom lists. You can, for example, create a
picklist for an attribute you want to track per dimension, and then add that list to a line item
table. Customizing line item tables can help speed up and standardize data entry by Cost Object
Owners when they work in line item tables. For more information, see [Schema](manage_schema.htm#Schema).
