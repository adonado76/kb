---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Data Refresh Cycles"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Data Studio Reference"
  - "Tables"
source_path: "studio/new-uc/reference/data-refresh-cycles.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Data Refresh Cycles

|  |  |  |
| --- | --- | --- |
| **Cycle** | **Description** | **Expiration Check** |
| Ad-Hoc updates | Updates as needed; append or replace | None |
| 1 version; No scheduled updates | Single version, replaced on upload | None |
| 1 version; Update every month | Monthly refresh, replaces existing | Monthly |
| 1 version; Update every year | Annual refresh, replaces existing | Annual |
| Monthly versions; Update every month | New version each month | Monthly |
| Yearly versions; Update every month | Rolling 12-month versions | Monthly |
| Yearly versions; Update at start of year | Annual version at fiscal year start | Annual |
| Yearly versions with carryover | Annual with previous year carry-forward | Annual |

**Parent topic:** [Tables](../../../studio/new-uc/reference/tables.html)
