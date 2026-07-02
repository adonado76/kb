---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Capturing the “steady-state” runbook"
breadcrumb:
  - "Billing"
  - "Go-Live Playbook"
source_path: "boit/billing/go-live/runbook.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Capturing the “steady-state” runbook

Once you have:

- Completed at least one cycle in Production, and
- Fixed the major issues revealed in hypercare,

then lock in the steady-state runbook:

- Document:
  - Monthly timeline and key dates.
  - Data loads and model runs sequence.
  - Standard QA checks and thresholds.
  - Who does what, when.
- Link that runbook back to:
  - The billing cycle description (Section 9).
  - Environment usage (Section 7).
  - Configuration references (Sections 11 and 12).

That runbook becomes the anchor: new team members learn it, audits reference it, and any
future enhancements to Billing should respect it instead of reinventing the entire
process.
