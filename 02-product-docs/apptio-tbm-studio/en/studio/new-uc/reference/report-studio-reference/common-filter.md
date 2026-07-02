---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Common Filter Patterns"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Filters and Slicers"
source_path: "studio/new-uc/reference/report-studio-reference/common-filter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Common Filter Patterns

**Time Period Selector**

**Objective:** Allow users to switch between monthly, quarterly, and annual views.

**Implementation:**

1. Add a Column Picker
2. Drag time-based values from the Time perspective: CurrentMonth, CurrentQuarter (or QTD), YTD
3. Set to Single Selection with Selection Required
4. Add dynamic text <%=CurrentDate()%> to table column headers

**Hierarchical Region Filter**

**Objective:** Filter by Region → Country → City.

**Implementation:**

1. Create custom perspective group
2. Add and rename fields: 01\_Region, 02\_Country, 03\_City
3. Create hierarchical slicer using the group
4. Optionally use compact slicer format for space efficiency

**Cost Threshold Filter**

**Objective:** Filter showing only significant costs above a minimum.

**Implementation:**

1. Add Cost (or relevant metric) as a slicer
2. Configure slider range
3. Set default position to exclude small values
4. Save report with defaults

**Parent topic:** [Report Components: Filters and Slicers](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
