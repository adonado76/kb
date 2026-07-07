---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Running the Billing Standard calculation in In Development / Staging"
breadcrumb:
  - "Configuring Billing Standard (Implementation)"
  - "Running the Billing Standard calculation in In Development / Staging"
source_path: "SSV8ML/boit/billing/config-bs/run-bill.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Running the Billing Standard calculation in In Development / Staging

*Once domain masters, units, prices, and mappings are in place, the Billing Standard calculation can be tested.*

Steps:

1. Run Billing models in In Development Execute the primary Billing Standard models: Services and consumers. Domain-specific models (Cloud, Applications, Infrastructure, Projects). Price and variance models, if configured.
1. Inspect key outputs Check: Core charge tables (services × consumers). Domain views (cloud, servers, storage, devices, applications, projects). Variance tables and unit-rate tables.
1. Publish and test reports in In Development Open representative Billing Standard reports for: Overall charges. At least one domain (for example, Cloud or Applications). Unit-rate and variance views where used.
1. Move to Staging for full QA After initial validation, check in changes. Validate with more complete data in Staging: Re run Billing models. Run QA and exception reports. Validate key stakeholder views (cloud leads, app owners, infra teams, Finance).
