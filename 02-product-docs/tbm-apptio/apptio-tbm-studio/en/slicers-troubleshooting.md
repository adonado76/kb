---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Troubleshooting"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Filters and Slicers"
  - "Troubleshooting"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/troubleshooting.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Troubleshooting

Slicer Shows No Values

Possible causes:

- Field not compatible with current data
- All values filtered out by component-level filters
- !ALL_ROWS disabled and no data in current period
- Field from incompatible perspective

Resolution: Verify field source in perspective, check component-level filters, test with different time periods, and verify !ALL_ROWS project setting.

Slicer Selection Has No Effect

Possible causes:

- Selecting Unrelated values (grayed out)
- Slicer in group box, components outside group
- Slicer on different tab than target components
- Legacy table/chart not compatible with slicers

Resolution: Check slicer scope (group or report level), verify components use Ad Hoc Query format, ensure slicer and components on same tab, and check for conflicting filters in other slicers.
