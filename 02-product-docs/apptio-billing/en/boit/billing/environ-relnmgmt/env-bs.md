---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Environment flow for Billing Standard"
breadcrumb:
  - "Billing"
  - "Administration and Operations"
  - "Environments and Release Management"
source_path: "boit/billing/environ-relnmgmt/env-bs.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Environment flow for Billing Standard

Billing Standard follows the same environment lifecycle as the underlying Costing
Standard project, but introduces a separate Billing endpoint for end users.

Note: Applies to Billing Standard only.

Implications:

- Billing Standard components are installed and changed in the **Costing Standard**
  project’s In Development environment.
- When Billing Standard-related items are checked in:
  - A new In Development build is created for the Costing Standard project.
  - A corresponding Staging build is automatically created.

Staging is then used to validate:

- Billing Standard models and processes (for example, unit-rate calculations, variance
  logic).
- Domain-specific Billing reports (Cloud, Applications, Projects, Infrastructure, Transfer
  Pricing).
- End-to-end Billing scenarios:
  - Charges by consumer and domain.
  - Unit-rate and variance views.
  - Journals and any downstream exports.

Promotion behavior:

- When the Staging build is promoted to Production:
  - The **Costing Standard** Production environment is updated.
  - The **Billing Standard endpoint** reflects the new Billing logic and reports,
    because it is backed by the same project content.

Operational recommendations:

- Treat Billing Standard releases as coordinated events:
  - Confirm the Costing Standard model changes and Billing Standard changes in the same
    build.
  - Communicate to stakeholders which Billing domains (for example, Cloud, Projects,
    Transfer Pricing) are affected in each release.
- Use Staging as the primary place to test both:
  - Technology-focused views (unit rates, domain breakdowns).
  - Business-focused views (bills, journals, variance reports).
