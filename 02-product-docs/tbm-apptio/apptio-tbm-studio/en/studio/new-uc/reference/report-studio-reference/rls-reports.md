---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Row-Level Security in Reports"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Permissions"
source_path: "studio/new-uc/reference/report-studio-reference/rls-reports.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Row-Level Security in Reports

**How RLS Applies to Report Data**

Row-level security filters the data displayed in report components based on the current user's
identity. When RLS is configured:

1. The system identifies the current user
2. It looks up the user in RLS mapping tables
3. Only rows matching the user's permissions are displayed
4. Aggregate calculations reflect only the visible data

**RLS Configuration Steps:**

1. **Create mapping tables** in the Row-Level Security project that define which items each user
   can view
2. **Add RLS pipeline steps** to transform tables that should be filtered
3. **Configure filter rules** that match table columns to mapping table values

**RLS + Report Permissions Interaction**

RLS and report permissions are independent but complementary:

|  |  |  |  |
| --- | --- | --- | --- |
| **Scenario** | **Report Permission** | **RLS Access** | **User Experience** |
| **A** | ✓ Granted | ✓ All data | Full report, all data |
| **B** | ✓ Granted | ✓ Filtered | Full report, filtered data |
| **C** | ✓ Granted | ✗ No data | Empty report components |
| **D** | ✗ Denied | — | Cannot access report |

**Common Scenario:** A user has report access but sees no data. This typically indicates that:

- RLS is configured on the underlying tables
- The user's ID is not in the RLS mapping tables
- The user needs to be added to the appropriate RLS access list

**RLS Debugging**

**Symptom: User sees no data in reports**

Check these items in order:

1. **RLS Mapping Tables:** Verify the user's ID exists in the appropriate mapping tables in the
   Row-Level Security project
2. **User ID Format:** Ensure the user ID in mapping tables exactly matches the user's login
   (case-sensitive)
3. **RLS Pipeline Steps:** Confirm RLS steps are configured on the tables feeding the report
4. **Column Matching:** Verify the filter column in the table matches values in the mapping
   table

Important: Tables do not automatically inherit RLS settings. You must add an RLS step
for each model step that should be filtered.

**Parent topic:** [Report Permissions](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
