---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Currencies and FX"
breadcrumb:
  - "Data Requirements and Integration"
  - "Currencies and FX"
source_path: "SSV8ML/boit/billing/datareq-integrate/currency.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Currencies and FX

*Billing can operate in multi-currency environments, but it is usually simpler if Billing outputs are presented in a single presentation currency for business stakeholders.*

Key points:

- Source currencies Costing may receive costs in multiple currencies and convert them using FX rates. Consumption volumes are usually currency-neutral.
- Presentation currency Decide which currency bills and journals should be presented in (for example, USD). Ensure that FX rates used in Costing are applied consistently so that Billing charges reconcile.
- Cross-entity billing For cross-country or multi-entity scenarios, confirm: Which currency rates are used for internal billing vs external reporting. Whether Billing needs to reflect FX separately or only the converted outcome.

Document the currency setup early and keep it stable. Changing FX logic mid-year can create confusion unless clearly communicated and traceable.
