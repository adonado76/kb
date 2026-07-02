---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Promoting to Production and first full Billing Standard run"
breadcrumb:
  - "Billing"
  - "Configuring Billing Standard (Implementation)"
source_path: "boit/billing/config-bs/promote-bill.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Promoting to Production and first full Billing Standard run

After Billing Standard content and endpoint behavior are validated in
Staging:

1. **Lock Staging**
   - Prevent new check-ins and keep the tested build stable.
2. **Run final QA in Staging**
   - Confirm:
     - All major services and consumers have charges.
     - Domain reports populate as expected.
     - Variance and unit-rate outputs look reasonable.
3. **Promote the build to Production**
   - Promote the validated Staging build for the Costing Standard project.
   - This effectively updates the Billing Standard endpoint content as well.
4. **Run Billing Standard models in Production**
   - Execute Billing models for the target period in Production.
   - Validate:
     - Core and domain outputs.
     - Key reports for the period.
5. **Open the Billing Standard endpoint to target audiences**
   - Confirm that:
     - Intended users can see the endpoint.
     - Reports render correctly.

Security filters behave as expected.
