---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Troubleshooting"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Editable Tables in Reports"
  - "Troubleshooting"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/editable-troubleshoot.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Troubleshooting

Common issues and solutions for editable table components.

Common Save Errors

| Issue | Solution |
| --- | --- |
| Issue | Solution |
| Validation errors prevent save | Review highlighted cells, correct invalid values, ensure required fields are populated |
| Cell is locked by another user | Wait for the other user to save or cancel their edit, or contact them to release the lock |
| Cannot publish changes | Ensure you have Publish Row Permission and Dev/Stage access; check for validation errors |
| Changes not appearing in reports | Verify publish completed successfully; wait for build/calculation to complete; refresh the report |
| Dropdown values not loading | Check Possible Values formula syntax; verify source table exists and is calculated |
| Cannot delete rows in enriched table | Rows from source transform cannot be deleted; only user-added rows can be removed |

Performance Considerations

For large editable tables:

- Enable Suppress initial data request in Advanced Properties to load data on demand
- Use filters or RLS to limit the number of rows displayed
- Limit the number of columns with complex dropdown formulas
- Consider using file upload for bulk data entry (more than 100 rows)
