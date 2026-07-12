---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Performance Considerations"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Tables"
source_path: "studio/new-uc/reference/report-studio-reference/performance-considerations.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Performance Considerations

Table performance depends on data volume, calculations, and configuration complexity.

|  |  |
| --- | --- |
| **Factor** | **Recommendation** |
| Row count | Use pagination for large datasets. Consider filters to reduce displayed rows. |
| Complex formulas | Move complex calculations to Data Studio transforms when possible. |
| Multiple time columns | Each calendar-based column requires separate calculations. Use sparingly. |
| Sparklines | Require data for each trended period. Ensure underlying data exists. |
| Status indicators | Icon calculations are lightweight but add processing overhead. |
| Grouping depth | Deep hierarchies (4+ levels) impact rendering time. |
| Interactive slicers | Use Manual Refresh for reports with many slicer interactions. |

**Parent topic:** [Report Components: Tables](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
