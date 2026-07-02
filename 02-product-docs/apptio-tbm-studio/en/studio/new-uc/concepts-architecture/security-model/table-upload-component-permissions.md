---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Table Upload Component Permissions"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Report and Component Permissions"
source_path: "studio/new-uc/concepts-architecture/security-model/table-upload-component-permissions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Table Upload Component Permissions

The Table Upload component supports advanced access control through an editable table that maps
specific tables to specific roles or individual users. This allows administrators to control which
users can upload to which tables without creating multiple reports.

**Example — Table Upload Access Configuration:**

|  |  |  |
| --- | --- | --- |
| **Table** | **Role** | **User** |
| Acme Contracts | Power User | (any Power User) |
| Acme General Ledger |  | bob@acme.com |
| Acme General Ledger |  | sally@acme.com |
| Acme IT Org Mapping |  | bob@acme.com |

In this configuration, Bob sees Acme General Ledger and Acme IT Org Mapping in his upload
dropdown. Sally sees Acme Contracts (by virtue of her Power User role) and Acme General Ledger.
Users not listed see no tables available for upload.

**Parent topic:** [Report and Component Permissions](../../../../studio/new-uc/concepts-architecture/security-model/report-component-permission.html)
