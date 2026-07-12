---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Allocation Order and Processing"
breadcrumb:
  - "Concepts and Architecture"
  - "Model Architecture"
  - "Allocation Order and Processing"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/model-architecture/allocation-order.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Allocation Order and Processing

## Why Order Matters

In a multi-tier cost model, allocations do not all execute simultaneously. The order in which allocations are processed determines the final results, because downstream allocations depend on the output of upstream ones.

Consider a simple chain: Cost Source allocates to Vendors, and Vendors allocates to Business Units. The Vendors allocation must complete before Business Units can receive its share — otherwise, there would be no costs i to distribute from Vendors.

## Dependency-Based Sequencing

TBM Studio determines allocation order automatically based on the model’s dependency graph. The system analyzes which objects feed into which other objects and establishes a processing sequence that respects these dependencies.

The rules are:

- An object’s allocations execute only after all incoming allocations to that object have completed
- Objects with no upstream dependencies (source objects) are processed first
- Objects at the same level with no dependencies on each other can be processed in parallel
- The processing sequence is deterministic — the same model always produces the same execution order

## Multi-Tier Allocations

In most real-world models, costs flow through multiple intermediate layers before reaching their final destination. This is called a multi-tier or multi-hop allocation.

How Multi-Tier Flows Work

| Tier | Object | What Happens | Result |
| --- | --- | --- | --- |
| Tier | Object | What Happens | Result |
| 1 | Cost Source | $1,000 enters from the GL as a datacenter expense | $1,000 source value |
| 2 | Vendors | Matched to Dell based on Vendor ID; $1,000 flows to Dell | Dell receives $1,000 |
| 3 | Tech Services | Allocated to Compute (70%) and Storage (30%) based on usage | Compute: $700, Storage: $300 |
| 4 | Solutions | Compute’s $700 splits across ERP ($400) and CRM ($300) by transaction volume | ERP: $400, CRM: $300 |
| 5 | Business Units | ERP’s $400 splits to Sales ($240) and Eng ($160) based on user count | Sales: $240, Eng: $160 |

At each tier, the allocation engine applies the rules defined for that model object. The output of one tier becomes the input for the next. This is why proper sequencing is essential — and why the model diagram is invaluable for understanding cost flow.

## Circular Dependencies

A circular dependency occurs when Object A allocates to Object B, and Object B allocates back to Object A (either directly or through a chain of intermediate objects). This creates an infinite loop that cannot be resolved through normal sequential processing.

TBM Studio’s approach:

- Prevention: The model graph must not contain cycles. TBM Studio validates the dependency graph and prevents you from creating allocation configurations that would result in circular flows.
- Recursion as the exception: Recursion allocation (Section 4.3.4) is the only supported mechanism for handling mutual dependencies. It uses iterative processing with precision and iteration limits to converge on a result.
- Detection: If a circular dependency is inadvertently created (typically through complex multi-object configurations), the build process reports an error rather than entering an infinite loop.

Avoiding Circular Dependencies

Design your model hierarchy to flow in one direction — from cost sources at the bottom to business consumers at the top. If you find yourself needing a backward allocation, consider whether recursion allocation or a restructured model hierarchy would be more appropriate.
