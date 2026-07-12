---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Handle Unallocated Costs"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Build Cost Models"
  - "Create Allocations"
source_path: "studio/new-uc/howtoguides/build-cost-model/handle-unallocated-costs.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Handle Unallocated Costs

**Objective:** Manage costs that don't match allocation criteria to ensure 100% of costs
are accounted for in your model.

**When to use:** After running allocations, you have remaining costs that weren't
distributed to target tables. This commonly occurs when driver matching criteria don't cover
all source rows.

**Time estimate:** 15-30 minutes depending on strategy chosen

## Understanding Unallocated Costs

Unallocated costs occur when:

- Source rows don't match any target rows (no matching key values)
- Filters exclude certain source rows from all allocations
- Weighting values are zero for some target rows
- New data arrives that wasn't anticipated in the original allocation design

## Strategy 1: Create a Residual Pool

A residual pool is a catch-all target that receives costs that don't match any specific
allocation criteria.

**When to use:** You want to track unallocated costs separately for investigation while
ensuring the model balances.

**Steps**

1. **Create a residual pool table**
   - In Data Studio, create a new table called "Unallocated Costs" or "Residual Pool".
   - Add the table to the model with a Model step.
2. **Create a catch-all allocation**
   - On the source table, create a new allocation after all specific allocations.
   - Do not add any filters (this catches everything remaining).
   - Set Weight By = Even.
3. **Monitor the residual pool**
   - Regularly review residual pool amounts.
   - Large amounts indicate matching or data quality issues.

## Strategy 2: Even Distribution of Remaining Costs

Distribute unallocated costs evenly across existing targets rather than tracking them
separately.

**When to use:** Unallocated costs are small or it's acceptable to spread them
proportionally across all targets.

- Create a two-step allocation: first with specific matching, second with Even
  distribution for the remainder.
- Add a From filter on the second allocation to select only unmatched rows.

## Strategy 3: Proportional Distribution Using Metric Weighting

Distribute unallocated costs proportionally based on how other costs were already
allocated.

**When to use:** You want unallocated costs to follow the same distribution pattern as
allocated costs.

- Create a secondary allocation with Weight By = Metric.
- Select the metric from your primary allocation.
- This distributes remaining costs using the same proportions.

## Strategy 4: Fix the Root Cause

Eliminate unallocated costs by addressing the underlying data or configuration issues.

1. **Identify why costs are unallocated**
   - Export the unallocated rows from the preview.
   - Analyze the matching key values.
2. **Fix data quality issues**
   - If keys are misspelled or inconsistent, fix in source data or transforms.
   - If new categories appeared, add them to the target table.
3. **Update matching logic**
   - If matching criteria are too restrictive, broaden them.
   - Add additional data relationships if needed.

## Unallocated Costs Decision Matrix

|  |  |
| --- | --- |
| **Scenario** | **Recommended Strategy** |
| Large unallocated amount (>5% of total) | Fix root cause |
| Small unallocated amount (<5% of total) | Proportional distribution or residual pool |
| Need audit trail for unallocated | Residual pool |
| One-time data issue | Even distribution to existing targets |
| Credits or reversals causing negatives | Segregate and handle separately |

**Parent topic:** [Create Allocations](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
