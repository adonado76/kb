---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Cloud cost and unit-rate view"
breadcrumb:
  - "Billing"
  - "Design Patterns and Use Cases"
source_path: "boit/billing/design-uc/uc-cloud.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Cloud cost and unit-rate view

Note: **Applies to Billing Standard only.**

**Problem**

You need a repeatable view of cloud cost and charges by provider, account, service, and
consumer, with unit-rate visibility.

**Inputs**

- Cloud provider billing / usage data
- Tag and account mapping tables (to services and consumers)
- Cloud-specific unit definitions
- Rates or price rules for cloud services

**Steps**

1. Confirm **cloud usage data** for the period is loaded and complete.
2. Validate **tag mappings**:
   - Sample a few accounts and ensure tags map to the expected service and consumer.
3. Run the **cloud domain models** in Billing Standard:
   - Aggregate volumes into standard units.
   - Attach cost and price where applicable.
4. Open the **Cloud Billing report**:
   - Filter by provider and period.
   - Review charges by service and consumer.
5. Open the **Cloud unit-rate report**:
   - For each provider-service combination:
   - Units, cost per unit, price per unit.
   - Identify outliers (high or low unit rates).
6. Use filters to drill into:
   - One account or subscription.
   - One tag grouping (for example, application, environment).

**Key reports**

- Cloud Billing by provider/account/service
- Cloud unit rates by provider/service/environment
- Cloud exception report for untagged or poorly tagged usage
