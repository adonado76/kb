---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Editable Table Permissions"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Report and Component Permissions"
source_path: "studio/new-uc/concepts-architecture/security-model/editable-table-permissions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Editable Table Permissions

Editable tables in reports have their own granular permission system that controls actions at the
row level:

|  |  |  |
| --- | --- | --- |
| **Permission** | **Controls** | **Default** |
| Add Row Permission | Which roles can add new rows to the table | Everyone |
| Duplicate Row Permission | Which roles can duplicate rows | Everyone |
| Delete Row Permission | Which roles can delete individual rows | Everyone |
| Publish Row Permission | Which roles can publish edits back to transforms | Everyone |
| Edit Row Permission | Which roles can modify existing rows | Everyone |
| Download Permission | Which roles can download the table data | Everyone |
| Upload Permission | Which roles can upload data to the table | Everyone |
| Show History Permission | Which roles can see the change history | Everyone |
| Delete All Rows Permission | Which roles can delete all rows at once | Admin and Partner |

Each permission can be set to “Everyone” or “Selected Roles,” allowing fine-grained control over
data entry workflows.

**Parent topic:** [Report and Component Permissions](../../../../studio/new-uc/concepts-architecture/security-model/report-component-permission.html)
