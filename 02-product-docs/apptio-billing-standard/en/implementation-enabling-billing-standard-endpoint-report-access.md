---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Enabling the Billing Standard endpoint and report access"
breadcrumb:
  - "Configuring Billing Standard (Implementation)"
  - "Enabling the Billing Standard endpoint and report access"
source_path: "SSV8ML/boit/billing/config-bs/enable-bill.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Enabling the Billing Standard endpoint and report access

*With content validated in Staging, the endpoint and reports can be prepared for users.*

Steps:

1. Confirm Billing Standard endpoint linkage Ensure the endpoint points to the correct Costing Standard project and environments.
1. Promote required reports into the endpoint Decide which report collections are in scope for go-live: Services & consumers. Cloud. Applications. Infrastructure. Projects. Variance / pricing. Journals. Publish and categorize them appropriately.
1. Configure report access Align report access with roles: Admins and Analysts: broad access. Service or Product Owners: views relevant to their domains. Finance: unit-rate, variance, and journal reports.
1. Smoke-test the endpoint Log in as a typical user profile. Confirm: Reports open and respond. Filters and drill-downs work.

Security behaves as expected.
