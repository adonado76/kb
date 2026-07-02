---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Utilization Summary"
breadcrumb: []
source_path: "reports/utilization-summary.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Utilization Summary

Use this report to understand the impact of your on-premises storage resources on the
cost, and to view utilization metrics (such as storage cost, addressable space, percentage of
allocated space, percentage of used space, and cost per terabyte) for your on-premises Storage
resources.

This report has the following elements:

![](../../resources/images/ct_images/ct%20report%20collections/utilization%20summary.png)

(1) KPIs: KPIs provide a high-level view of your host server spending:

- Cost YTD: This KPI shows the overall spend on storage devices YTD. Spending for the current
  period is shown as Cost.
- Effective Cost per Addressable TB: This KPI shows the effective cost (actual cost) per terabyte
  of on-premises memory currently available for programs and processes. The secondary KPI shows the
  terabytes of available storage as Addressable Space TB.
- Effective Cost per Allocated TB: This KPI shows the effective cost (actual cost) per terabyte of
  used storage. The secondary KPI shows the terabytes of used storage as Allocated Space TB.
- % Allocated of Addressable Space: This KPI shows the current percentage of addressable space
  that is allocated. The secondary KPI shows the total available terabytes as Available Space TB.

(2) Operational Metrics by Category: This report is similar to the Operational Summary report,
but with additional metrics about average and peak CPU usage, and average and peak memory usage. Use
the options at the top of this chart to display the trending spend for a selected metric based on
the metric selected in the Summarize Costs By.

(3) Table: The table provides the current monthly cost for the metric you select from the
Summarize Costs By list, and the counts, unit costs, average use, and peak of use related CPUs,
servers, memory, and instance hours. The first column changes based on your selection in the
Summarize Costs By column. Select any link in the first column to see the spending trend of Storage
TCO and details about the item selected.

Questions answered:

- How is our Storage utilization strategy evolving?
- Where are we incurring Storage costs?
- Are there anomalies in our Storage utilization?

**Parent topic:** [Costing Standard](../home.html)
