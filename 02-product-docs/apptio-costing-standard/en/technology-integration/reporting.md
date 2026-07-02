---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "technology-integration"
title: "Reporting"
breadcrumb: []
source_path: "technology-integration/reporting.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Reporting

The Hybrid IT Optimization Reporting component installs two reports as part of a new reporting collection called "Hybrid IT".

## Common KPIs Report

This report focuses on presenting key performance indicators across various operational and
financial dimensions.

![](../../resources/images/ct_images/trb-rep-1.jpg)

## Infrastructure Optimization Insights – Provider Report

This report is targeted at technical service providers responsible for managing infrastructure
optimization.

**Target Personas** 

- Technical Service Owner (e.g., Head of Compute)
- IT Finance

**Summary Tab**

The Summary tab allows users to perform:

- Trend Analysis for Hybrid Cost, Potential Savings, and Realized Savings
- Savings Analysis based on key dimensions such as Operational Category, Action Type, and
  Infrastructure Class
- A breakdown of Net Savings into Actual Savings vs. Necessary Investments

  ![](../../resources/images/ct_images/trb-rep-2.jpg)

**Financial Insights Tab**

The Financial Insights tab enables:

- A view of Potential Savings by Environment, Vendor, and categories like Direct, Delayed, or Cost
  Avoidance
- Pivoting by Offering, allowing insights into financial performance at a Technical Service Owner
  level
- COIN Index + Status, pivotable by Owner or Category
- Unit Economics, showing the relationship between actions and realized savings, which helps
  prioritize actions with the highest impact

  ![](../../resources/images/ct_images/trb-rep-summ.jpg)

**Operational Insights Tab**

The Operational Insights tab provides:

- Pending Action Counts, grouped by Environment and Infrastructure Class
- Insights into the automation rate of executed actions
- Optimization Impact, showing how much of the infrastructure is optimized by IBM Turbonomic
  versus the portion that is either fully optimized or not yet in scope
- Breakdown of actions into Pending vs. Executed and analysis of total actions, highlighting key
  areas

  ![](../../resources/images/ct_images/trb-rep-fin.jpg)

**Trend Tab**

The Trend tab offers the following insights:

- COIN Trend to monitor the rate of executed vs. pending actions
- Executed Actions trend over time
- Pending Actions trends, either decreasing due to more actions being executed or increasing as
  more infrastructure comes under optimization scope
- All trends are pivotable by various dimensions

  ![](../../resources/images/ct_images/trb-rep-opr.jpg)

**On-Prem Details Tab**

The On-Prem Details tab provides:

- Analysis of Potential Savings and Realized Savings at the Infra ID/Name level
- Savings quantification based on the unit cost at the Technical Service Offering level,
  multiplied by the quantity delta specific to each Infra ID
- Insights into infrastructure without identified optimization opportunities, indicating either
  fully optimized infrastructure or items not yet in scope

  ![](../../resources/images/ct_images/trb-rep-trnd.jpg)

**Workbench Tab**

The Workbench tab contains:

- Unit Rate Card, an editable report where users set the Addressable %, along with breakdowns for
  Direct, Delayed, and Cost Avoidance savings
- Editable tabs for Target & Settings and Filter Edits

  ![](../../resources/images/ct_images/trb-rep-onprem.jpg)

## Infrastructure Optimization Insights – Consumer Report

This report provides insights from the perspective of consumers of infrastructure services,
primarily application owners.

**Target Personas** 

- Solution Owner, primarily focusing on the Application Owner
- This view can be extended to higher-level views, such as Services and Business Units (BU)
  personas

**Key Differences from Provider View** 

- Charge is used instead of Cost, as this view is focused on consumption
- Key dimensions focus on Application-related metadata, such as Business Criticality and
  Investment Objective
- It offers fewer granular views, without an On-Prem Details tab or a Workbench Tab

  ![](../../resources/images/ct_images/trb-rep-3.jpg)

Note: This content is part of an Early Access release and is expected to evolve as customers onboard
and provide feedback, leading to further improvements and refinements in the reporting capabilities.

**Parent topic:** [Costing Standard](../home.html)
