---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Model Objects and Relationships"
breadcrumb:
  - "Concepts and Architecture"
  - "Model Architecture"
  - "Model Objects and Relationships"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/model-architecture/model-object-relationship.html"
images:
  - "03-media/apptio-tbm-studio/full-tbm-flow.png"
  - "03-media/apptio-tbm-studio/labor-cost-flow.png"
  - "03-media/apptio-tbm-studio/infrastructure-flow.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Model Objects and Relationships

## What Is a Model Object?

A model object is the fundamental building block of a Cost model. Think of it as a container that holds cost data at a particular level of your organization’s cost structure.

Every model object is backed by a transform table in Data Studio. The transform table provides the raw data (rows of cost records, vendor information, application details, etc.), and the model object defines how that data participates in the allocation engine. Adding a Model step to a table transform pipeline is what makes it a model object.

Key Concept: Objects as Containers

A model object does not store costs independently. It references a transform table and adds allocation behavior on top. The transform table is the “feed” — the model object is the “role” that data plays in the cost flow.

- Name: A descriptive label (e.g., “Cost Source,” “Vendors,” “Business Units”)
- Data source: The transform table that provides the underlying data
- Metrics: The modeled metrics it participates in (Cost, Budget, Forecast, etc.)
- Drivers: Unit or allocation drivers that feed into the object
- Allocations: Rules that distribute costs to other objects downstream
- Description: Documentation of the object’s purpose and intended use

## Object Types by Role

| Object Role | Description | Example |
| --- | --- | --- |
| Object Role | Description | Example |
| Source Objects | Where costs originate. These sit at the bottom of the model and receive data directly from general ledger, billing, or other financial sources. | Cost Source, GL Actuals |
| Intermediate Objects | Cost allocation waypoints or pathways. Costs pass through these objects on their way to final destinations. They add a layer of categorization or grouping. | Vendors, Labor, IT Towers, Technology Services |
| Target Objects | Final cost destinations. These represent the entities that ultimately “consume” costs for reporting and chargeback purposes. | Business Units, Applications, Solutions |

The same object can be both a target (receiving costs from upstream) and a source (allocating costs downstream). For example, the Vendors object receives costs from Cost Source and then allocates those costs onward to Technology Services. This dual role is what enables multi-tier allocation chains.

## Object Relationships

Model objects are connected through allocations. When you create an allocation from Object A to Object B, you establish a relationship that says: “Some or all of the costs in A should flow to B, distributed according to specific rules.”

- Direction: Costs always flow from source to target — from the “From” object to the “To” object. The model graph must not contain cycles (circular dependencies).
- One-to-many: A single source object can allocate to multiple target objects. For example, Cost Source might allocate simultaneously to Labor, Vendors, and Facilities.
- Many-to-one: Multiple source objects can allocate into the same target. Both Vendors and Labor might allocate costs into Technology Services.
- Navigability: In the Single Object Modeler, clicking a destination object navigates you to that object’s configuration, letting you trace the allocation chain interactively.

## Model Hierarchy

A well-designed model organizes objects into a hierarchy that mirrors your organization’s cost structure. TBM Studio’s allocation engine processes this hierarchy from the bottom up, flowing costs from source objects through intermediate layers to final targets.

Typical Hierarchy Patterns

![TBM Flow](../../../../resources/images/studio_images/full-tbm-flow.png)

![Labor Cost Flow](../../../../resources/images/studio_images/labor-cost-flow.png)

![Infrastructure Cost Flow](../../../../resources/images/studio_images/infrastructure-flow.png)

Best Practice: Hierarchy Design

Keep your hierarchy as shallow as practical. Each additional tier adds complexity and can make cost tracing harder. Most organizations use 3–5 tiers. Start simple and add intermediate layers only when they provide meaningful insight.

Ensure consistent granularity within each object. If one row in your Vendor object represents a single vendor, all rows should represent single vendors — do not mix vendor-level and invoice-level data in the same object.
