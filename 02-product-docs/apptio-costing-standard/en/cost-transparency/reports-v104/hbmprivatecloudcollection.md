---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Private Cloud VMWare report - HBM"
breadcrumb: []
source_path: "cost-transparency/reports-v104/hbmprivatecloudcollection.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Private Cloud VMWare report - HBM

- Applies to: Hybrid Business Management on TBM Studio TBM Studio and later

Use the Private Cloud VMware report to gain a detailed understanding of your private cloud
infrastructure. The reports allow you to analyze your private cloud spend, better understand your
private cloud with key metrics, and track efficiency month-over-month. Use this report to understand
the overall financial health of your private cloud deployment, with insightful KPIs and high-level
analytics.

This report collection is designed for the following roles:

- Director of IT
- Head of Operations

This report collection aligns to the following business goals:

- Understand utilization of deployed and provisioned resources
- Optimize private cloud spend

## Display the report

1. Log in to Apptio.
2. On the **Home** page, click **Hybrid Business Management**.
3. In the Report collection menu, select **Private Cloud**.

This report has the following elements:

(1) KPIs
:   KPIs provide a high-level view of your private cloud spend:

    - **Cost YTD** - This KPI shows the overall spend on deployed private cloud YTD.
    - **Deployed CPU Cores** - This KPI shows total number of CPU cores used for VMware. The
      secondary KPI shows **Unused CPU Cores**.
    - **Deployed RAM GB** - This KPI shows the total RAM used for VMware in gigabytes. The
      secondary KPI shows total **Unused RAM**.
    - **Deployed Storage GB** - This KPI shows the total storage used for VMware in gigabytes. The
      secondary KPI shows **Unused Storage**.

(2) Cost chart
:   - Click the **Summary** tab to view your monthly spend on provisioned CPU, savings, and
      recommending cost of VMware services. Use the check boxes on the right to show and hide data in the
      chart.
    - Click the **Details** tab to view the **Savings Analysis** table, which provides a more
      in-depth view of the data used to generate the Cost chart. Use the filters on the right to filter
      the Savings Analysis table by Host Reservation and Group Name. Note that these filters do not affect
      the data displayed on the Cost chart.

(3) Capacity Chart
:   This chart shows your monthly capacity for VMware CPU, RAM, and storage. Use the check boxes on
    the right to show and hide data in the chart.

Questions answered:

- What is the cost of my private cloud and unused capacity?
- How much unused capacity can be reclaimed to serve the incoming resource requests from the
  application teams?
- How efficient is my private cloud deployment?
- How many resources are the application teams are using?
