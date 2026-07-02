---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Unit rate analysis and optimization"
breadcrumb:
  - "Billing"
  - "Advanced Topics"
source_path: "boit/billing/advance-topic/unit-rate-analysis.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Unit rate analysis and optimization

Unit rates are often the heart of Billing conversations. This subsection focuses on how
to analyze and tune them over time.

## Basic unit rate analysis

Key questions:

- What is the unit rate for each offering this period?
- How has that unit rate changed over time?
- Are changes driven by cost, volume, or price decisions?

Typical inputs:

- **Units**
  - From Billing consumption tables.
- **Charges**
  - From Billing output tables.
- **Cost per unit**
  - From Costing outputs where available.

Basic analysis patterns:

- Calculate unit rate as Charge / Units for each offering and period.
- Compare current period unit rate vs:
  - Prior period.
  - Same period last year.
- Compare unit rate vs cost per unit (if cost is available).

Use this view to identify:

- Offerings with rising unit rates and flat or declining volumes.
- Offerings with sudden drops in unit rate that may signal data or rate configuration
  issues.

## Understanding unit rate movements

Common drivers of unit rate changes:

- **Cost changes**
  - Upstream cost increases in Technology towers or vendors.
  - Changes in allocation logic in Costing.
- **Volume changes**
  - Fixed costs spread over significantly more or fewer units.
  - One-time migrations or retirements.
- **Price changes**
  - Explicit decisions to change rates, adjust recovery, or introduce discounts.

Helpful report patterns:

- For each offering and period:
  - Units, cost per unit, price per unit, and variance columns.
- Trend charts:
  - Unit rate over time alongside volume trend.

Use these patterns to separate structural issues (data or model changes) from conscious
business decisions (new rate strategy).

## Optimization levers

When unit rates look off, the typical levers are:

- Improve cost drivers and allocations in Costing.
- Adjust service design or catalog structure.
- Change rates or recovery targets.
- Reduce underlying cost (for example, vendor renegotiation, cloud optimization).

Billing surfaces the unit rate behavior. The implementation work to optimize it is usually
done in Costing models, domain designs, and sourcing decisions.
