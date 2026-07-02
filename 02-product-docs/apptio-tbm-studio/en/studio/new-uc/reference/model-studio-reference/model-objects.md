---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Model Objects"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Model Studio Reference"
source_path: "studio/new-uc/reference/model-studio-reference/model-objects.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Model Objects

Model objects are the fundamental building blocks of a TBM Studio cost model. Each model object
represents a distinct layer or entity in your organization’s cost structure, such as cost sources,
vendors, applications, or business units.

## Model Object Types and Their Purposes

TBM Studio supports a unified model object type that can serve different purposes based on its
position in the model hierarchy and configuration.

**Model Object**

**Description:** A model object is created by adding a Model step to a table’s transform
pipeline. This converts the table into a modeled entity that can participate in allocations, receive
drivers, and flow metrics through the cost model.

**Purpose:** Model objects group data for analysis and define allocation relationships. They
can serve as source objects (providing value), target objects (receiving value), or both.

**Common Model Object Roles**

|  |  |  |
| --- | --- | --- |
| **Role** | **Description** | **Examples** |
| Cost Source | Entry point for financial data. Typically contains GL or invoice data with unit drivers. | Cost Source Actuals, General Ledger, Fixed Asset Ledger |
| Cost Pool | Intermediate grouping layer. Receives allocations from cost sources and allocates to infrastructure or services. | Labor, Facilities, Fixed Assets, Software Licenses |
| Infrastructure | Technology resource layer. Represents physical or virtual assets. | Servers, Storage, Network, Data Centers |
| Service | IT service layer. Represents services consumed by business. | Technology Services, Applications, Solutions |
| Consumer | Final destination for cost allocation. Represents business consumers. | Business Units, Departments, Projects, Customers |

*→ See [TBM
Framework Layers for conceptual overview](../../concepts-architecture/model-architecture/model-concepts-overview.html)*

*→ See [Create a model object for step-by-step instructions](../../howtoguides/build-cost-model/create-model-rep.html)*

- **[Model Object Properties](../../../../studio/new-uc/reference/model-studio-reference/model-objects-properties.html)**
- **[Object Relationships and Dependencies](../../../../studio/new-uc/reference/model-studio-reference/objects-relationships.html)**
- **[Object Naming Conventions](../../../../studio/new-uc/reference/model-studio-reference/object-naming-convention.html)**
