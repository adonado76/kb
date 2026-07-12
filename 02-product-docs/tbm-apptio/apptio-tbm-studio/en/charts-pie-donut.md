---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Pie and Donut Charts"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
  - "Pie and Donut Charts"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/pie-donut-chart.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Pie and Donut Charts

Pie charts display data as proportional slices of a circle, making them excellent for showing how parts contribute to a whole. TBM Studio offers four pie chart variants to suit different presentation needs.

Pie Chart Variants

| Variant | Description |
| --- | --- |
| Variant | Description |
| Standard | Full circle pie chart showing all slices as proportional segments. |
| Standard Half | Semi-circle pie chart displaying data in a 180-degree arc. Useful when vertical space is limited. |
| Donut | Full circle with a hollow center, allowing space for KPIs or summary text. |
| Donut Half | Semi-circle donut chart combining the half-circle format with a hollow center. |

Pie Chart Behavior

Important: Pie charts only work with positive numbers. If your data contains negative values, a message statingstating that there is inappropriate data is displayed in place of the chart.

A pie chart always shows slices representing the total (100%) of the value being charted. If you limit the display to show only the top items (using Maximum Rows), an additional slice called "Other" is automatically added to represent the remaining percentage. The Other slice cannot be hidden.

Exploded Slice

You can emphasize a specific slice by "exploding" it, which offsets the slice slightly from the rest of the pie. There are two ways to create an exploded slice:

- Right-click a slice in the chart and select Explode from the context menu.
- Enter the slice name in the Exploded Slice field in the Chart properties dialog.

Pie Chart Properties

Pie chart properties are available on the Pie tab in the Properties dialog. Key options include label positioning, slice percentages, and visual styling. Experiment with the options to achieve your desired presentation.
