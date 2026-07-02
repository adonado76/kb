---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Service catalog centric design"
breadcrumb:
  - "Billing"
  - "Administration and Operations"
source_path: "boit/billing/admin-ops/ao-service-catalog.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Service catalog centric design

**When to use it**

- Technology organization has a service catalog or product portfolio that it wants to bill
  against.
- Main conversations are at the service or product level, not per server or
  application.

**Shape**

- Service or product catalog is the primary billing object.
- Domains (infrastructure, cloud, applications) feed cost and volumes into services inside
  Costing.
- Billing focuses on service level units, rates, and charges.

**Key elements**

- Stable service catalog with clear ownership.
- Mapping tables:
  - Infrastructure objects → services.
  - Applications → services.
  - Cloud accounts/tags → services.
- Billing:
  - Consumption at service level.
  - Rates at service level.
  - Optional domain drill backs through reports.

**Typical reports**

- Service centric bill views: one row per service per consumer.
- Service profitability or margin views where price vs cost is relevant.
- Optional domain drill downs (for example, “what makes up the cost of this service”).

**Implementation notes**

- Put the design effort into getting service definitions right. Billing will be much
  easier.
- Treat services as the “language” used with business stakeholders, and use domains to
  support internal analysis.
