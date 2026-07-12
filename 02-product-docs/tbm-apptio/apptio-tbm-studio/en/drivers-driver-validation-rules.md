---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Driver Validation Rules"
breadcrumb:
  - "Reference"
  - "Model Studio Reference"
  - "Drivers"
  - "Driver Validation Rules"
source_path: "SSWRJM/studio/new-uc/reference/model-studio-reference/driver-validation-rules.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Driver Validation Rules

Validation Checks

- Column must exist in the underlying table
- Column data type must be numeric for value columns
- Formula syntax must be valid
- Referenced metrics must exist in the project
- Cross-project references must point to accessible projects

Common Driver Issues

| Issue | Cause | Resolution |
| --- | --- | --- |
| Issue | Cause | Resolution |
| Driver shows $0 | Column contains non-numeric data | Verify column type in Data Studio |
| Driver missing for period | No data loaded for that period | Load data for required periods |
| Formula error | Invalid syntax or missing reference | Check formula syntax and references |
| Wrong values | Incorrect column selected | Verify column contains expected data |

→ See Driver troubleshooting for detailed solutions

→ See Data Studio Reference for data type configuration
