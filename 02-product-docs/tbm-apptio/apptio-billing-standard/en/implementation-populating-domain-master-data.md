---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Populating domain master data"
breadcrumb:
  - "Configuring Billing Standard (Implementation)"
  - "Populating domain master data"
source_path: "SSV8ML/boit/billing/config-bs/bs-pop-domain.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Populating domain master data

*Domain masters enable the Billing Standard reports that slice charges by application, infrastructure, cloud, project, and legal entity.*

## Applications

- Load or align application master data: Application ID, name, owner, lifecycle status, criticality.
- Map applications to: Services or offerings. Consumers (if applications are treated as consumers). Projects, if project work is app-centric.

Fig #: Applications Master Data table viewed from TBM Studio

## Servers, storage, and end user devices

- Servers Ensure each server (or server group) has ID, type, environment, platform, owner, and mapping to services or consumers.
- Storage Maintain storage pools or tiers, capacity, and mappings to consumers or services.
- End user devices Maintain device type (laptop, desktop, VDI, etc.), user or group, and allocation rules.

Fig #: Servers Master Data table viewed from TBM Studio

## Cloud

- Standard pattern: Load provider billing data into a consolidated cloud usage table. Maintain a tag or account mapping table that links: Provider and account ID. Tags (for example, app, owner, cost center). Resulting Service and Consumer IDs.

Fig #: Cloud Service Provider Master Data table viewed from TBM Studio

## Projects

- Populate project master data with: Project ID, name, type, owner. Link to services, products, or applications. Identify which projects, if any, are treated as billable consumers.

Legal entities and intercompany

- If transfer pricing is in scope: Maintain a table of legal entities with tax and regulatory attributes. Map consumers, services, and infrastructure to legal entities. Configure intercompany pairing logic (from-entity to-entity).
