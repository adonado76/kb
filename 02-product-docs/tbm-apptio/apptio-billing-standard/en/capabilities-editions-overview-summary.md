---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Editions Overview and Summary"
breadcrumb:
  - "Administration and Operations"
  - "Edition and Capabilities"
  - "Editions Overview and Summary"
source_path: "SSV8ML/boit/billing/edition-capabilities/es-intro.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Editions Overview and Summary

*Billing is available in two editions: Billing Essentials and Billing Standard .*

They solve the same core problem, but with different levels of scope and flexibility.

- A given organization uses one Billing edition at a time , aligned with its Costing project.
- Billing Essentials is delivered through component template version 200 in conjunction with a Costing Essentials implementation.
- Billing Standard is delivered through component templates version 120 and earlier in conjunction with a Costing Standard implementation.

## Edition summary

Billing Essentials

- Focuses on getting a clean, repeatable PxQ billing or showback process in place.
- Appears as a Billing report collection in the same project that runs Costing Essentials.
- Customizing is limited to reports.
- Emphasizes: Simple, understandable bills. Straightforward rate setting and charge calculation. Minimal configuration surface area.

## Billing Standard

- Includes all of the core capabilities of Billing Essentials.
- Adds a broader set of components to support: Domain-specific views (Cloud, Servers, Storage, Applications, Projects, End User Devices). Unit-rate analysis and optimization. Cost vs plan vs price variance analysis. Intercompany and legal-entity reporting.
- Exposed through a separate Billing endpoint , in addition to the Costing Standard project’s endpoint.

Capability comparison The table below summarizes how the editions compare across typical capability areas.

| Capability area | Examples | Billing Essentials | Billing Standard |
| --- | --- | --- | --- |
| Core PxQ rating | Multiply units by rates to calculate charges per period | Yes | Yes (includes Essentials behavior) |
| Basic rate management | Maintain rate tables and mark offerings as billable | Yes | Yes (with additional domain-specific rate views) |
| Bill / invoice generation | Online invoice-style reports, exports, and archives | Yes | Yes (plus additional domain breakdowns) |
| Bill validation & review | Validate charges before release, investigate anomalies | Yes | Yes (with more detailed drill-down by domain) |
| Journal preparation | Export journal-ready data for Finance | Yes | Yes |
| Cloud-specific billing views | Cloud unit rates, provider-level and service-level breakdowns | Limited* | Out of box (Cloud and related components) |
| Application-centric views | Charges by application, application family, or portfolio | Limited* | Out of box (Applications and related reports) |
| Infrastructure domain views | Servers, storage, end-user devices, etc. | Limited* | Out of box (Servers, Storage, End User Devices) |
| Project-centric views | Charges and recovery by project, program, or initiative | Limited* | Out of box (Projects and related views) |
| Unit-rate analysis & optimization | Trends, variance, and driver analysis for unit rates | Limited* | Extended, domain-specific analysis |
| Cost vs plan vs price variance | Compare actual cost, planned cost, and price/recovery | Limited* | Out of box (Cost Variance, Plan Variance, Price) |
| Transfer pricing & legal entities | Intercompany flows, legal-entity view of charges and tax effects | No | Out of box (Inter Company Transfer Pricing, tax data) |
| Scenario / forecast support | Compare different rate, volume, or service assumptions | Limited* | Extended (more structured planning and variance use) |

* Limited out-of-box content. Customizations allowed for reports only.
