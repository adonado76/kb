---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Storage Insights & Optimization Collection"
breadcrumb:
  - "Costing Standard"
  - "Report Walkthrough"
  - "Storage Collection"
source_path: "cost-transparency/reports-v104/hbmstoragecollection.html"
images:
  - "resources/images/hbm_images/hbmimages/11691_1.png"
  - "resources/images/hbm_images/hbmimages/11691_2.png"
  - "resources/images/hbm_images/hbmimages/11691_3.png"
  - "resources/images/hbm_images/hbmimages/11691_4.png"
  - "resources/images/hbm_images/hbmimages/11691_5.png"
  - "resources/images/hbm_images/hbmimages/11691_6.png"
  - "resources/images/hbm_images/hbmimages/11691_7.png"
  - "resources/images/hbm_images/hbmimages/11691_8.png"
  - "resources/images/hbm_images/hbmimages/11691_9.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Storage Insights & Optimization Collection

♦ Applies to: Hybrid Business Management on TBM Studio TBM Studio and later

Use the Storage reports to understand the cost, capacity, and utilization of your Storage
resources. The reports in this collection allow you to analyze your spend profile, understand
Storage metrics, analyze your storage details (devices and logical units), and understand an
Applications view of your storage. The collection provides granular reporting so you can optimize
storage costs and utilization.

This report collection is designed for the following roles:

- Director of IT
- Compute team in IT
- Head of Operations
- Service Owners

This report collection aligns to the following business goals:

- View Storage costs against plan for both on-premises and cloud servers
- Track Storage infrastructure strategy and use of Storage resources to determine whether Storage
  spending is trending as expected
- View Storage capacity (installed and addressable) and year-over-year changes

These reports enable you to determine the following:

- Whether storage tiers properly aligned with the business criticality of your application
  portfolio
- Storage units that are approaching the end of their serviceable lifecycle
- The cost of unallocated storage capacity
- The average unit cost of total available storage
- The effective unit cost of allocated storage
- The average utilization rate by storage tier
- Opportunities are to reclaim under-utilized storage

## Display the report collection

1. Log in to Apptio.
2. On the **Home** page, click **Hybrid Business Management**.
3. In the Report collection menu, select **Storage**. The **Storage Summary** report opens by
   default.

## Storage Summary report

Use this report to view your overall Storage spend across the enterprise and a view of Storage
costs per IT Tower and Sub-tower.

This report has the following elements:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_1.png)

**(1) KPIs** - KPIs provide a high-level view of your infrastructure spend:

- **On Prem Cost YTD** - This KPI shows the overall spending for on-premise storage servers
  YTD. Spending for the current period is shown as **On Prem Cost**.
- **Public Cloud Cost YTD** - This KPI shows the overall spending for public cloud storage
  servers YTD. Spending for the current period is shown as **Public Cloud Cost**.
- **On Prem Addressable Space TB** - This KPI shows the terabytes of on-premises memory that is
  currently available for programs and processes. The secondary KPI shows the average cost per
  terabyte as **Avg Cost per Addressable TB**.
- **Public Cloud Used Space TB** - This KPI shows the terabytes of public cloud memory
  currently in use. The secondary KPI shows the average cost per terabyte of used space as **Avg Cost
  per Used Space TB**.

**(2) Storage Spend Month Over Month** - Use this chart to view the 1-year trending spend for
Storage resources across your on-premises and public cloud servers.

**(3) Storage Costs by** - Click the **Cost Pools**, **IT Towers**, **Environment**,
or **Vendors** tabs to view charts of the current Compute spending for the month. The
**Details** table lists the spending of the current month, QTD, and YTD.

Questions answered:

- Are there anomalies in our spending?
- Is the spending in line with our Storage strategy?
- How is the infrastructure strategy evolving?
- Where are we incurring Storage costs?

## Spend Profile report

Click **Spend Profile** in the Report collection tab to open the report. Use this report to
view the planned spend and utilization of Storage resources.

This report has the following elements:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_2.png)

**(1) KPIs** - KPIs provide a high-level view of your infrastructure spend:

- **Cost YTD** - This KPI shows the overall spend on servers YTD. Spending for the current
  period is shown as **Cost**.
- **Installed Space TB** - This KPI shows the amount of used storage capacity in terabytes. The
  secondary KPI shows the average cost per installed terabyte as **Avg Cost per Installed
  TB**.
- **Addressable Space TB** - This KPI shows the terabytes of on-premises memory that is
  currently available for programs and processes. The secondary KPI shows the average cost per
  terabyte as **Avg Cost per Addressable TB**.
- **YoY Installed TB Cost Change** - This KPI shows the year-over-year change in the cost of
  installed on-premises memory.

**(2) Current Month Spend by Cost Pool** - Use this chart to view the Storage spending per
cost pool for the current month.

**(3) Addressable Space (TB) and Avg Cost per** - Use this chart to view the amount of
available memory in terabytes per month and the average cost of that space.

**(4) Storage YTD pie charts** - The pie charts show the relationship of a specific type of
storage by tier, by location, or by manufacturer. Use this information as a quick overview of your
Storage spending profile.

Questions answered:

- Are there anomalies in our spending?
- Is the spending in line with our Storage strategy?
- How is the infrastructure strategy evolving?
- Where are we incurring Storage costs?

## Operational Summary

Click **Operational Summary** in the Report collection tab to open the report. Use this report
to understand the operational metrics (such as cost, average cost, addressable space in terabytes)
of your on-premises storage.

This report has the following elements:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_3.png)

**(1) KPIs** - The KPIs in this report are the same as in the Storage Spend Profile. See
element 1 in the [Storage Spend Profile report](hbmstoragecollection.html).

**(2) Filters** - The following filters are available in this report. These filters are
cumulative, and affect all data on the page, including the KPIs:

- **Location** - Select a specific location to see the impact of Storage spending for that
  location.
- **Manufacturer** - Select a specific cloud service provider to limit the data in the report
  to the services from that provider.
- **Type** - Select a type of server purpose to see the impact of Storage spending on servers
  by type.

**(3) Operational Metrics by Category** - Use the options at the top of this chart to
selectively display various metrics. Additional metrics are available in the **Summarize Cost
By** list. Use the chart to view the current Storage spending based on the metric you select.

**(4) Device Details** - This table provides the current monthly cost per location for the
metrics you select from the **Summarize By** list. Click any link in the first column to see the
spending trend of Storage TCO and details about the selected item.

Questions answered:

- How is our Storage strategy evolving?
- Where are we incurring Storage costs?
- Are there anomalies in our Storage spending?

## Utilization Summary

Click **Utilization Summary** in the Report collection tab to open the report. Use this report
to understand the impact of your on-premises storage resources on the cost, and to view utilization
metrics (such as storage cost, addressable space, percentage of allocated space, percentage of used
space, and cost per terabyte) for your on-premises Storage resources.

This report has the following elements:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_4.png)

**(1) KPIs** - KPIs provide a high-level view of your host server spending:

- **Cost YTD** - This KPI shows the overall spend on storage devices YTD. Spending for the
  current period is shown as **Cost**.
- **Effective Cost per Addressable TB** - This KPI shows the effective cost (actual cost) per
  terabyte of on-premises memory currently available for programs and processes. The secondary KPI
  shows the terabytes of available storage as **Addressable Space TB**.
- **Effective Cost per Allocated TB** - This KPI shows the effective cost (actual cost) per
  terabyte of used storage. The secondary KPI shows the terabytes of used storage as **Allocated
  Space TB**.
- **% Allocated of Addressable Space** - This KPI shows the current percentage of addressable
  space that is allocated. The secondary KPI shows the total available terabytes as **Available Space
  TB**.

**(2) Operational Metrics by Category** - This report is similar to the Operational Summary
report, but with additional metrics about average and peak CPU usage, and average and peak memory
usage. Use the options at the top of this chart to display the trending spend for a selected metric
based on the metric selected in the **Summarize Costs By**.

**(3) Table** - The table provides the current monthly cost for the metric you select from the
**Summarize Costs By** list, and the counts, unit costs, average use, and peak of use related
CPUs, servers, memory, and instance hours. The first column changes based on your selection in the
**Summarize Costs By** column. Click any link in the first column to see the spending trend of
Storage TCO and details about the item selected.

Questions answered:

- How is our Storage utilization strategy evolving?
- Where are we incurring Storage costs?
- Are there anomalies in our Storage utilization?

## Device Details

Click **Device Details** in the Report collection tab to open the report. Use this report to
view your spending for on-premises servers and physical storage devices (network-attached storage
[NAS] and storage area networks [SAN]). The report provides the cost, cost YTD, and metrics related
to space allocation and use.

This report has the following elements:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_5.png)

**(1) KPIs** - The KPIs in this report are the same as in the Storage Utilization Summary. See
element 1 in the [Utilization Summary report](hbmstoragecollection.html).

**(2) Filters** - The filters in this report are the same as in the Storage Operational
Summary. See element 2 in the [Storage - Spend Profile report](hbmstoragecollection.html).

**(3) Storage Device Additional Details**

- Use the options at the top of this chart to add columns for **Location** and
  **Manufacturer** to the chart.
- Use the table to view details about specific storage devices and quickly understand installed
  space versus addressable space versus allocated space.
- Click any link in the **Supported Apps** column to view information about the applications
  that use the storage device.

  ![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_6.png)

Questions answered:

- How is our Storage strategy for devices evolving?
- Where are we incurring Storage device costs?

## Storage LUN Details

Click **Storage LUN Details** in the Report collection tab to open the report. Use this report
to view your Storage spending by logical unit number (LUN). The report provides the cost for the
current period, cost YTD, total space, and used space.

This report has the following elements:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_7.png)

**(1) KPIs** - The KPIs in this report are the same as in the Storage Utilization Summary. See
element 1 in the [Utilization Summary report](hbmstoragecollection.html).

**(2) Filters** - The filters in this report are the same as in the Storage Operational
Summary. See element 2 in the [Operational Summary report](hbmstoragecollection.html).

**(3) Storage LUN Additional Details** - Use the options at the top of the table to add
columns that list the **Purpose** and **Location**. Use the table to view the current monthly
cost, cost YTD, total space, and used space for your logical storage. Click any link in the
**Supported Apps** column to view information about the applications that use the storage
device.

Questions answered:

- How is our logical server strategy evolving?
- Where are we incurring costs?

## Financial View

Click **Financial View** in the Report collection tab to open the report. Use this report as a
financial view of your Storage spending per location, type, manufacturer, product, model, or
source.

This report has the following elements:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_8.png)

**(1) KPIs** - The KPIs in this report are the same as in the Storage Spend Profile. See
element 1 in the [Spend Profile report](hbmstoragecollection.html).

**(2) Cost YTD By** - Use the options at the top of this chart to view the spending YTD for
Storage resources per cost pool (Outside Services, Hardware, etc.) versus IT Sub-tower (Servers,
Transport, Voice, etc.). This information provides an overview of your overall Storage spending per
ATUM Tower and Sub-tower.

**(3) Table** - The table shows the same data month-by-month, based on your selection in the
**Summarize Costs By** list. Click any link in the first column to view infrastructure cost pool
details about the item you click.

- How is our Storage strategy evolving?
- Where are we incurring Storage costs?
- Are there anomalies in our Storage spending?

## By Applications

Click **By Applications** in the Report collection tab to open the report. Use this report to
view your Storage spending per application across your entire virtualization profile.

This report has the following elements:

![](../../../../../03-media/apptio-costing-standard/resources/images/hbm_images/hbmimages/11691_9.png)

**(1) KPIs** - The KPIs in this report are the same as in the Storage Spend Profile. See
element 1 in the [Spend Profile report](hbmstoragecollection.html).

**(2) Storage LUN by Application** - Use this table to view the spending YTD for Storage LUN
resources per application (for example, Active Directory, SAP Data Warehouse, and Office 365). The
table shows the application owner, allocated space and percentages per tier and environment for each
application. Click any link in the **Application Name** column to view infrastructure cost pool
details about the application you click.

Questions answered:

- How is our Storage strategy evolving?
- Where are we incurring Storage costs?
- Are there anomalies in our Storage spending?
