---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Configuring and loading rates"
breadcrumb:
  - "Billing"
  - "Configuring Billing Essentials (Implementation)"
source_path: "boit/billing/config-be/configure.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Configuring and loading rates

Rates translate units into monetary charges.

Steps:

1. **Define rate strategy**
   - For each offering, determine whether the rate will be:
     - Cost-based, cost-plus, price-based, budget-based, or hybrid.
   - Decide how often rates can change:
     - Annually, quarterly, or ad hoc with governance.
2. **Design the rate table layout**
   - At minimum:
     - Offering ID.
     - Period or effective date.
     - Rate amount.
     - Currency.
   - Optional:
     - Rate type (standard, discounted, internal).
     - Notes or comments.
3. **Load initial rates**
   - Populate rates for:
     - The first billing period.
     - A defined future horizon (for example, the full fiscal year).
4. **Validate resolution**
   - Run a test report or model run to confirm:
     - Every billed offering in the period resolves to a single, unambiguous rate.
     - No offerings are missing rates.

Governance tip:

- Treat rate changes as controlled events, with clear documentation and approval, especially
  mid-year.
