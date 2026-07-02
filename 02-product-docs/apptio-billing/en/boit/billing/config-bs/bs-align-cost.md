---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Aligning cost, consumption, and unit definitions"
breadcrumb:
  - "Billing"
  - "Configuring Billing Standard (Implementation)"
source_path: "boit/billing/config-bs/bs-align-cost.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Aligning cost, consumption, and unit definitions

Billing Standard needs a coherent story across cost, units, and prices.

Steps:

1. **Review Costing allocation outputs**
   - Confirm that cost flows:
     - From resource towers and domains to services/applications.
     - From services/applications to consumers.
2. **Define standard units**
   - For each domain, map raw measures into standardized units, for example:
     - VM hours → VM per month.
     - Raw GB/hours → GB per month.
     - Tickets → Tickets per month.
     - Populate the units table accordingly.
3. **Tie domain volumes to services and consumers**
   - Ensure domain tables (servers, storage, cloud, devices, projects) feed into:
     - Service-level volumes.
     - Consumer-level volumes.
4. **Tie Costing outputs to Billing units where needed**
   - For unit-rate analysis:
     - Combine cost from Costing with volumes from Billing to get cost per unit.
   - Use this to:
     - Validate prices.
     - Explain changes in unit rates.
