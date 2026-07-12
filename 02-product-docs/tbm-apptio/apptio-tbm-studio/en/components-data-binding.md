---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Data Binding"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components - Input Components"
  - "Data Binding"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/data-binding.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Data Binding

Input components bind to editable table columns, which store user-entered data in the project database.

Binding to Editable Table Columns

All input components are configured through the editable table's Configure Columns step:

- Select the editable table in Project Explorer
- Navigate to Steps > Configure Columns
- Select or add a column to configure
- Set the column properties (type, validation, possible values, etc.)

Two-Way Binding Behavior

Changes made in report input components flow through the system as follows:

- User edits a cell in the report
- Value is stored client-side (pending state)
- User clicks Save to commit changes to the editable table
- User clicks Publish to push data to the associated transform table
- Build or staging calculations incorporate the updated values
