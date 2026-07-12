---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Filter Scope"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Filters and Slicers"
  - "Filter Scope"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/filter-scope.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Filter Scope

Report-Level Scope

Slicers placed directly on the report canvas (not in a group box) apply to all tables and charts in the report.

Behavior:

- All Ad Hoc Query components respond to slicer selections
- Slicers on different tabs only affect components on the same tab
- Multiple slicers combine with AND logic

Group-Level Scope

Slicers placed inside a Group Box apply only to components within that group (and nested groups).

To create group-scoped slicers:

1. Add a Group Box to the report
1. Place the slicer inside the group box
1. Place tables/charts that should be filtered inside the same group

This allows multiple independent filter contexts within one report, comparison views with different filter settings, and section-specific filtering.
