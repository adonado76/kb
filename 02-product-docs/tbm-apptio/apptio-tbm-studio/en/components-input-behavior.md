---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Input Behavior"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components - Input Components"
  - "Input Behavior"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/input-behavior.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Input Behavior

Cell-Level Locking (Concurrency Control)

TBM Studio prevents conflicting edits through cell-level locks:

- When User A begins editing a cell, that cell is locked
- User B sees the cell as locked and cannot edit it
- Lock persists until User A saves or cancels
- Prevents partial updates and data collisions

Save Workflow

TBM Studio uses a manual save model, not auto-save:

- Edit: User modifies cell values
- Save: User clicks Save to commit changes to the editable table
- Publish: User clicks Publish to push data to the transform table
