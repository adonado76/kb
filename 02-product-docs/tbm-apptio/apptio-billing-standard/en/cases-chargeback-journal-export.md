---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Chargeback with journal export"
breadcrumb:
  - "Design Patterns and Use Cases"
  - "Chargeback with journal export"
source_path: "SSV8ML/boit/billing/design-uc/uc-chargeback.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Chargeback with journal export

Problem

You want Billing outputs to drive internal revenue and expense postings into the general ledger.

Inputs

- All inputs from 15.1 (PxQ showback)
- Mapping from consumers to Finance segments (cost center, company code, etc.)
- Mapping from services to Finance accounts
- Agreed journal format and posting rules with Finance

Steps

1. Validate current period bills using the PxQ recipe (15.1).
1. Ensure mapping tables are complete: Consumers → cost centers / segments Services → GL accounts or account patterns
1. Run Billing models and verify the Billing output / journal table contains: Period, Consumer, Service Units, charges All required Finance segment fields
1. Open the journal export report : Filter to the current period. Confirm totals align with the Billing summary report.
1. Export the journal file in the agreed format (for example, CSV).
1. Provide the file to Finance or load it via integration.
1. Confirm posting: Totals in Finance match the exported totals. No lines failed due to missing or invalid segments.

Key reports

- Invoice / summary report (for comparison)
- Journal export report
- Reconciliation report: Billing total vs journal total
