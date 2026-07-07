---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Investigate a unit rate spike"
breadcrumb:
  - "Design Patterns and Use Cases"
  - "Investigate a unit rate spike"
source_path: "SSV8ML/boit/billing/design-uc/uc-investgate.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Investigate a unit rate spike

Problem

A stakeholder reports that the rate for a particular service “jumped” this month. You need to explain why.

Inputs

- Historical unit rate data for the service
- Costing outputs for that service (if available)
- Consumption volumes over time
- Rate table history

Steps

1. Open the unit rate analysis report for the service: Filter to the service, current period, and at least three prior periods.
1. Compare: Units per period Charges per period Unit rate per period
1. Determine which driver changed: Units moved significantly with cost stable: likely volume-driven. Cost per unit changed: likely allocation or cost driver change in Costing. Explicit rate change: check the rate table.
1. Cross-check the rate table : Confirm if a rate change was configured for the period. If yes, verify that change was approved and documented.
1. If cost is available from Costing: Compare cost per unit vs price per unit across periods.
1. Summarize findings in simple terms: “Unit rate increased because volume dropped by X% on a mostly fixed cost base.” “Unit rate increased because the rate was changed from A to B per unit.” “Unit rate changed because underlying cost allocation changed in Costing.”

Key reports

- Unit rate trend report for the service
- Rate history (rate table view)
- Cost vs price comparison view (if configured)
