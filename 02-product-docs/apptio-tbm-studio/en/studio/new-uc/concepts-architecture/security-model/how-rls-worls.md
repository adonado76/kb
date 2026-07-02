---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How RLS Works"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Row-Level Security (RLS)"
source_path: "studio/new-uc/concepts-architecture/security-model/how-rls-worls.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How RLS Works

The RLS process follows a predictable sequence each time a user requests data:

1. The user opens a report or views a table in TBM Studio.
2. The system identifies the logged-in user by their User ID (email address).
3. For each table with RLS configured, the system looks up the user’s ID in the corresponding
   mapping table(s).
4. The system determines which dimension values (such as business units, cost centers, or data
   centers) the user is permitted to see.
5. The system filters the table, showing only rows where the relevant dimension values match the
   user’s permitted values.
6. The user sees only the permitted data—aggregations, totals, and drill-throughs all reflect the
   filtered view.

**Parent topic:** [Row-Level Security (RLS)](../../../../studio/new-uc/concepts-architecture/security-model/row-level-security.html)
