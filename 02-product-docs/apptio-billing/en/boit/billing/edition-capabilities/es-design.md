---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Designing with the edition in mind"
breadcrumb:
  - "Billing"
  - "Administration and Operations"
  - "Edition and Capabilities"
source_path: "boit/billing/edition-capabilities/es-design.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Designing with the edition in mind

When working with Billing Essentials:

- **Keep the catalog disciplined**
  - Focus on a set of offerings that can be clearly described and understood by
    non-technical stakeholders.
  - Avoid unnecessary fragmentation of services that would confuse bills.
- **Anchor on clear units and rates**
  - Use units that can be measured consistently and traced back to consumption data.
  - Keep rate tables simple enough that Admins and Analysts can explain them without
    referring to model diagrams.
- **Use Billing Essentials reports as the primary billing view**
  - Treat the out-of-box invoice, detail, and archive reports as the main reference for
    monthly discussions.
  - Align any external summaries (for example, PowerPoint or spreadsheet summaries) with
    those reports.
- **Push deep technical analysis back to Costing**
  - If a question is about cost structure or allocation logic (for example, how
    infrastructure costs roll into a service), answer it using Costing models and
    reports.
  - Use Billing Essentials to answer “who is being charged what and why” at the service or
    product level.

When working with Billing Standard:

- **Leverage the domain components as intended**
  - Use the components (Cloud, Projects, Applications, Servers, Storage, End User Devices,
    etc.) instead of re-creating similar logic in custom models.
  - Align master data and keys with those domains so the out-of-box reports can be used as
    designed.
- **Plan which domains to expose**
  - Decide early which domains will be visible to which audiences (for example, unit rates
    and variances by cloud provider vs by internal service).
  - Use that decision to drive which master tables must be populated and governed.
- **Structure conversations around domain views**
  - Use domain reports to support different types of discussions:
    - Infrastructure and operations: servers, storage, devices.
    - Product and application owners: applications, projects.
    - Finance and leadership: variance, transfer pricing, and legal-entity views.
- **Be explicit about which capabilities are “Phase 1” vs later**
  - It is common to start with invoice-style and unit-rate views, then layer in more
    advanced areas like transfer pricing and variance analysis.
  - Document which components are actively used and which are staged for future use so the
    model remains understandable.

Across both editions, the principle is the same: design Billing so that charges are
transparent, traceable, and defensible.
