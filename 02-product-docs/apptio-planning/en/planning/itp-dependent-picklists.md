---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Line Item Filters"
breadcrumb: []
source_path: "planning/itp-dependent-picklists.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Line Item Filters

The Apptio Planning user interface uses drop-downs to allow users to enter data from a
list of approved options. Line Item Filters allow you to restrict the options which can be selected
from a drop-down list based on the value already entered in another column. This makes it easier for
the user to select the right option, because they are not overwhelmed with a list of irrelevant
options.

For example, if you are updating Line Items with the Department and the Account, you may want the
Account drop-down to only display those accounts associated with the Department you have selected.
You can create a Line Item Filter with the following mapping:

| Account | Department |
| --- | --- |
| ACCT\_6000 | CC-200 |
| ACCT\_6100 | CC-200 |
| ACCT\_6200 | CC-200 |
| ACCT\_3001 | CC-200 |
| ACCT\_3002 | CC-210 |
| ACCT\_3011 | CC-210 |
| ACCT\_2006 | CC-220 |
| ACCT\_4021 | CC-220 |

If Department is set to CC-200, then only accounts ACCT\_6000, ACCT\_6100, and ACCT\_6200 are
displayed in the Account drop-down.

You can apply additional filters to create a chain of dependencies. For example, you can create
another filter which filters Location by Account, to be applied with the example above. When a
Department is selected, the Location drop-down only displays the Locations which are mapped to the
Accounts that are mapped to the selected Department in the first filter. When the user selects an
Account, the Location options reduce further to only include the Locations which are mapped to the
selected Account.

Filters only restrict the options that are displayed in the drop-down. They do not modify data in
any way.

## Create a Line Item Filter

To add a Line Item Filter:

1. Navigate to Configuration > Line Item Filters.

   ![](../../resources/images/studio_images/line-item-filter.png)
2. In the top right corner of the page, select ![](../../resources/planning_images/icon-itp-apex-add-filter_20x20.png).

   The Add Line Item
   Filter dialog is displayed.
3. Enter the following, then select Add:
   - A unique Name.
   - In Column, select the column for which you want to filter available drop-down options.
   - In Filter By, select the column which you want to use to restrict the options.

   The new filter is displayed in the list of Line Item Filters.
4. Select the Line Item Filter you have just created. From the top right corner of the page, select
   ![](../../resources/images/it%20planning_images/options1_23x20.png) > Export To File.
   Alternatively, you can right-click the Line Item Filter and select the same option. The Line Item
   Filter's mapping file downloads in .CSV format. Because there are no mapped values yet, the table is
   empty.

   You can also select ![](../../resources/images/it%20planning_images/options1_23x20.png) > Export Template for newly
   added Line Item Filters since only the template will be exported, which allows you to fill in the
   data.
5. Add rows to the mapping file, pairing Column values with Filter By values, then save as a .CSV
   file.

   For dimensions that use a Code as a unique identifier, you must provide the code value
   instead of the name value.
6. From the top right corner of the page, select ![](../../resources/images/it%20planning_images/options1_23x20.png) > Import From File.
   Alternatively, right-click the Line Item Filter and select the same option.

   The Import File dialog
   is displayed.
7. Import the mapping file.

The mapped values are displayed in the Line Item filter page.

## Update a Line Item Filter

To change which drop-down options the filter displays, update the mapping file.

1. Navigate to Configuration > Line Item Filters and select the Line Item Filter you want to
   update.
2. From the top right corner of the page, select ![](../../resources/images/it%20planning_images/options1_23x20.png) > Export To File.
   Alternatively, you can right-click the Line Item Filter and select the same option.

   The Line Item
   Filter's mapping file downloads in .CSV format.
3. Add, update or remove rows in the mapping file then save as a .CSV file.

   For dimensions that
   use a Code as a unique identifier, you must provide the code value instead of the name
   value.
4. From the top right corner of the page, select ![](../../resources/images/it%20planning_images/options1_23x20.png) > Import From File.
   Alternatively, right-click the Line Item Filter and select the same option.

   The Import File dialog
   is displayed.
5. Import the mapping file.

The new mapped values are displayed in the Line Item filter page.

## Delete a Line Item Filter

To delete a Line Item Filter:

1. Navigate to Configuration > Line Item Filters.
2. Right-click the Line Item Filter you want to delete and select Delete.

   The filter will no
   longer be applied to drop-downs.
