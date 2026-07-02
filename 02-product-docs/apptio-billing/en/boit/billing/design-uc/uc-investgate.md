---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Investigate a unit rate spike"
breadcrumb:
  - "Billing"
  - "Design Patterns and Use Cases"
source_path: "boit/billing/design-uc/uc-investgate.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Investigate a unit rate spike

**Problem**

A stakeholder reports that the rate for a particular service “jumped” this month. You need to
explain why.

**Inputs**

- Historical unit rate data for the service
- Costing outputs for that service (if available)
- Consumption volumes over time
- Rate table history

**Steps**

1. Open the **unit rate analysis report** for the service:
   - Filter to the service, current period, and at least three prior periods.
2. Compare:
   - Units per period
   - Charges per period
   - Unit rate per period
3. Determine which driver changed:
   - Units moved significantly with cost stable: likely volume-driven.
   - Cost per unit changed: likely allocation or cost driver change in Costing.
   - Explicit rate change: check the rate table.
4. Cross-check the **rate table**:
   - Confirm if a rate change was configured for the period.
   - If yes, verify that change was approved and documented.
5. If cost is available from Costing:
   - Compare **cost per unit** vs **price per unit** across periods.
6. Summarize findings in simple terms:
   - “Unit rate increased because volume dropped by X% on a mostly fixed cost base.”
   - “Unit rate increased because the rate was changed from A to B per unit.”
   - “Unit rate changed because underlying cost allocation changed in Costing.”

**Key reports**

- Unit rate trend report for the service
- Rate history (rate table view)
- Cost vs price comparison view (if configured)
