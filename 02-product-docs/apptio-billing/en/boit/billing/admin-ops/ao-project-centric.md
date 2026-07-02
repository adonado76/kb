---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Project centric design"
breadcrumb:
  - "Billing"
  - "Administration and Operations"
source_path: "boit/billing/admin-ops/ao-project-centric.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Project centric design

Note: Applies to Billing Standard only.

**When to use it**

- Project and initiative spend need to be visible in billing terms.
- Leaders want to see which projects drive Technology consumption and charges.

**Shape**

Two common variants:

1. **Project as a billed consumer**
   - Projects receive charges like any other consumer.
   - Useful when Technology costs need to be capitalized or allocated to projects
     directly.
2. **Project as a reporting lens**
   - Charges still go to business units or products.
   - Project attributes tag the charges to support portfolio analysis.

**Key elements**

- Project master data aligned with PPM and Finance.
- Mapping:
  - Labor, infrastructure, and cloud usage to projects.
  - Projects to services or applications if relevant.
- Billing reports that can pivot by project, service, and consumer.

**Typical reports**

- Charges by project and service.
- Project view of shared platforms or services consumed.
- Portfolio views:
  - Top projects by Technology spend.
  - Project spend by sponsor or portfolio.

**Implementation notes**

- Be clear on whether projects are true billing targets or just tags. Mixing the two without
  clarity creates confusion.
- Keep project IDs stable across systems and years where possible.
