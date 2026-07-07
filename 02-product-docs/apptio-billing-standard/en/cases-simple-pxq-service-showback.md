---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Simple PxQ service showback"
breadcrumb:
  - "Design Patterns and Use Cases"
  - "Simple PxQ service showback"
source_path: "SSV8ML/boit/billing/design-uc/uc-simple.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Simple PxQ service showback

Problem

You want a transparent monthly view that answers:

“Who is using which services, how much are they using, and what is the calculated charge?”

Inputs

- Service / offering catalog with units and billable flags
- Consumer master
- Monthly consumption data (units by service and consumer)
- Rates by service and period

Steps

1. Confirm the offering catalog is up to date and billable flags are set correctly.
1. Load or refresh consumption data for the current period.
1. Load or confirm rates for each active offering for the period.
1. Run the Billing models in the appropriate environment (In Development/Staging for testing, Production for live).
1. Open the invoice / summary report for the period.
1. Filter by consumer as needed and confirm: Services listed match expectations. Units and rates look correct. Total charges are reasonable.

Key reports

- Invoice / summary report
- Consumer summary report
- QA / exception report for missing mappings
