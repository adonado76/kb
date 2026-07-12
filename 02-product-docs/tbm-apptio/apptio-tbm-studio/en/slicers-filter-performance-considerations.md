---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Filter Performance Considerations"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Filters and Slicers"
  - "Filter Performance Considerations"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/filter-performance.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Filter Performance Considerations

Large Value Lists

Limits and thresholds:

| Component | Limit | Handling |
| --- | --- | --- |
| Component | Limit | Handling |
| Slicer values | 250 values maximum | Message displayed when exceeded |
| Filter dialog | 1,000 values displayed | Use search box for additional values |
| Edit Filter selections | No hard limit | Use "Values not currently shown" option |

Performance best practices:

1. Filter slicers to reduce value count before display
1. Use compact slicers when multiple dimensions needed
1. Apply component-level filters to pre-filter data before slicer evaluation
1. Consider hierarchy slicers for large categorical dimensions
