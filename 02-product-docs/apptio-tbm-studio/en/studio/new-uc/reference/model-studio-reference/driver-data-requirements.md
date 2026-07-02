---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Driver Data Requirements"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Model Studio Reference"
  - "Drivers"
source_path: "studio/new-uc/reference/model-studio-reference/driver-data-requirements.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Driver Data Requirements

**Column Requirements**

|  |  |  |
| --- | --- | --- |
| **Requirement** | **Description** | **Impact if Not Met** |
| Numeric Type | Driver column must be numeric | Driver ignored; no value flows |
| Non-Null Values | Column should have values for rows | Rows with null values contribute $0 |
| Period Data | Data must exist for active period | No driver value for that period |
| Transform Success | Table transform must complete | Model calculations blocked |

Warning: If a numeric column contains at least one non-numeric value, drivers
referencing that column may fail silently. Always verify data types in Data Studio.

**Parent topic:** [Drivers](../../../../studio/new-uc/reference/model-studio-reference/drivers.html)
