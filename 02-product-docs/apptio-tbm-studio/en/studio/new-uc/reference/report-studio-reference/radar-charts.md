---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Radar Charts"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
source_path: "studio/new-uc/reference/report-studio-reference/radar-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Radar Charts

Radar charts (also called spider charts) compare multiple characteristics across two or more
entities using axes radiating from a central point. They are effective for comparing budget and
actuals across several departments or evaluating items across multiple criteria.

**Radar Chart Types**

- Filled Radar: Displays filled polygonal areas connecting data points. Best for comparing three
  or fewer characteristics to avoid visual clutter.
- Radar with Markers: Shows only the data points and connecting lines without fill. Suitable for
  any number of characteristics.

**Creating a Radar Chart**

1. On the Report tab, click Chart.
2. Drag a field into the Axis area (this defines the characteristics compared).
3. Drag one or more fields into the Values area.
4. On the Ad Hoc tab, click Radar.
5. From the Radar dropdown, select Filled Radar or Radar with Markers.

**Pivot behavior:** When a pivot is applied to a radar chart, it affects the axis rather than
the rows (unlike other chart types).

**Maximum Rows:** Controls the number of axes displayed. The default is six. Unlike other
charts, radar charts do not display an "Other" category for excess items.

**Parent topic:** [Report Components: Charts](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
