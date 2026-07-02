---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Access patterns for Billing Standard"
breadcrumb:
  - "Billing"
  - "Getting started"
  - "User Roles and Permissions"
source_path: "boit/billing/getting-started/access-patterns-bs.html"
images:
  - "resources/images/boit_images/apbs.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Access patterns for Billing Standard

Billing Standard introduces a separate Billing endpoint in addition to the Costing
project. Access needs to account for both.

Note: Applies to Billing Standard only.

**Typical patterns:**

- **Admins and Analysts**
  - Have front-end access to the Billing Standard endpoint and relevant report
    collections.
  - Have TBM Studio access to the Costing Standard project where the “BoIT” components are
    installed.
  - Coordinate with security teams to ensure that the right users see the right Billing
    reports and domains.
- **Service or Product Owners, Senior Leaders, Stakeholders, and Consumers**
  - Access Billing Standard through the dedicated endpoint in the front-end.
  - See only the report collections and views relevant to their responsibilities and
    scope.
  - May have finer-grained access control for sensitive areas like transfer pricing or
    legal entity reporting.

## Key points:

- Access to Billing Standard reports and dashboards is controlled at the endpoint level
  and within the report collections.
- TBM Studio access remains focused on configuration roles; most business roles stay in
  the front-end only.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/apbs.png)

Fig #: Frontdoor landing page with Billing Standard endpoint highlighted
