---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Edit Table Properties"
breadcrumb: []
source_path: "data_studio/table-properties.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Edit Table Properties

## Filter by Value

Keep the cursor on the cell/ for which you want to filter the table for. Right-click and then
select Filter by Value to see the results filtered by that cell value.

## Add a row to a table

Click the Add Row button from bottom of the table. A new row is added to
the bottom of the table, in orange color.

## Truncate

Applies to: 12.11.4 and later

The Truncate button appears for both General and Enriched editable tables.
However, the Truncate function works only for generated tables.

1. Open a enriched editable table. The Truncate button appears at the bottom
   right of the page.

   ![](../../resources/images/studio_images/truncate-generated.png)
2. Change the value 'Q1' and 'Engagement in the highlighted cells above, save the table, and then
   select Truncate . A popup warning message appears as shown.

   ![](../../resources/images/studio_images/edit-generated-table.png)
3. Select Ok. The original value of Q1 and Engagement is reverted as
   shown.

   ![](../../resources/images/studio_images/revert-generated.png)
4. Now, open a general editable table.

   ![](../../resources/images/studio_images/truncate-general.png)
5. Select Truncate. The popup message appears.

   ![](../../resources/images/studio_images/warning-truncate.png)
6. Select the Ok button. All the rows are deleted from the table.

   ![](../../resources/images/studio_images/truncated-empty.png)
7. Check in the editable table. The truncation is permanent only after checking in the editable
   table. The rows are deleted from MySQL DB, and this change will not appear in Show
   Changes as well.

Note: If an editable table is linked to a report, then the truncated rows will be deleted even
in that report.

Revert Changes

If you want to revert the truncate action, it should be done before you check-in the table. Once
you truncate and check-in the table, it is not possible to reverse the truncate action.
