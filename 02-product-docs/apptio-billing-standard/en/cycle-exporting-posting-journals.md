---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Exporting and posting journals"
breadcrumb:
  - "Running the Billing Cycle"
  - "Exporting and posting journals"
source_path: "SSV8ML/boit/billing/run-bill-cycle/exporting.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Exporting and posting journals

*For chargeback, Billing outputs often feed Finance systems as journals.*

Typical steps:

1. Prepare journal dataset Use a report or export that contains: Consumer identifiers that match Finance structures. GL segment mappings or accounting codes. Amounts by account, consumer, and period. Any required reference fields such as document type or description.
1. Validate journal totals Confirm that: The sum of journal entries matches total Billing charges. There are no orphan lines with missing codes. Debits and credits balance if both are present in the export.
1. Export in the required format Adjust column order, field naming, and data types to match Finance system requirements. Save in the required format, typically CSV, fixed width text, or an integration friendly layout.
1. Hand off or load to Finance Either: Provide the file to Finance for manual upload. Use an integration process to push journals directly.

1. Confirm posting and trail Verify that: Journals were accepted without errors. The Finance system shows the expected totals by account and consumer. Capture references or document IDs for audit and reconciliation.

Even if the organization is only using showback today, it can be helpful to keep journal ready outputs available so that chargeback can be enabled later without redesigning the Billing model.
