---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Scope and prerequisites"
breadcrumb:
  - "Configuring Billing Essentials (Implementation)"
  - "Scope and prerequisites"
source_path: "SSV8ML/boit/billing/config-be/be-overvie.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Scope and prerequisites

*This section describes how Billing Essentials is configured in a Costing Essentials project, from installing components through to first usable bills. It assumes that Costing Essentials is already deployed and stable.*

Configuration steps in TBM Studio are normally performed by an Admin with Studio access or by a partner / IBM team acting on behalf of the IT organization.

## Scope and prerequisites

Before making any changes, confirm the following:

- The organization is using Billing Essentials (Component Template version 200).
- The Costing Essentials project is live and using In Development, Staging, and Production environments.
- There is a clear plan for: Billable offerings (services/products). Consumers (business units, cost centers, etc.). Consumption sources (how usage will be measured). Rate strategy (how rates are set and maintained).

Minimum technical prerequisites:

- Access to the Costing Essentials project in TBM Studio (for the configuration team).
- Agreement on which environments to use for initial configuration, QA, and go-live.
