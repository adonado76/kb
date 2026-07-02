---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Cloud centric design"
breadcrumb:
  - "Billing"
  - "Administration and Operations"
source_path: "boit/billing/admin-ops/ao-cloud-centric.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Cloud centric design

Note: Applies to Billing Standard only.

**When to use it**

- Cloud spend is material and under scrutiny.
- Stakeholders want to see cloud charges by provider, account, service, tag grouping, and
  consumer.

**Shape**

- Cloud data is modeled as its own domain.
- Tags and accounts map to:
  - Services or cost categories.
  - Consumers (business units, products, applications).
- Billing uses cloud domain tables plus unit and price configuration to generate charges and
  unit rates.

**Key elements**

- Ingested cloud billing files into standardized usage tables.
- Tag mapping tables that link tags and accounts to services and consumers.
- Cloud specific unit definitions:
  - GB per month.
  - vCPU hour.
  - Request counts, etc.
- Optional:
  - Separate cloud price logic for chargeback vs cost.

**Typical reports**

- Cloud spend by provider, region, and service.
- Cloud unit rates and trend analysis.
- Cloud spend by tag grouping (for example, application, environment).

**Implementation notes**

- Tagging discipline is non negotiable here. Billing will accurately reflect whatever
  tagging mess exists.
- Use exception reports to highlight untagged or poorly tagged cloud spend.
