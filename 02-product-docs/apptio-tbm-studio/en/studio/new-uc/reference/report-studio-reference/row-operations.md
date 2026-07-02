---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Row Operations"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Editable Tables in Reports"
source_path: "studio/new-uc/reference/report-studio-reference/row-operations.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Row Operations

Editable table components support various row-level operations controlled by permissions.

**Add New Rows**

Users with appropriate permissions can add rows:

1. Click the Add Row button at the bottom of the table
2. A new row appears at the bottom, highlighted in orange
3. Enter values in the editable columns
4. Click Save to persist the new row

Enable Add Row Dialog in the Editable Tables ribbon to display a form dialog for entering new row
data.

**Delete Rows**

To delete rows:

1. Right-click on the row to delete
2. Select Delete Row from the context menu
3. The row is marked for deletion (shown in Show Changes)
4. Click Save to confirm the deletion

For bulk deletions, enable the Enable Checkbox Column option in Advanced Properties. Select
multiple rows using checkboxes, then right-click and select Delete Row.

**Duplicate Rows**

The Duplicate Row feature simplifies split mapping scenarios:

- Right-click a row and select Duplicate Row
- A copy appears below the original row
- All visible and hidden columns are duplicated
- Columns with unique constraints are cleared and highlighted as required

Warning: *In enriched editable tables, users cannot delete rows sourced from the
transform table; only added rows can be deleted.*

**Parent topic:** [Report Components: Editable Tables in Reports](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
