---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Dress rehearsal"
breadcrumb:
  - "Go-Live Playbook"
  - "Dress rehearsal"
source_path: "SSV8ML/boit/billing/go-live/gl-dress-rehersal.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Dress rehearsal

*A dress rehearsal is a full end-to-end run in Development and verified in Staging that mimics what you will be published into Production.*

## Scope of the dress rehearsal

At minimum, the rehearsal should include:

- Data refresh for the selected period (or a realistic test period) in Development.
- Full Costing runs that feed Billing in Development.
- Full Billing runs for in Development: Core PxQ calculation. Any domain-specific models in scope (for example, cloud, projects, applications).
- Report validation in Development: Invoice/summary views. Detail/drill-down views. Journals and exports.
- QA checks in Staging: Structural, volume, and rate checks. Reconciliation to Costing where applicable.

If any of those fail, you are not ready for Production go-live.

## Documenting QA results

Record, at least:

- Which Staging build ID was used.
- Which datasets were loaded and which dates they cover.
- Any anomalies discovered and how they were addressed.
- Sign-offs from: Admin/Analyst (technical validity). Finance (if chargeback/journals are in scope). One or two key Service or Product Owners.

This becomes your reference when someone later asks, “What changed at go-live?”
