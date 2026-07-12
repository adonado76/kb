---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Project-centric billing and views"
breadcrumb:
  - "Advanced Topics"
  - "Project-centric billing and views"
source_path: "SSV8ML/boit/billing/advance-topic/project-centric-billin.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Project-centric billing and views

*Projects often represent investments in products, services, or change initiatives. Billing Standard project components enable project-centric billing and showback.*

## Project as consumer vs project as dimension

Two common patterns:

- Project as consumer The project is billed for services it consumes (for example, platforms, environments, shared tools). Useful for tracking project usage of shared infrastructure or platforms.
- Project as dimension Charges to business units are tagged with project attributes. Useful for understanding how much a business unit spends on specific initiatives.

Design choices:

- Decide whether projects will: Directly receive charges. Tag underlying labor or service consumption only.
- Ensure project IDs and names are stable and consistent across systems (PPM, HR, Finance).

## Data needed for project views

Minimum requirements:

- Project master: Project ID, name, owner, type, and lifecycle status.
- Project-to-service mappings: Link projects to services, applications, or platforms used.
- Labor and other cost drivers: Time, cost, or points per project where projects drive allocation.

With these in place, Billing Standard can:

- Show charges by project and consumer.
- Show project-specific unit rates for shared services.
- Support reporting such as “top 10 projects by Technology consumption.”
