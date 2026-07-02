---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Input Behavior"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components - Input Components"
source_path: "studio/new-uc/reference/report-studio-reference/input-behavior.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Input Behavior

**Cell-Level Locking (Concurrency Control)**

TBM Studio prevents conflicting edits through cell-level locks:

- When User A begins editing a cell, that cell is locked
- User B sees the cell as locked and cannot edit it
- Lock persists until User A saves or cancels
- Prevents partial updates and data collisions

**Save Workflow**

TBM Studio uses a manual save model, not auto-save:

- Edit: User modifies cell values
- Save: User clicks Save to commit changes to the editable table
- Publish: User clicks Publish to push data to the transform table

Important: Saving commits changes to the editable table. Publishing pushes those changes
to the downstream transform table and triggers recalculation.

**Parent topic:** [Report Components - Input Components](../../../../studio/new-uc/reference/report-studio-reference/report-component-input-components.html)
