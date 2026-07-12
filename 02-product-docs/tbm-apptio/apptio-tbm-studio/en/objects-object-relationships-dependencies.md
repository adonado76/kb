---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Object Relationships and Dependencies"
breadcrumb:
  - "Reference"
  - "Model Studio Reference"
  - "Model Objects"
  - "Object Relationships and Dependencies"
source_path: "SSWRJM/studio/new-uc/reference/model-studio-reference/objects-relationships.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Object Relationships and Dependencies

Model objects are connected through allocations and drivers. Understanding these relationships is critical for building accurate cost models.

Relationship Types

| Relationship | Direction | Description |
| --- | --- | --- |
| Relationship | Direction | Description |
| Driver | Into object | Unit driver brings value into the model object from a column |
| Allocation (Outbound) | Out of object | Sends value from this object to target objects |
| Allocation (Inbound) | Into object | Receives value from source objects |

Dependency Rules

- Model graph must not contain cycles (no circular allocations)
- All model objects must have valid data for the active time period
- Source and target tables must be checked out before creating allocations
- Allocations execute in deterministic order based on the object graph
- Transform errors block model calculations for affected objects

→ See Model Execution Order for calculation sequence details

→ See Circular allocation errors for troubleshooting
