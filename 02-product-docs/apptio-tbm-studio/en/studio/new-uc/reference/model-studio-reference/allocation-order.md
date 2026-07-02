---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Allocation Order and Precedence"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Model Studio Reference"
  - "Allocations"
source_path: "studio/new-uc/reference/model-studio-reference/allocation-order.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Allocation Order and Precedence

Allocations are executed in a deterministic order based on the model graph structure.

**Execution Rules**

- Allocations execute from lowest tier to highest tier (bottom-up)
- Within a tier, allocations execute in creation order
- Unit drivers execute before allocations for each object
- All inputs to an object must complete before its outputs execute Recursive allocations execute
  after standard allocations

**Parent topic:** [Allocations](../../../../studio/new-uc/reference/model-studio-reference/allocations.html)
