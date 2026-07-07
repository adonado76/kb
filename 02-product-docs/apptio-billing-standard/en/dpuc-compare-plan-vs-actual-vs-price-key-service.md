---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Compare plan vs actual vs price for a key service"
breadcrumb:
  - "Design Patterns and Use Cases"
  - "Compare plan vs actual vs price for a key service"
source_path: "SSV8ML/boit/billing/design-uc/uc-compare.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Compare plan vs actual vs price for a key service

Problem

You want to understand if a key service is under or over recovering relative to plan and cost.

Inputs

- Actual cost per service (from Costing)
- Plan or budget per service (from planning tools or tables)
- Price per unit for the service
- Actual units and charges from Billing

Steps

1. Confirm plan data is loaded and aligned with the service and consumer structure used in Billing.
1. Open a Plan vs Actual vs Price report : Filter to the service and relevant periods (for example, year-to-date).
1. For each period, review: Plan cost per unit. Actual cost per unit. Price per unit. Variance columns: Actual vs plan. Price vs cost.
1. Identify patterns: Persistent under recovery (price < cost). Persistent over recovery (price > cost). Large swings due to volume change.
1. Summarize findings and potential actions: Adjust rates. Adjust cost drivers or allocations in Costing. Revisit service design or consumption patterns.

Key reports

- Service-level Plan vs Actual vs Price report
- Consumer-level variance report for the same service
- Unit-rate trend view for the service
