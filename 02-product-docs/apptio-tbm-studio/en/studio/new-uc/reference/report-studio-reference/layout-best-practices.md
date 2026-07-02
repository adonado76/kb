---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Layout Best Practices"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Layout Options"
source_path: "studio/new-uc/reference/report-studio-reference/layout-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Layout Best Practices

**Alignment and Spacing**

- Use group boxes with Vertical or Horizontal layout for consistent spacing.
- Set explicit spacing values in the Spacing dialog for uniform gaps between components.
- Align related components (e.g., a chart and its corresponding table) using group boxes.

**Print-Friendly Layouts**

- Test layouts in Print Layout mode before finalizing.
- Use Vertical flow for reports with many components to ensure consistent pagination.
- Pin filter slicers to the end so printed reports show the filtering context.
- Avoid placing critical information near page margins.

**Common Layout Patterns**

|  |  |
| --- | --- |
| **Pattern** | **Implementation** |
| **Dashboard layout** | Multiple group boxes with charts and KPIs; slicers in a sidebar group |
| **Detail report** | Large table with associated slicers; use Vertical flow for print |
| **Tabbed analysis** | Tabbed component with different views on each tab; shared slicers outside tabs |
| **Master-detail** | Summary table with drill-through buttons to detail reports |

**Parent topic:** [Layout Options](../../../../studio/new-uc/reference/report-studio-reference/layout-options.html)
