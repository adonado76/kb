---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "TBM Maturity Model"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "TBM Fundementals"
source_path: "studio/new-uc/concepts-architecture/tbm-maturity-model.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# TBM Maturity Model

TBM is a journey, not a destination. Organizations typically progress through stages of
increasing sophistication. Understanding where you are on this journey helps you set realistic
expectations and plan your next steps. The following maturity model provides a roadmap.

## Level 1: Cost Visibility

**Characteristics**

At this stage, the organization has basic awareness of IT costs but limited ability to break them
down by service or consumer. Cost data exists in financial systems but is not structured for TBM
analysis.

**Typical Capabilities** 

- Total IT spend is known at a high level
- Costs can be categorized into broad pools (hardware, software, labor)
- Limited or no allocation of shared costs
- Reporting is ad-hoc, typically in spreadsheets

**TBM Studio Features That Support This Level**

- Data Studio for importing and organizing financial data from GL systems
- Basic transform tables for categorizing costs
- Simple reports showing cost breakdown by category

**Signs You’re Ready to Advance**

- You have consistent, reliable data flowing into TBM Studio
- Stakeholders are asking for more detail (“What’s behind the software number?”)
- You have identified the key drivers that could support allocation

## Level 2: Cost Transparency

**Characteristics**

The organization has implemented cost allocation and can trace IT costs through the taxonomy
layers to services and consumers. Showback reporting is in place, and stakeholders understand what
they are paying for IT.

**Typical Capabilities**

- Full cost allocation from cost pools through towers to services and business units
- Service-level costing is available
- Showback reports are distributed regularly
- Budget vs. actual tracking is in place

**TBM Studio Features That Support This Level**

- Model Studio’s full allocation engine with multi-tier flows
- Multiple model metrics (Cost, Budget, Forecast)
- Report Studio dashboards with row-level security for business unit reporting
- Model reports (Sankey views) for cost flow visualization

**Signs You’re Ready to Advance**

- Your cost model has been validated and stakeholders trust the numbers
- Business units are asking “How can we reduce our costs?”
- You have enough historical data for trend analysis

## Level 3: Cost Optimization

**Characteristics**

The organization uses TBM data actively to identify and pursue cost savings. Trend analysis
reveals patterns, benchmarking highlights opportunities, and optimization initiatives are tracked
and measured.

**Typical Capabilities**

- Period-over-period trend analysis
- Internal and external benchmarking
- Active optimization programs driven by TBM data
- Chargeback may be in place to create financial incentives
- What-if scenario modeling for proposed changes

**TBM Studio Features That Support This Level**

- Calculated metrics for variance analysis and trend computation
- Published tables for exporting data to financial systems (chargeback support)
- Editable tables for scenario planning and data enrichment
- Drill-through capabilities for root cause analysis

**Signs You’re Ready to Advance**

- Cost optimization is delivering measurable savings
- Leadership asks about the business value of IT investments, not just the cost
- You have the data infrastructure to connect IT costs to business outcomes

## Level 4: Value Management

**Characteristics**

The organization connects IT costs to business value. Investment decisions are informed by TBM
data, and IT is positioned as a strategic business partner rather than a cost center. TBM data
drives portfolio management, investment prioritization, and strategic planning.

**Typical Capabilities**

- IT investment portfolio management
- Business value metrics linked to IT cost data
- Strategic decision support for technology investments
- Continuous optimization culture embedded in the organization
- Advanced forecasting and predictive analysis

**TBM Studio Features That Support This Level**

- Full suite of model metrics including custom value-based metrics
- Advanced reporting with calculated metrics combining cost and business data
- API integration for connecting TBM data to enterprise planning systems
- ApptioScript for custom calculations and value modeling

**Signs of Maturity at This Level**

- IT investment decisions are data-driven and tied to business outcomes
- CIO conversations focus on value delivery rather than cost reduction
- TBM data is integrated into enterprise planning and strategy processes

## Maturity Model Summary

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Level** | | **Focus** | **Key Question** | **Primary TBM Studio Areas** |
| **1. Visibility** | | Know what you spend | How much does IT cost? | Data Studio, basic reports |
| **2. Transparency** | | Understand where costs flow | What are we spending on? | Model Studio, Sankey views |
| **3. Optimization** | | Reduce and optimize costs | Where can we save? | Calculated metrics, chargeback, drill-through |
| **4. Value** | | Align IT with business value | What value does IT deliver? | Full platform + API integrations |

Tip: Tip Most organizations operate at Level 2 or 3. There is no need to rush to Level
4. Each level builds upon the previous one, and moving too fast can undermine trust in your cost
data. Focus on mastering your current level before advancing.
