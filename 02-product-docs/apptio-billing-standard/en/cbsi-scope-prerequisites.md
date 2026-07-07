---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Scope and prerequisites"
breadcrumb:
  - "Configuring Billing Standard (Implementation)"
  - "Scope and prerequisites"
source_path: "SSV8ML/boit/billing/config-bs/bs-overview.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Scope and prerequisites

*This section describes how Billing Standard is configured on top of a Costing Standard project, from installing components through to first usable domain-rich bills. It assumes that Costing Standard is already deployed and stable.*

Configuration in TBM Studio is normally done by an Admin or equivalent role with Studio access.

## Scope and prerequisites

Before making changes, confirm:

- The organization is using Billing Standard (Component Template version 120 or earlier).
- A Costing Standard project exists with: In Development, Staging, and Production environments. A working cost model that already supports Technology towers, applications, services, and consumers.
- There is a clear design for: Billable offerings (services/products). Consumers (BUs, cost centers, projects, products, etc.). Domain modeling: Applications Servers and storage Cloud accounts and services End user devices Projects Legal entities, if transfer pricing is in scope Rate strategy and variance approach (cost vs plan vs price).

Technical prerequisites:

- TBM Studio access to the Costing Standard project.
- Agreement on which domains will be actively used at go-live versus phased in later.
