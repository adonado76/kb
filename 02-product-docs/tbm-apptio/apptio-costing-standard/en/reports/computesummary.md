---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Compute Summary"
breadcrumb: []
source_path: "reports/computesummary.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Compute Summary

This report provides an overview of total Compute spend in the enterprise, across
on-premises and cloud, as well as helps to visualize the spend across dimensions such as Cost pools,
Environments, Vendors, and IT Towers.

This report has the following elements:

![](../../resources/images/ct_images/ct%20report%20collections/compute%20summary.png)

(1) KPIs: KPIs provide a high-level view of your infrastructure spend:

- Cost YTD: This KPI shows the overall spend on Compute YTD. Spending for the current period is
  shown as Cost.
- Server Count: This KPI shows the current number of on-premises servers. The secondary KPI
  shows the percentage of virtual servers as % Virtualized Servers.
- Virtual Instance Hours: This KPI shows the current usage (in instance hours) of your virtual
  servers. The secondary KPI shows Cost per Instance Hour.
- Cloud Instance Hours: This KPI shows the current usage (in instance hours) of your public and
  cloud servers. The secondary KPI shows Cost per Instance Hour.

(2) Filters: The following filters are available in this report. These filters are cumulative,
and affect all data on the page, including the KPIs:

- Virtualization Profile: Select a specific type of on-premises or cloud server to see the
  impact of Compute spending on that server type.
- OS: Select a specific operating system (OS) to see the impact of Compute spending on that
  OS.
- Environment: Select a specific environment (such as Dev, Prod, or Test) to limit data in the
  report to servers in that environment.
- Location: Select a specific location to see the impact of Compute spending for that
  location.
- Purpose: Select a specific server purpose to see the impact of Compute spending on servers
  with the same purpose.

(3) Compute Spend Month Over Month: Use this chart to view the 1-year trending spend for Compute
resources across your on-premises and public cloud servers.

(4) Compute Costs by: Select the Cost Pools, IT Towers, Environment, or Vendors tabs to view
charts of the current Storage spending for the month. The Details table lists the spending of the
current month, QTD, and YTD.

Questions answered:

- Are there anomalies in our spending?
- Is the spending in line with our Compute strategy?
- How is the infrastructure strategy evolving?
- Where are we incurring Compute costs?

**Parent topic:** [Costing Standard](../home.html)
