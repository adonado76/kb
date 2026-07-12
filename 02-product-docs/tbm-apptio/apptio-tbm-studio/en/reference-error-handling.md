---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Error Handling"
breadcrumb:
  - "Reference"
  - "Data Studio Reference"
  - "Error Handling"
source_path: "SSWRJM/studio/new-uc/reference/error-handling.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Error Handling

## Common Error Types

Source Errors:

| Error | Cause | Resolution |
| --- | --- | --- |
| Error | Cause | Resolution |
| Double-string conversion | Type mismatch in column reference | Change column type or use explicit conversion |
| Error Getting Backing Table | Source table deleted | Recreate source table |

Import Errors:

| Error | Cause | Resolution |
| --- | --- | --- |
| Error | Cause | Resolution |
| Expected Type Label but Found Numeric | All values numeric in Label column | Change Incoming Type to Any |
| Column Does Not Exist | Validation expects missing column | Delete from validation or add to upload |
| Column Was Added | Unexpected column in upload | Add to validation or remove from upload |

Formula Errors:

| Error | Cause | Resolution |
| --- | --- | --- |
| Error | Cause | Resolution |
| Cannot find column | Referenced column missing | Add column or fix formula |
| Cannot find table | Referenced table missing | Update formula reference |
| Mismatched lookup | Type mismatch in lookup columns | Align column types or convert |

Pipeline Errors:

| Error | Cause | Resolution |
| --- | --- | --- |
| Error | Cause | Resolution |
| Cycle Detected | Circular reference between tables | Remove one side of circular reference |
| Recursion detected | Table references itself | Fix self-referential configuration |
