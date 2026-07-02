---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Billing admin checklist"
breadcrumb:
  - "Billing"
  - "Running the Billing Cycle"
source_path: "boit/billing/run-bill-cycle/admin-checklist.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Billing admin checklist

This checklist summarizes the recurring tasks for each billing period. It can be adapted
into a more detailed operational runbook.

**Before period close**

- Confirm the billing calendar and cut off dates for the upcoming period.
- Validate that source systems are ready to provide consumption data on time.
- Check that rate tables are up to date for the next period.

**After period close**

- Refresh Costing data for the period.
- Load or refresh consumption feeds that Billing requires.
- Run Billing models in the appropriate environment (Staging first, then Production after
  promotion).

**Validation**

- Run structural, volume, and rate QA reports.
- Reconcile Billing totals to Costing and, if applicable, to plan or budget.
- Resolve any data or configuration issues and rerun models if needed.

**Bill release**

- Generate invoice and detail reports for the period.
- Confirm that reports render correctly and that security is behaving as expected.
- Make reports available to the appropriate audiences and notify them.

**Journals and finance integration**

- Prepare and validate journal exports.
- Deliver or load journals to the Finance system.
- Confirm posting and record any reference IDs.

**Housekeeping**

- Archive Billing outputs for the period.
- Record any known issues, manual adjustments, or one off treatments.
- Update documentation or notes that will be relevant at the next annual planning
  cycle.
