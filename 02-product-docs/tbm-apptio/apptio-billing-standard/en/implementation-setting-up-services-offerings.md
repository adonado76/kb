---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Setting up services and offerings"
breadcrumb:
  - "Configuring Billing Standard (Implementation)"
  - "Setting up services and offerings"
source_path: "SSV8ML/boit/billing/config-bs/bs-setup.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Setting up services and offerings

*The catalog of what is billed is central regardless of edition, but Billing Standard often needs richer linkage to domains.*

Steps:

1. Review existing service/product catalog Reuse what is already defined in Costing where possible. Confirm: Names are meaningful to business stakeholders. Each service/product can be mapped to underlying domain objects (apps, cloud, servers, etc.) where needed.
1. Populate or update the services table For each service or product: Assign a stable Service/Offering ID. Set a clear name and description. Define unit of measure. Set status (active/retired) and billable flags.
1. Link services to domains Depending on design: Map services to applications (for app-centric views). Map services to server or storage pools. Map services to cloud account/tag groupings. Map services to projects or portfolios, if relevant.

Design suggestions:

- Avoid one service per tiny technical component. Group technical building blocks into services that make business sense.
- Use domain links to enrich analysis, not to overcomplicate the catalog.
