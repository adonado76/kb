---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Configure Weighting Columns"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Build Cost Models"
  - "Advanced Modeling"
  - "Configure Weighting Columns"
source_path: "SSWRJM/studio/new-uc/howtoguides/build-cost-model/config-wc.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Configure Weighting Columns

## Objective

Configure weighted value allocations that distribute costs proportionally based on a numeric column, rather than evenly across all target rows.

## When to Use This Procedure

Use weighting columns when:

- Not all target entities are equal (e.g., servers have different CPU counts, applications have different user counts)
- You have a measurable metric that reflects relative consumption or capacity
- You want larger consumers to receive proportionally more cost than smaller consumers
- An even distribution would not accurately reflect actual consumption or usage patterns

Prerequisites

- Source and target tables both added to the model
- Target table contains a numeric column with weighting values
- Weighting column contains non-null, non-negative numeric values (see notes on negative values below)
- Tables checked out for editing

## Time Estimate

10-15 minutes

## Understanding the Concept

A weighted value allocation distributes costs based on the ratio (relative size) of values in a column you select from the target table. The formula is:

Allocation to Row = SOURCE × (Row's Weight / Total Weight of All Matching Rows)

For example, if you are allocating $100,000 across five servers based on CPU count:

| Server | CPU Count | Allocation |
| --- | --- | --- |
| Server | CPU Count | Allocation |
| Server A | 4 | $10,000 (4/40 = 10%) |
| Server B | 8 | $20,000 (8/40 = 20%) |
| Server C | 16 | $40,000 (16/40 = 40%) |
| Server D | 8 | $20,000 (8/40 = 20%) |
| Server E | 4 | $10,000 (4/40 = 10%) |
| Total | 40 | $100,000 |

## Steps

1. In Project Explorer, click the source table and click the Model step in the transform pipeline.
1. In the Sankey diagram, click Add Allocation (or click an existing allocation to edit it).
1. In the Allocate section, select the metrics to which the allocation will apply.
1. Under Using, select Weighted Value as the allocation type.
1. Under To, select the target table.
1. In the distribution options, select Weight By.
1. Select the numeric column from the target table that contains your weighting values (e.g., CPU Count, User Count, Square Feet).
1. (Optional) Configure data relationships if you need to match source to target rows.
1. Click Preview to verify costs are distributed proportionally based on your weighting column.
1. Click Save to apply your changes.

## Expected Results

The allocation preview shows:

- Each target row's weight value and its percentage of the total
- Allocated cost proportional to the weight ratio
- Total allocated cost matching the source amount

## Advanced: Using Other Driver Weighting

In TBM Studio 12.5 and later, you can use Other Driver to weight an allocation based on the results of a different allocation. This is useful when you want consistent weighting across multiple allocations.

For example, if you have already allocated Labor costs to IT Resource Towers, you could use that same weighting pattern to allocate Project costs to IT Resource Towers. Select Other Driver and choose the existing Labor driver to maintain consistency.

## Common Pitfalls

- Non-numeric values: If your weighting column contains at least one non-numeric value, the weighting will be ignored and costs will be distributed evenly. Clean your data to ensure all values are numeric.
- All zeros: If all weighting values are 0, costs are distributed evenly across target rows (fallback behavior via the Ratio function).
- NULL values: Rows with NULL in the weighting column will not receive any allocation.
- Negative values: By default, TBM Studio does not allocate when negative weightings are present, as this can result in unexpected outcomes. If you must use negative weights, consult the documentation on negative number handling.

## Related Tasks

- Use Matching Logic for Allocations
- Create formula allocations (Section 5.2 Reference)
- Handle Unallocated Costs
