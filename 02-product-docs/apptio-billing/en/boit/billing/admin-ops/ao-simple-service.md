---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Simple service showback"
breadcrumb:
  - "Billing"
  - "Administration and Operations"
source_path: "boit/billing/admin-ops/ao-simple-service.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Simple service showback

**When to use it**

- First Billing deployment where the priority is transparency, not internal revenue.
- Stakeholders want to see “who consumes what” and “how much it would cost” without posting
  journals.

**Shape**

- A disciplined, relatively small catalog of services or products.
- Units and rates maintained in a small number of tables.
- Consumption feeds mapped directly to services and consumers.
- Journals available, but not used for posting.

**Key elements**

- Offerings table: clear service names and units.
- Consumption table: consumer × service × period × units.
- Rate table: one rate per service per period.
- Billing outputs: used for invoices and summary views only.

**Typical reports**

- Invoice style summary by consumer and service.
- Trend views showing charges over time.
- QA reports for missing mappings and outliers.

**Implementation notes**

- Keep units and rates simple and explainable.
- Do not over engineer domain modeling for a pure showback pattern; focus on clarity.
