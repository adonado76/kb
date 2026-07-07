---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Validating current period bills"
breadcrumb:
  - "Running the Billing Cycle"
  - "Validating current period bills"
source_path: "SSV8ML/boit/billing/run-bill-cycle/validating.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Validating current period bills

*Validation is where most billing issues are caught before they reach consumers.*

Typical validations:

1. Structural checks Confirm that: Every consumer expected to be billed has at least one charge. New or retired consumers are handled correctly. Offerings marked as billable actually appear.
1. Volume checks Compare units for the current period against: Prior periods. Known business events, such as migrations, new rollouts, or retirements. Investigate: Large spikes or drops. Major shifts between offerings.
1. Rate checks Confirm that: The correct rate is applied for the current period. Special rates or discounts are used where agreed. No default or placeholder rates are used where they should not be.
1. Charge reasonableness Check total charges: By consumer. By offering or service. Compare against: Budget or plan. Costing outputs for cost based implementations.

1. Reconciliation with Costing For chargeback scenarios, confirm that: Total Billing charges approximate the Costing view of recoverable cost. Any gap between cost and charges is understood and documented as planned variance.

For Billing Standard, some validations can be done at domain level (for example, cloud, servers, projects) instead of only at the offering level. The same principles apply.
