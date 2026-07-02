---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Handover and operationalization"
breadcrumb:
  - "Billing"
  - "Configuring Billing Essentials (Implementation)"
source_path: "boit/billing/config-be/handover.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Handover and operationalization

After the first successful Production run:

- Document the **recurring billing process** based on Section 9:
  - Data refresh steps.
  - Model run sequence.
  - QA and approval checkpoints.
- Clarify **roles**:
  - Who maintains offerings and rates.
  - Who owns consumption feeds.
  - Who runs models and QA.
  - Who approves bills and journals.
- Set up **routine QA reports** and **dashboards**:
  - Exceptions (missing mappings, odd volumes).
  - Trend comparisons against prior periods.

The goal is to shift Billing Essentials from a one-time project to a predictable monthly
process, with configuration changes handled through the same environment lifecycle as Costing
Essentials.
