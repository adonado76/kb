---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Public Cloud"
breadcrumb:
  - "Costing Standard"
  - "Report NX Walkthrough"
  - "Public Cloud NX Reports"
source_path: "cost-transparency/reports/pc-nx-report.html"
images:
  - "resources/images/ct_images/nx-pctco.png"
  - "resources/images/ct_images/nx-pctco1.png"
  - "resources/images/ct_images/nx-pctco2.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Public Cloud

Use this report to analyze cloud spending across providers, track resource efficiency
through reserved instance utilization and coverage, and identify cost optimization
opportunities.

This report is designed for use by the following personas:

- Cloud Architects
- FinOps Teams
- IT Financial Controllers
- Cloud Operations
- CIO

## Key Elements

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-pctco.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-pctco1.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-pctco2.png)

| Element | Description |
| --- | --- |
| Summary Cards (1) | Five summary cards show cost, reserved instance coverage rate, reserved instance utilization, reserved instance wastage, and cloud credits. |
| Filter Options - Top Row (2) | Five filters let you narrow the report by provider, category, business unit, division, and cost center. |
| Filter Options - Bottom Row (2) | Additional filters let you narrow the report by account name, application, usage family, service name, service category, product, lease type, and location. |
| Tab Navigation (3) | Tabs switch between Overview, KPI Definitions, Filter Definitions, Cloud Credit Details, Cloud Tower Mapping, and Definitions views. |
| Provider Cost Table (4) | This table shows provider, cost, compute usage quantity, and compute cost per 100 units by month. |
| RI Coverage Rate by Month Chart (5) | A line chart shows reserved instance coverage rate over time with benchmark ranges. |
| RI Utilization Rate by Month Chart (5) | A line chart shows reserved instance utilization over time compared with the benchmark. |
| Compute Usage vs Cost Chart (5) | A combined bar and line chart shows compute usage quantity and compute cost per 100 units over time. |
| Compute Cloud Cost vs Cost per 100 Units Chart (5) | A combined bar and line chart shows compute cloud cost and compute cost per 100 units over time. |
| Number of Reserved Instances Chart (5) | A line chart shows the number of reserved instances over time. |
| Total Cloud Cost by Cloud Tower Chart (5) | A bar chart shows total cloud cost by cloud tower. |
| Cloud Tower Tabs (6) | Tabs switch between Compute and RI Overview and Storage Overview views. |
| Dimension Selector Check boxes (7) | Use these checkboxes to show or hide available columns in the analysis table. |

## Questions Answered

- How much am I spending on public cloud services each month?
- What is my Reserved Instance coverage rate and how does it compare to best practices?
- Am I fully utilizing my Reserved Instances or wasting money?
- Which cloud provider (Azure, AWS) costs more?
- What is my cost per 100 compute units and is it increasing or decreasing?
- Which cloud tower (Compute, Storage, Network) consumes the most budget?
- How many cloud credits do I have available?
- Is my number of Reserved Instances increasing or decreasing?
- What is my total cloud wastage and where is it coming from?

## Recommended Actions

- Review the RI Coverage Rate (22.69%) - it's well below the Best In Class range of 75-85%,
  indicating significant opportunity to save money by purchasing more Reserved Instances.
- Check the RI Utilization rate (100%) - this is excellent and shows you're fully using your
  Reserved Instances, but with low coverage, you're paying on-demand rates for most resources.
- Look at the Number of Reserved Instances chart showing a decline from 13,000 to 5,000 -
  investigate why RI count is dropping and whether this aligns with your cloud strategy.
- Review the Total Cloud Cost by Cloud Tower chart to identify which services (Compute, Storage,
  Marketplace) offer the best optimization opportunities.
- Filter by Provider to compare Azure versus AWS spending and determine if you're getting better
  value from one provider.
- Use the Compute Cost per 100 Units trend to track whether your unit costs are improving over
  time or if you need to renegotiate rates or optimize usage.
- Click the Cloud Credit Details tab to understand your $1.5M in credits and ensure they're being
  applied correctly to reduce costs.
