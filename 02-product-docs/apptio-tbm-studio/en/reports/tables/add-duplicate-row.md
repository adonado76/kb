---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Add Duplicate Row"
breadcrumb: []
source_path: "reports/tables/add-duplicate-row.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add Duplicate Row

The Duplicate Row feature improves and simplifies split mapping. The duplicate row button will
appear on the right click menu on ET or report having ET. This button will have the same permission
as add row operation since duplicating a row is similar to adding a new row but with some content.
Duplicate row will be added just below the row which is being duplicated. It works for both raw and
enriched editable tables. It allows the user to allocate a row to more than one items so the costs
can be split across multiple things. Duplication of multiple rows is allowed even before saving it.
The rows will not disappear if maximum number of rows in table are reached and pagination is
triggered. The user can turn this option off at a table level. This function will duplicate all the
visible and hidden columns. The auto-incremented column will continue to remain hidden, but for
columns that enforce uniqueness within the table:

- Prepopulate with incremented value if auto-increment is turned on.
- Set to empty but highlight as required if not auto incremented.

## Navigation

1. Right click on a cell and click Duplicate Row

   ![](../../../resources/images/studio_images/duplicate-row-et_647x314.png)
2. The new duplicate row appears just below the original row. If it is a blank editable table, All
   fields in that row will be duplicated, regardless of whether they are included in the "Included
   Columns".
3. Edit the row as desired.
4. Click "Save"

Note: The Duplicate Row does not always retain its position below the original row, due to the way
editable tables sort.

## Example

This is the Editable Table with four columns, before duplicating the row.

![](../../../resources/images/studio_images/et-dup-1.jpg)

However, only two columns are included in the Report. Let us duplicate the third row.

![](../../../resources/images/studio_images/et-dup-last.jpg)

Note: The Duplicate Row does not always retain its position below the original row, due to the way
editable tables sort. It displays values in all columns, matching the original row, unless manually
changed or removed.
