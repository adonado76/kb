---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Use Matching Logic for Allocations"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Build Cost Models"
  - "Advanced Modeling"
source_path: "studio/new-uc/howtoguides/build-cost-model/use-logic.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Use Matching Logic for Allocations

## Objective

Configure data relationships to dynamically match source rows to target rows during
allocation, eliminating the need for multiple allocation lines when data changes.

## When to Use This Procedure

Use matching logic (data relationships) when:

- You need to allocate costs from a source to specific matching rows in a target table
  (e.g., data center costs to servers in that same data center)
- Your source and target tables share a common dimension (e.g., Data Center, Region,
  Vendor ID, Application Category)
- You want to avoid creating separate allocation lines for each unique value
- New values (e.g., new data centers) should automatically be handled without
  reconfiguration

**Prerequisites**

- Source and target tables both added to the model with Model steps
- Both tables contain a column with matching values (the relationship column)
- Tables checked out for editing

## Time Estimate

15-20 minutes

## Understanding the Concept

Without matching logic, you would need to create a separate allocation line for each unique
value. For example, to allocate data center costs only to servers in that same data center,
you might create:

- Allocation 1: From filter = "SEA", To filter = "SEA"
- Allocation 2: From filter = "NYC", To filter = "NYC"
- And so on for each data center...

This approach is not recommended because it creates maintenance overhead and requires
adding new allocation lines whenever your data changes.

The **Data Relationship** option solves this by creating a single allocation line that
automatically slices the allocation into buckets based on matching column values. Each
unique value in your data relationship column results in a separate SOURCE value and a
corresponding set of target rows.

## Example Scenario

**Before**: You have a Data Centers table with costs ($100,000 for SEA, $80,000 for NYC)
and a Servers table with servers in multiple data centers. Without matching logic, all
$180,000 would be allocated across all servers proportionally.

**After**: With a data relationship on the Data Center column, SEA costs ($100,000) are
allocated only to SEA servers, and NYC costs ($80,000) are allocated only to NYC
servers.

**Steps**

1. In Project Explorer, click the source table and click the Model step in the transform
   pipeline.
2. In the Sankey diagram, click Add Allocation under the Allocations heading (or click an
   existing allocation to edit it).
3. In the Allocate section, select the metrics to which the allocation will apply (e.g.,
   Cost, Budget).
4. Under Using, select your allocation type (Weighted Value, Even, or another distribution
   method).
5. Under To, select the target table.
6. Locate the Data Relationship section in the allocation configuration panel.
7. If Automatic relationship is enabled, clear the checkbox to configure explicit
   relationships.
8. In Source Column, select the column from the source table that contains the matching
   values (e.g., Data Center).
9. In Destination Column, select the corresponding column from the target table.
10. (Optional) To add additional matching criteria, repeat steps 8-9 for each additional
    column pair. All relationships must match for the value to be allocated.
11. Click Preview to verify the allocation results show costs flowing to the correct matching
    rows.
12. Click Save to apply your changes.

## Expected Results

The allocation preview shows:

- Source costs grouped by your relationship column(s)
- Each unique value receiving its own pool of costs
- Target rows receiving costs only from their matching source rows

## Using Multiple Data Relationships

You can specify more than one relationship when you need to match on multiple dimensions.
For example, to allocate vendor costs to applications by both Vendor ID and Region:

- Source Column 1: Vendor ID → Destination Column 1: Vendor ID
- Source Column 2: Region → Destination Column 2: Region

Note: When you specify multiple relationships, ***all*** relationships must match for
the value to be allocated. A row must match on both Vendor ID AND Region to receive
costs.

## Common Pitfalls

- Mismatched values: Ensure the values in your source and destination columns match
  exactly (including case sensitivity and whitespace). Mismatched values result in
  unallocated costs.
- NULL values: Rows with NULL in the relationship column will not match and costs will
  remain unallocated.
- Legacy automatic relationships: If you see errors about "Legacy model join operation,"
  clear the Automatic relationship checkbox and configure explicit source and destination
  columns.
- Too many relationships: Adding excessive matching criteria can result in no matches.
  Start with one or two key relationships.

## Related Tasks

- [Configure weighting columns](config-wc.html)
- [Handle Unallocated Costs](handle-unallocated-costs.html)
- [Trace Cost Flows Through the Model](trace-cost-flow.html)

**Parent topic:** [Advanced Modeling](../../../../studio/new-uc/howtoguides/build-cost-model/adv-model.html)
