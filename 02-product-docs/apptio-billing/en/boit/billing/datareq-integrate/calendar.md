---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Calendars and periods"
breadcrumb:
  - "Billing"
  - "Data Requirements and Integration"
source_path: "boit/billing/datareq-integrate/calendar.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Calendars and periods

Billing needs a consistent notion of **periods**:

- Most implementations are **monthly**, sometimes aligned to a fiscal calendar.
- Each record in consumption and rate tables must reference:
  - A period identifier (for example, YYYY-MM).
  - Possibly a fiscal period key if the organization’s fiscal calendar differs from
    calendar months.

Design considerations:

- Decide whether Billing aligns strictly with the **fiscal calendar**, the **calendar
  month**, or a hybrid approach.
- When partial periods or cutover events occur (for example, mid-month go-live), document
  how those are treated:
  - Split periods.
  - One-time adjustments.
  - Pro-rated rates or units.

If Costing already uses a fiscal calendar, reuse the same structure in Billing to avoid
unnecessary reconciliation work.
