---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Core domain tables and relationships"
breadcrumb:
  - "Billing"
  - "Configuring Billing Standard (Implementation)"
source_path: "boit/billing/config-bs/bs-core.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Core domain tables and relationships

Billing Standard’s strength comes from its domain-rich model. At minimum, expect to work
with the following table families:

- **Services / offerings catalog**
  - ID, name, unit of measure, lifecycle status, billable flag.
- **Consumers**
  - Shared with Costing or aligned to it.
  - Consumer ID, name, hierarchy, and attributes such as region, function, or
    manager.
- **Units and unit definitions**
  - Standard units (for example, VM per month, GB per month, named user per month, ticket
    per month).
  - Mappings from domain-specific measures into standard units.
- **Applications**
  - Application ID, name, owner, lifecycle status.
  - Links to services/offers and possibly to projects and consumers.
- **Servers and storage**
  - Servers: ID, type, environment, platform, ownership, capacity.
  - Storage: pool, tier, capacity, allocation or mapping to consumers/services.
- **End user devices**
  - Device ID or group, device type, owner, location, allocation rules.
- **Cloud**
  - Provider, account/subscription ID, service type.
  - Tag mappings to services, consumers, and domains.
- **Projects**
  - Project ID and name, type (CapEx/OpEx/other), owner, linked services or apps.
- **Legal entities / transfer pricing** (if in scope)
  - Legal entity ID, name, country, tax attributes, intercompany pairing
    relationships.
- **Price and variance tables**
  - Price lists, cost vs plan vs price configuration, variance buckets.

These tables are designed to work together. Avoid creating isolated custom tables that
duplicate their purpose unless there is a clear reason.
