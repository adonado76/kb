---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Validating current period bills"
breadcrumb:
  - "Billing"
  - "Running the Billing Cycle"
source_path: "boit/billing/run-bill-cycle/validating.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Validating current period bills

Validation is where most billing issues are caught before they reach
consumers.

Typical validations:

1. **Structural checks**
   - Confirm that:
     - Every consumer expected to be billed has at least one charge.
     - New or retired consumers are handled correctly.
     - Offerings marked as billable actually appear.
2. **Volume checks**
   - Compare units for the current period against:
     - Prior periods.
     - Known business events, such as migrations, new rollouts, or retirements.
   - Investigate:
     - Large spikes or drops.
     - Major shifts between offerings.
3. **Rate checks**
   - Confirm that:
     - The correct rate is applied for the current period.
     - Special rates or discounts are used where agreed.
     - No default or placeholder rates are used where they should not be.
4. **Charge reasonableness**
   - Check total charges:
     - By consumer.
     - By offering or service.
   - Compare against:
     - Budget or plan.
     - Costing outputs for cost based implementations.

1. **Reconciliation with Costing**
   - For chargeback scenarios, confirm that:
     - Total Billing charges approximate the Costing view of recoverable cost.
     - Any gap between cost and charges is understood and documented as planned
       variance.

For Billing Standard, some validations can be done at domain level (for example, cloud,
servers, projects) instead of only at the offering level. The same principles apply.
