---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Performance Considerations"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Tables"
  - "Performance Considerations"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/performance-considerations.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Performance Considerations

Table performance depends on data volume, calculations, and configuration complexity.

| Factor | Recommendation |
| --- | --- |
| Factor | Recommendation |
| Row count | Use pagination for large datasets. Consider filters to reduce displayed rows. |
| Complex formulas | Move complex calculations to Data Studio transforms when possible. |
| Multiple time columns | Each calendar-based column requires separate calculations. Use sparingly. |
| Sparklines | Require data for each trended period. Ensure underlying data exists. |
| Status indicators | Icon calculations are lightweight but add processing overhead. |
| Grouping depth | Deep hierarchies (4+ levels) impact rendering time. |
| Interactive slicers | Use Manual Refresh for reports with many slicer interactions. |
