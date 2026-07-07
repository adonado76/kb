---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Chargeback with journals"
breadcrumb:
  - "Administration and Operations"
  - "Chargeback with journals"
source_path: "SSV8ML/boit/billing/admin-ops/ao-chargeback-journal.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Chargeback with journals

When to use it

- Finance wants to treat Billing outputs as internal revenue and expense.
- Chargeback entries are posted into the general ledger.

Shape

- Same basic structure as showback, plus a stable mapping into GL or Finance segments.
- Stronger monthly QA around journal totals and posting.

Key elements

- Billing output table extended with: GL account fields. Cost center and other Finance segments. Any document type or reference fields required by Finance.
- Journal reports tuned to Finance format.

Typical reports

- Invoice reports for conversations with consumers.
- Journal export report with account level detail.
- Reconciliation report: Billing total vs journal total vs Costing recoverable cost.

Implementation notes

- Align consumer and segment structures with Finance from day one.
- Treat rate changes and mapping changes as governed events, with change history.
