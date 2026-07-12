---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Edit Row Properties"
breadcrumb: []
source_path: "studio/reports/edit-row-properties.html"
images:
  - "resources/images/studio_images/cf-findall.png"
  - "resources/images/studio_images/cf-replaceallerror.png"
  - "resources/images/studio_images/checkbox-del-row.png"
  - "resources/images/studio_images/editable-table-options.png"
  - "resources/images/studio_images/fr-menu.png"
  - "resources/images/studio_images/fr-popup.png"
  - "resources/images/studio_images/fr-uneditablecolumn.png"
  - "resources/images/studio_images/search-datasets.png"
  - "resources/images/studio_images/show-changes-history.jpg"
  - "resources/images/studio_images/show-changes-row.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Edit Row Properties

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/editable-table-options.png)

## Search datasets

Keep the cursor on the value/cell for which you want to search the datasets for. Right-click and
then select Search datasets for <value> to see the search results in a pop up window.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/search-datasets.png)

## Filter by Value

Keep the cursor on the cell/ for which you want to filter the table for. Right-click and then
select Filter by Value to see the results filtered by that cell value.

## Find and replace

**Applies to** 12.10.10 and later

This feature is applicable only for some columns in the Editable Table and [Reports with Editable
Table](tables/et-report-find-replace.htm "(Opens in a new tab or window)") component. You can find or replace in columns that come from another source table if
**Allow editing in included columns** check box is selected in ET configuration.

To find and replace a value in the table, do the following:

1. Right-click on the editable table column

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/fr-menu.png)
2. Choose the **Find & Replace** option. The following popup appears

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/fr-popup.png)
3. Enter the value (case-sensitive) to search and select **Find All** button. The count of exact
   matching results will be displayed.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cf-findall.png)
4. Enter the value to be replaced and select **Replace All** button. If there is any error in
   the replace value, an appropriate error message will appear. See below for example

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cf-replaceallerror.png)
5. The Find and Replace option will be disabled for [non-editable columns](tables/edit-properties-tables.htm "(Opens in a new tab or window)").

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/fr-uneditablecolumn.png)

**Exceptions**

- The find feature does not support Boolean search
- The search is applicable only to a single column at a time, and not in the entire table or
  multiple columns together.
- The search is not applicable to disabled columns like formula, total, other and pk columns.

## Add Row

Click the **Add Row** button from bottom of the table. A new row is added to the bottom of the
table, in orange color.

## Duplicate Row

To know more, see [Add
duplicate row.](tables/add-duplicate-row.htm "(Opens in a new tab or window)")

## Delete Row

Right-click on the editable table and then click **Delete Row**.

If the **Add Checkbox column** is enabled in the [advanced properties](tables/set-table-properties.htm "(Opens in a new tab or window)"), then select the checkbox for a single or
multiple rows, right-click and then select **Delete Row**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/checkbox-del-row.png)

## Show changes for this row

**12.11.1 and later**: This option will show the changes for the selected row.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/show-changes-row.png)

## Show changes

**12.11.0 and before**: This option showed the changes for the selected row.

**12.11.1 and later**: Select this option to display all changes across the entire table​

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/show-changes-history.jpg)
