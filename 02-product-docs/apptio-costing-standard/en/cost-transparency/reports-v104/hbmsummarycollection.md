---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Summary Report Collection"
breadcrumb:
  - "Costing Standard"
  - "Report Walkthrough"
  - "Previous Version Layouts"
  - "Hybrid Business Management Reports"
source_path: "cost-transparency/reports-v104/hbmsummarycollection.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Summary Report Collection

Use the Summary report collection to view your cost, capacity, and utilization for both
on-premises and public cloud servers. The reports allow you to analyze your spend, better understand
your complete infrastructure with key metrics, and understand the cost differences between public
and private clouds. Use this report collection to understand the overall financial health of your
deployment against plan, with actionable, insightful KPIs and high-level analytics. This information
is especially helpful in developing an efficient cloud migration strategy.

This report collection is designed for the following roles:

- VP or Director of Infrastructure or IT
- CIO or CTO

## Display the report collection

1. Log in to Apptio.
2. On the **Home** page, click **Hybrid Business Management**.
3. In the Report collection menu, select **Summary**. The **Deployment** report opens by
   default.

## Deployment report

Use the HBM Deployment report to understand the overall cost of your servers so you can compare
the cost of running on-premises servers versus and public cloud servers.

**TIP**: *Deployment* refers to the location of your on-premises or public cloud servers.
On-premises deployments can include private cloud servers, on-premises data centers, MSP data
centers, co-lo, etc.

**Use cases**:

- View infrastructure costs against plan
- View the balance of on-premises and public cloud spending
- Track infrastructure strategy and use of cloud resources
- Track the balance between Server, Storage, and Network IT Resource Towers to determine whether
  infrastructure spending is trending as expected

This report contains the following elements:

**(1) KPIs** - KPIs provide a high-level view of your infrastructure spend. The arrows
indicate the current actual spend as a percentage over or under plan, which is displayed as
secondary metric.

- **Infrastructure Cost YTD** - This KPI shows the overall infrastructure spend YTD, with the
  percentage over or under plan. Planned spend is shown as **Target Spend YTD**.
- **On Prem Cost YTD** - This KPI shows the overall cost of on-premises server usage YTD, with
  the percentage over or under plan. Planned spending is shown as **On Prem Target Spend**.
- **Public Cloud YTD** - This KPI shows the overall cost of your public cloud server usage YTD,
  with the percentage over or under plan. Planned spending is shown as **Public Cloud
  Target**.

**(2) Infrastructure Cost Summary** - Use this chart to view the overall trend of spend across
public cloud and on-premises infrastructure. Click the **3 Years** tab to view the trend over
multiple years.

Questions answered:

- Is my overall infrastructure spend in line with my infrastructure strategy?
- Is the spend trending according to plan?

**(3) Public Cloud Deployment** - Use this chart to view a 12-month summary of spending for
public cloud servers for the current year, broken out by the Compute, Storage, and Network IT
Resource Towers. Click the **3 Years** tab to view data per year for the current and two previous
years. The table on the right provides the percentage of change between actual spend and plan for
the current period.

Questions answered:

- How is the infrastructure strategy evolving?
- Is our use of cloud resources too high?
- Is our strategy to move to cloud working well?
- Which resources (compute/storage/network) form the biggest part of our on-premises and cloud
  usage? Is it as expected?

**(4) On Prem Deployment** - Use this chart to view a 12-month summary of spend for
on-premises servers for the current year, broken out by the Compute, Storage, and Network IT
Resource Towers. Click the **3 Years** tab to view data per year for the current and two previous
years. The table on the right provides the percentage of change between actual spending and plan for
the current period.

Questions answered:

- How is the infrastructure strategy evolving?
- Is our use of cloud resources too high?
- Is our strategy to move to cloud working well?
- Which resources (server/storage/network) form the biggest part of our on-premises and cloud
  usage? Is it as expected?

## Domains report

Click **Domains** in the Report collection tab to open the report. Use the HBM Domains report
to understand the distribution of on-premises and public cloud services across various domains. The
report allows you to see the spend on your infrastructure domains, capacity and unit costs.

**TIP**: *Domains* refers to the IT Resource Towers in the ATUM taxonomy: Compute,
Storage, Data Centers, and Network.

**Use cases**:

- View infrastructure costs by IT resource tower
- Understand how cost and capacity are distributed across Compute and Storage for different
  deployments
- Determine whether resource capacity is correctly distributed across on-premises and cloud
  deployments regarding capacity and unit cost
- High level view of on-premises data center costs

The report contains the following elements:

**(1) KPIs** - The KPIs in this report are the same as in the Deployment report. See element 1
in the [Deployment report](hbmsummarycollection.html).

**(2) Infrastructure Tower Summary** - Use this chart to see 1-year or 3-year trending spend
per domain (Compute, Storage, Date Centers, and Network) for on-premises and cloud servers.

Questions answered:

- Is my overall infrastructure spend in line with plan?
- Does the distribution of spend across domains align with plan?

**(3) Compute** - Click **Compute** to jump to the **Compute Summary** report.

- The **Compute Cost** tab shows the 1-year trending spend on Compute resources per deployment.
  The table to the right lists costs for the current month and the percentage of change in spend since
  the previous month.
- Click the **Compute Capacity** tab to view the 1-year trend of instance hours used per
  deployment. The table to the right lists usage of instance hours for the current month and the
  percentage of change in usage since the previous month.
- Click the **Compute Unit Cost** tab to view the 1-year trend of instance hour cost per
  deployment. The table to the right lists the cost per instance hour for the current month.

Questions answered:

- How are Compute costs and capacity distributed across different deployments?
- Does the unit cost metric prove/disprove our hypothesis of migration to cloud strategy?
- Do we have high or low on-premises or cloud spending? Why?

**(4) Storage** - Click **Storage** to jump to the **Storage Summary** report.

- The **Storage Cost** tab shows the 1-year trending spend on Storage resources per deployment.
  The table to the right lists costs for the current month and the percentage of change in spending
  since the previous month.
- Click the **Storage Capacity** tab to view the 1-year treading capacity for on-premises
  addressable space and public cloud used space.
- Click the **Storage Unit Cost** tab to view the 1-year trending unit cost for on-premises
  addressable space and public cloud used space.

Questions answered:

- How are Storage costs and capacity distributed across different deployments?
- Does the unit cost metric prove/disprove our hypothesis of migration to cloud strategy?
- Do we have high or low on-premises or cloud spending? Why?
- Is the resource capacity correctly distributed across on-premises vs cloud?

**(5) Data Center** - Click **Data Center** to jump to the **Data Center Summary**
report. Use this chart and table to view the trending cost of your data centers. This information
can help you evaluate changes in costs YTD and the cost of your data centers per square foot.

Questions answered:

- Are there anomalies in resource usage?
- Is the organization spending a lot on one of these domains/resources? Why?

## Public vs Private Cloud report

Click **Public vs Private Cloud** in the Report collection tab to open the report. Use the
Public vs Private Cloud report to understand the total cost of ownership (TCO) of public cloud and
private cloud services. The report allows you to see the trending spend for public cloud per IT
Tower (service category) and the trending spend for private cloud per host reservation. This
information is especially helpful in analyzing resource efficiency and capacity.

**TIP**: *Private cloud* is an infrastructure deployment model that is run as cloud in
the cloud, but managed by the enterprise. It does not have shared resources like public cloud.

**Use cases**:

- Compare public cloud TCO with private cloud
- Understand your current CPU, RAM, and storage costs
- Track resource usage over time to inform your migration-to-cloud strategy
- Determine whether costs align with the resources and capacity across deployments

The report contains the following elements:

**(1) KPIs** - The KPIs in this report are the same as in the Deployment report. See element 1
in the [Deployment report.](hbmsummarycollection.html)

**(2) Public Cloud TCO** - Click **Public Cloud TCO** to go to the Public Cloud home page.
Use this chart to view the 1-year trending spend per domain per service. The table to the right
lists the cost of each service for the current period and the percentage of change since the
previous period. Click the **3 Years** tab to view data per year for the current and two previous
years.

Questions answered:

- Is my overall public cloud spending in line with plan?
- Does the distribution of spending across service category align with plan?

**(3) Private Cloud** - Click **Private Cloud** to go to the Private Cloud - VMWare report.
Use this chart to view the 1-year trending spend of all provisioned private cloud servers and the
trending cost per private cloud host. The table to the right lists CPU, RAM, and storage costs for
the current period. Click the **3 Years** tab to view data per year for the current and two
previous years.

Questions answered:

- Is my overall private cloud spending in line with plan?
- At a summary level, are the resources being used efficiently?
- What's the cost of unused capacity?
- Can I reuse this capacity before purchasing more resources to meet the upcoming demands in the
  organization?

## Infrastructure Variance report

Click **Infrastructure Variance** in the Report collection tab to open the report. Use this
report to understand actual infrastructure costs compared to budget. The report provides various
views of infrastructure variances to help you analyze budget efficiency and spending. This
information is especially useful to determine whether infrastructure spending aligns with the
budget, and whether the budget needs to be revised.

**Use cases**:

- Compare actual spend for infrastructure to target spend
- Understand your current costs per IT Resource Tower
- Track spend variance for the current month, quarter, and year

The report contains the following elements:

**(1) KPIs** - The KPIs in this report are the same as in the Deployment report. See element 1
in the [Deployment report](hbmsummarycollection.html).

**(2) Actual vs Target Spend** - Use this chart to view and 1-year trend of actual cost vs
plan for infrastructure spend. The **Deployment** filter allows you to narrow the data to
on-premises data or public cloud data. The **Details** table lists costs per IT Tower by
month.

Questions answered:

- How are my actual infrastructure costs trending compared to planned spend?
- Am I in-line with budget?
- Should I revise my budget?

**(3) Actual Plan Spend Variance** - This chart shows the variance between the infrastructure
spend YTD versus plan per the metric you select from the list. Red bars on the left represent costs
over budget. The table to the right lists costs YTD, target spend, and variance for each metric
based on your selection from the list. Click the **Quarter to Date** or **Current Month** tabs
to toggle between date ranges.

Questions answered:

- What's the variance between my planned and actual spend?
- Where's the biggest variance?
