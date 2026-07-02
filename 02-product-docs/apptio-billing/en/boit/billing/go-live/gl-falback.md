---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Fall-back and correction strategies"
breadcrumb:
  - "Billing"
  - "Go-Live Playbook"
source_path: "boit/billing/go-live/gl-falback.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Fall-back and correction strategies

Things will occasionally go wrong. Decide up front how you will correct
them.

## Within-period corrections

Use when an issue is caught before bills are formally released or journals posted.

Typical actions:

- Fix data (for example, consumption, mapping, rates).
- Re run the relevant Billing models in Staging and Production.
- Revalidate core reports and QA views.
- Reexport journals if applicable.

Try to avoid repeated partial reruns for the same period; group fixes where possible.

## Post-release corrections

Use when an issue is discovered after bills are shared or journals posted.

Options:

- **Billing only** (showback):
  - Correct the model and data for the next period.
  - Document the correction and, if needed, apply a one-off adjustment in the next
    period’s bill.
- **Chargeback** (journals):
  - If the error is material, prepare correction journals in coordination with
    Finance.
  - Use Billing to calculate the deltas:
    - What was billed.
    - What should have been billed.
    - Difference by consumer and account.

In both cases, ensure the root cause is addressed so the same issue does not repeat each
month.
