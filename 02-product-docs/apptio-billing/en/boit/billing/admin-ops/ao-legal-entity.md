---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Legal entity and transfer pricing view"
breadcrumb:
  - "Billing"
  - "Administration and Operations"
source_path: "boit/billing/admin-ops/ao-legal-entity.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Legal entity and transfer pricing view

Note: Applies to Billing Standard only.

**When to use it**

- Multiple legal entities consume and provide Technology services.
- Intercompany charging, tax, and regulatory requirements matter.

**Shape**

- Legal entity becomes a key dimension alongside consumer and service.
- Billing separates:
  - Internal revenue lines.
  - Internal expense lines.
  - Possibly tax related surcharges.

**Key elements**

- Legal entity master data with country and tax attributes.
- Mappings:
  - Consumers to legal entities.
  - Services or infrastructure to providing entities.
- Rules in Billing models to:
  - Identify cross entity flows.
  - Create intercompany lines.
  - Tag them with appropriate codes.

**Typical reports**

- Intercompany matrix:
  - Rows as providing entities.
  - Columns as consuming entities.
  - Cells showing charges.
- Legal entity P&L style views for Technology services.
- Audit friendly extracts that reconcile to journals.

**Implementation notes**

- Do not attempt transfer pricing until the basic billing model is stable and
  reconciled.
- Work closely with tax and Finance teams on account structures and documentation.
