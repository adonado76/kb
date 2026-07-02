---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Data requirements for Billing Standard"
breadcrumb:
  - "Billing"
  - "Data Requirements and Integration"
source_path: "boit/billing/datareq-integrate/data-bs.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Data requirements for Billing Standard

Billing Standard uses a wider set of components and, therefore, a broader data model. It
still needs the same basic foundations as Essentials but spreads them across multiple
domains.

Note: Applies to Billing Stnadard only.

Common domain master tables and datasets:

- **Units and unit definitions**
  - Standardized units used across domains (for example, VM per month, GB per month, named
    user per month).
  - Used to keep different domains consistent and comparable.
- **Applications**
  - Application master data:
    - Application ID and name.
    - Owning team or function.
    - Lifecycle status (active, sunset, retired).
  - Relationships to:
    - Services or offerings.
    - Projects and initiatives.
    - Consumers, in app-centric billing designs.
- **Infrastructure**
  - **Servers**: Server ID, type, environment, platform, and ownership.
  - **Storage**: Storage pool, tier, and capacity allocations.
  - **End User Devices**: Device type, owner, location, and allocation rules.

- **Cloud**
  - Cloud account or subscription IDs.
  - Provider and service-level mappings.
  - Tags or labels grouped into:
    - Services or offerings.
    - Consumers.
    - Cost allocation dimensions.
- **Projects**
  - Project ID and name.
  - Type (capital, operating, internal, external).
  - Related applications, services, or products.
  - Mappings between project cost and billing outputs when projects are billed or used as
    consumers.
- **Legal Entities and tax**
  - Legal entity and company codes.
  - Tax and intercompany attributes.
  - Used for transfer pricing and legal-entity-level reporting.
- **Billing-specific master tables**
  - Catalog of billable offerings and price lists, similar to Essentials but aligned with
    the richer domain model.
  - Unit-rate and variance configuration by domain.

Integration patterns for Billing Standard:

- Data sources are broader and often include:
  - CMDB and asset systems.
  - Cloud provider billing files and APIs.
  - PPM tools (for project data).
  - HR or directory systems (for user and ownership mapping).
  - Finance systems for legal entities and tax attributes.
- ETL and integration are:
  - Often implemented with Datalink, integration platforms, or batch processes into TBM
    Studio.
  - Usually governed with stronger data ownership and QA, since there are more domains and
    more stakeholders.

The intent is to model Technology and financial reality once, then reuse those domain masters
across Costing and Billing, rather than maintaining separate, duplicated lists.
