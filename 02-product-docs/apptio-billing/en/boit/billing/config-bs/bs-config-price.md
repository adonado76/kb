---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Configuring price and variance logic"
breadcrumb:
  - "Billing"
  - "Configuring Billing Standard (Implementation)"
source_path: "boit/billing/config-bs/bs-config-price.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Configuring price and variance logic

Billing Standard can analyze cost, plan, and price. The configuration decides how that
works.

Steps:

1. **Define price lists**
   - Decide whether pricing is:
     - Single rate per service.
     - Tiered by consumer, region, or volume.
   - Populate price tables with:
     - Service/Offering ID.
     - Period or effective dates.
     - Price per unit.
     - Currency and rate type.
2. **Connect plan and budget data**
   - If variance is in scope:
     - Integrate planned cost and/or planned volumes from planning systems or
       spreadsheets.
   - Align plan data keys to the same services and consumers used in Billing.
3. **Configure variance rules**
   - Decide which variance types are tracked:
     - Volume variance.
     - Rate variance (cost vs price).
     - Mix or structural variance where appropriate.
   - Configure which variances appear in:
     - Domain reports (for example, cloud, applications).
     - Summary variance reports.
4. **Test variance results**
   - Run small test cases:
     - Known cost, plan, and price scenarios.
     - Confirm that the variance decomposition matches expectations.
