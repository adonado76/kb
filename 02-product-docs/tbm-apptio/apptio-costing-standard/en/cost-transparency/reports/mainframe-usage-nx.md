---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Mainframe Usage"
breadcrumb:
  - "Costing Standard"
  - "Report NX Walkthrough"
  - "Mainframes NX Reports"
source_path: "cost-transparency/reports/mainframe-usage-nx.html"
images:
  - "resources/images/ct_images/mf-nx-usage2.png"
  - "resources/images/ct_images/nx-mf-usage1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Mainframe Usage

Use this report to understand processor consumption, evaluate usage across categories and
time periods, and identify trends to support capacity planning and workload optimization. Apply
filters and available views to focus on the data relevant to your analysis.

This report is designed for use by the following personas:

- Capacity Planners
- Performance Analysts
- IT Operations Managers
- Infrastructure Architects

## Key Elements

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-mf-usage1.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/mf-nx-usage2.png)

| Element | Description |
| --- | --- |
| Filter controls (1) | Five filters let you narrow the report by product line name, product name, processor complex name, location, and environment. |
| MSU consumption tabs (2) | Two tabs let you switch between GCP and zIIP MSU consumption views. |
| Dimension selector (3) | Use this dropdown to select which dimension to view in the charts, such as Product Line Name. |
| GCP by category chart (4) | This horizontal bar chart shows GCP MSU consumption by category, such as Credit Cards, Customer Engagement, Loans, Wealth Management, and Underwriter Solutions. |
| GCP trend chart (5) | This stacked bar chart shows GCP MSU consumption trends over time by category, with monthly data points from August FY2021 to August FY2021. |
| MSU variance details tabs (6) | Three tabs let you view variance data by time period: MoM (Month over Month), QoQ (Quarter over Quarter), and YoY (Year over Year). |
| MSU variance details table (7) | This table shows MSU variance data with columns for product line name, GCP MSU values, and MoM GCP MSU percentage changes across multiple months. The table includes a total row and pagination controls. |

## Questions answered

- Which product lines consume the most processor capacity?
- How is processor consumption trending over time across different categories?
- What are the month-over-month and year-over-year changes in MSU consumption?
- Which areas show increasing or decreasing processor usage patterns?
- How is workload distributed between GCP and zIIP processors?
- Are there seasonal patterns or anomalies in processor consumption?
- Which product lines might benefit from workload optimization or processor type changes?

## Recommended Actions

- Switch between GCP and zIIP tabs to compare consumption across processor types.
- Review the variance details to understand month-over-month and year-over-year changes.
- Identify product lines with significant consumption increases and investigate the causes.
- Filter by product line or environment to focus on specific areas of interest.
- Analyze trends to forecast future capacity needs and plan infrastructure investments.
- Export usage data to share with capacity planning and operations teams.
- Compare GCP and zIIP usage to identify workloads that could be migrated to specialized
  processors.
