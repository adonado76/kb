---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Save Behavior"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Editable Tables in Reports"
source_path: "studio/new-uc/reference/report-studio-reference/save-behavior.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Save Behavior

Editable tables use a two-stage save process: local save (persisting changes to the editable
table) and publish (updating the associated transform table).

**Save Process**

When users make changes:

1. Changes are tracked client-side until explicitly saved
2. Click Save at the bottom of the table to persist changes
3. Saved changes update the editable table but not yet the transform pipeline
4. The Show Changes option displays all pending modifications

**Publish Process**

To move saved data into the transform pipeline:

1. Click Publish at the bottom of the table
2. Confirm the publish action in the warning dialog
3. Enter a description and click Check In
4. The associated transform table updates with the new data

Publishing always overwrites the entire editable table dataset in the associated transform table.

**Prerequisites:** *Manual publishing requires Dev access and Stage access but does not
require TBM Studio or Admin access.*

**Error Handling on Save**

When save or publish fails:

- **Validation errors:** Invalid data prevents publishing; fix errors and retry
- **Connection errors:** Retry the operation; changes remain in local state
- **Concurrent edit conflicts:** See the Concurrency Control section below

**Concurrency Control**

Editable tables enforce cell-level locking to prevent conflicts:

- When a user begins editing a cell, that cell is locked for other users
- The lock persists until the user saves or cancels their edit
- Other users can edit different cells in the same row simultaneously
- If all cells in filtered rows are locked, Add Row, Delete Row, and Duplicate Row are disabled

**Parent topic:** [Report Components: Editable Tables in Reports](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
