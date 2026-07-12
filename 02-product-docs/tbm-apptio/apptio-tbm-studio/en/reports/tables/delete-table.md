---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Delete an editable table"
breadcrumb: []
source_path: "reports/tables/delete-table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Delete an editable table

1. Check out the editable table.
2. On the Home tab in the Document group, click Delete.
3. Check in the editable table.

These tables cannot be recovered later via audit log roll back. To warn user about this
consequence, a warning message appears as shown.

![](../../../resources/images/studio_images/r-notes/purge%20sql%202_582x354.png)

You must delete all dependents before deleting the editable table as the no backing database
table will be available. If an editable has dependents (except reports), the delete confirmation
button will be disabled and an error message appears as shown.

![](../../../resources/images/studio_images/r-notes/purge%20sql%201_576x404.png)
