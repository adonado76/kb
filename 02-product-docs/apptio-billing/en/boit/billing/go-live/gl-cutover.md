---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Cutover approach"
breadcrumb:
  - "Billing"
  - "Go-Live Playbook"
source_path: "boit/billing/go-live/gl-cutover.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Cutover approach

Cutover is the controlled move from “we are testing” to “we are using Billing as the
source of truth.”

## Common cutover decisions

Decide and document:

- First **official Billing period** in Production.
- Whether you are:
  - Starting Billing brand new, or
  - Replacing a prior manual or legacy process mid-year.
- Whether you will:
  - Republish prior periods for history, or
  - Start fresh from the go-live period onward.

## Essentials-specific notes

Note: **Applies to Billing Essentials only.**

For Billing Essentials:

- Cutover is tied directly to the Costing Essentials project promotion.
- When you promote the Staging build to Production:
  - You are promoting both Costing and Billing Essentials content together.
- Go-live actions usually include:
  - Promoting the validated build to Production.
  - Running Billing Essentials models in Production for the first official period.
  - Making the **Billing report collection** visible to target audiences.

## Standard-specific notes

Notice: Applies to Billing Standard only.

For Billing Standard:

- Cutover involves both:
  - Promoting the Costing Standard project build that contains Billing Standard
    configuration.
  - Enabling and exposing the **Billing endpoint** with the correct report
    collections.

Typical steps:

1. Lock Staging and promote the tested build to Production.
2. Confirm that the **Billing endpoint** displays the agreed report collections
   (services, cloud, applications, projects, variance, journals, etc.).
3. Have one or two pilot users (for example, a Service Owner and a Finance representative)
   log into the Billing endpoint and confirm:
   - Navigation works.
   - Filters and drill-downs behave as expected.
