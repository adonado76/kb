---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How Report Permissions and RLS Interact"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Report and Component Permissions"
source_path: "studio/new-uc/concepts-architecture/security-model/report-permission-rls-interact.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How Report Permissions and RLS Interact

Report permissions and RLS work as complementary layers:

1. Report permissions determine whether the user can access the report at all.
2. If the user can access the report, RLS filters the data visible within it.
3. Component visibility further refines what the user sees on the report surface.

**Common Scenario:** A “Cost Overview” report is accessible to all roles. An executive sees
all business units (no RLS restriction). A department manager sees only their department’s data (RLS
filters by business unit). Both see different component layouts (component visibility by role). All
of this is accomplished with a single report definition.

Note:

**Common Gotcha: Missing RLS on Drill Targets**

If a user drills from a secured summary table to a detail table that does not have RLS
configured, they may see unfiltered data in the detail view. Always ensure RLS is configured on all
tables that can be reached through drill-through navigation.

**Parent topic:** [Report and Component Permissions](../../../../studio/new-uc/concepts-architecture/security-model/report-component-permission.html)
