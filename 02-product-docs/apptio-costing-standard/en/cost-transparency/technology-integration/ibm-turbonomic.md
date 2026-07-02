---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "IBM Turbonomic Overview"
breadcrumb:
  - "Costing Standard"
  - "Technology Integrations"
  - "IBM Turbonomic"
source_path: "cost-transparency/technology-integration/ibm-turbonomic.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# IBM Turbonomic Overview

## Overview

IBM Turbonomic integrates with IBM Apptio Costing Standard to provide a unified view of
Hybrid IT cost and optimization opportunities.

This native integration ingests Pending and Executed Actions from Turbonomic into IBM
Apptio’s TBM Studio, where they are standardized, quantified, and aligned to the TBM
framework. Customers gain visibility into the potential and realized financial impact of
infrastructure optimizations across On-Premises, Private Cloud, and Public Cloud environments.

This integration introduces:

- A new IBM Apptio Target Type in Turbonomic that securely pushes optimization output to
  IBM Apptio’s Datadrop.
- Three new TBM Studio content components: Turbonomic – Actions, Hybrid IT Optimization,
  and Hybrid IT Optimization Reporting; that enable ingestion, modeling, and reporting.
- A consistent framework for quantifying optimization opportunities using IBM Apptio Unit
  Cost, Price, Addressable % splits, and Hybrid IT specific metrics such as COIN (Cost
  Optimization Index).

This gives IT Finance, Technical Service Owners, and Solution Owners a new level of
actionable insight, financial quantification, and transparency into Hybrid IT optimization.

## Target Audience

This integration is designed for joint IBM Turbonomic and IBM Apptio customers,
particularly those with an established cost model in IBM Apptio and active optimization
actions in Turbonomic. Target personas include:

**Technical Service Owners (Infrastructure Providers)**

- Need visibility into optimization opportunities across compute, storage, network, and
  cloud
- Require financial quantification to prioritize actions
- Benefit from operational indicators (Pending vs Executed, automation rates, COIN trends)

**Solution / Application Owners (IT Consumers)**

- Want to understand how infrastructure optimizations impact their Applications or
  Services
- Require charge-based views and TBM-aligned rollups (Application Family, Business
  Criticality, Investment Objective)

**IT Finance & TBMAs**

- Want a single place to review Potential & Realized Savings
- Require trusted quantification and attribution aligned to TBM
- Use insights to accelerate cost-reduction cycles and partner with Service Owners

**DevOps / I&O teams (secondary)**

- Benefit from alignment of operational optimization (IBM Turbonomic) and financial impact
  (IBM Apptio)

## Use Cases

**Hybrid IT Optimization Insights in IBM Apptio**

Automatically ingest Pending & Executed Actions from IBM Turbonomic (across On-Prem,
Private and Public Cloud) into IBM Apptio using the IBM Apptio Target Type and Datadrop
workflow to provide insight into Hybrid IT Optimization opportunities.

- Supports granular On-Premises optimization data and aggregated Cloud data
- Exposes actions at the TBM solution level for consumption by multiple stakeholders

**Quantify Optimization Opportunities**

IBM Apptio uses its cost model and Unit Cost/Price to calculate Potential and Realized
Savings.

- On-Premise: Savings = Action Value Change × Unit Cost × Addressable %
- Cloud: Savings sourced directly from IBM Turbonomic
- Savings categorized into Direct Savings, Delayed Savings, and Cost Avoidance

**Align Optimization Data to the TBM framework**

Optimization actions are modeled and reported through the TBM lens:

- Actions are brought in and linked to IBM Apptio’s ATUM framework and connected to the
  Applications/Services/Business Units topology.
- The optimization data gets further enriched with key metadata that speaks to the owners
  of the solution layers (e.g. Business Criticality & Investment Objective)

**Track Realized Savings and Communicate ROI**

After actions execute in IBM Turbonomic, IBM Apptio automatically reflects Realized
Savings, enabling:

- Monthly & YTD savings tracking
- Reporting for Finance, Infra, and Application Owners
- Consistent communication of optimization impact across teams

## Outcomes

This integration delivers measurable financial and operational benefits:

**Operational Outcomes**

- Centralized visibility of optimization actions across Hybrid IT
- Trend analysis for Pending vs Executed actions
- Improved automation rates (Executed vs Pending)
- Identification of under-optimized infrastructure via “Infra without Actions” views

**Financial Outcomes**

- Quantified Potential Savings for prioritization
- Verified Realized Savings from executed actions
- Savings split into Direct, Delayed, and Cost Avoidance, enabling budgeting accuracy
- KPI calculation including Hybrid Cost and COIN index for optimization maturity tracking

**Strategic Outcomes**

- Extends IBM Apptio’s value proposition from Cost Transparency to Optimization
- Strengthens the customer’s ITFM practice by adding ROI-focused insights
- Accelerates time-to-value with a productized integration vs custom work
