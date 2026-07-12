---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Unallocated Costs"
breadcrumb:
  - "Concepts and Architecture"
  - "Model Architecture"
  - "Unallocated Costs"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/model-architecture/unallocated-costs.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Unallocated Costs

Unallocated costs are one of the most important concepts to understand in cost modeling. They represent costs that entered the allocation engine but did not find a matching target — money that “fell through the cracks” of your model.

## What Are Unallocated Costs?

When an allocation runs, it attempts to distribute every dollar from the source to one or more targets. If the driver or matching logic cannot find a target for some portion of the source costs, those costs remain unallocated. They stay in the source object rather than flowing downstream.

Unallocated costs are not an error in the traditional sense — they are a signal. They tell you that your model’s rules do not fully account for all your data. In a well-tuned model, unallocated costs should be minimal.

## Common Causes

| Cause | Example | Resolution |
| --- | --- | --- |
| Cause | Example | Resolution |
| Missing driver data | The FTE count table does not include a newly created business unit, so costs targeting that unit have no weight to distribute | Update the driver table to include the missing entity |
| Mismatched dimension values | Source data uses vendor code “AWS-001” but the target table uses “Amazon Web Services” as the matching key | Standardize dimension values through transform mappings |
| Incomplete mapping tables | A mapping table linking applications to business units is missing 15 applications that were recently added | Add the missing mappings to the mapping table |
| Data quality issues | A weighting column contains null or non-numeric values for some rows, causing them to be excluded from allocation | Clean the weighting data in Data Studio |
| New categories not yet modeled | A new expense type appears in GL data that does not match any existing allocation rule | Add a new allocation rule or category mapping |

## Handling Strategies

Strategy 1: Investigate and Resolve

The best approach is to treat unallocated costs as a data quality signal and address the root cause. Use the allocation preview in the Single Object Modeler to identify which rows remain unallocated, then trace back to determine why.

Steps:

1. Open the model object in the Single Object Modeler
1. Review the allocation preview to identify unallocated rows
1. Check driver data and matching logic for gaps
1. Update transform tables or mapping data as needed
1. Re-run the build and verify unallocated amounts decrease

Strategy 2: Residual Pools

When some costs cannot be meaningfully attributed to a specific target, you can create a residual pool — a catch-all model object that collects unallocated costs for visibility and further analysis.

- When to use: When you have a small percentage of costs that defy categorization, and you want to make them visible in reports rather than leaving them hidden.
- Caution: A large residual pool is a red flag. If more than 5–10% of your costs land in residual, your model likely needs attention.

Strategy 3: Even Distribution of Residuals

As a last resort, you can spread unallocated costs evenly across all targets. This ensures your model “balances” (total source equals total target), but it sacrifices allocation accuracy.

- Pros: Model totals balance; no costs are hidden
- Cons: Dilutes precision; assigns costs to entities that may not have consumed them

Monitor Unallocated Costs Continuously

After every build, check unallocated costs. A model that balanced perfectly last month may have new unallocated amounts this month due to data changes. Build a reporting habit of reviewing unallocated amounts as part of your monthly close process.
