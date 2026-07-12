---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Common Filter Patterns"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Filters and Slicers"
  - "Common Filter Patterns"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/common-filter.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Common Filter Patterns

Time Period Selector

Objective: Allow users to switch between monthly, quarterly, and annual views.

Implementation:

1. Add a Column Picker
1. Drag time-based values from the Time perspective: CurrentMonth, CurrentQuarter (or QTD), YTD
1. Set to Single Selection with Selection Required
1. Add dynamic text <%=CurrentDate()%> to table column headers

Hierarchical Region Filter

Objective: Filter by Region → Country → City.

Implementation:

1. Create custom perspective group
1. Add and rename fields: 01_Region, 02_Country, 03_City
1. Create hierarchical slicer using the group
1. Optionally use compact slicer format for space efficiency

Cost Threshold Filter

Objective: Filter showing only significant costs above a minimum.

Implementation:

1. Add Cost (or relevant metric) as a slicer
1. Configure slider range
1. Set default position to exclude small values
1. Save report with defaults
