---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Set Up Simple Allocations (One-to-One)"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Build Cost Models"
  - "Create Allocations"
source_path: "studio/new-uc/howtoguides/build-cost-model/setup-sa.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Set Up Simple Allocations (One-to-One)

**Objective:** Distribute costs from a source table to a target table using a
straightforward distribution method.

**When to use:** You need to allocate costs based on a measurable attribute such as
headcount, server count, user count, or square footage. This is the most common allocation
pattern and serves as the foundation for more complex cost models.

**Time estimate:** 15-20 minutes

## Understanding Allocation Types

Before creating an allocation, choose the type that best fits your scenario:

|  |  |  |
| --- | --- | --- |
| **Allocation Type** | **Use When** | **Example** |
| **Weighted Value** | Distribute costs proportionally based on a numeric column | Allocate datacenter costs based on CPU usage |
| **Consumption** | Model actual consumption against available capacity | Allocate service costs based on units consumed |
| **Standard Value** | Target table contains the exact amount to allocate | Allocate fixed costs where target specifies the dollar amount |
| **Even** | Equal distribution across all target rows | Split shared costs equally among departments |

## Step-by-Step: Create a Weighted Value Allocation

This procedure demonstrates the most common allocation pattern—distributing costs
proportionally based on a weighting column.

**Scenario:** Allocate $500,000 in datacenter costs to five applications based on their
server counts.

**Steps**

1. **Check out both tables**
   - In Project Explorer, right-click the source table (e.g., "Datacenter Costs") and
     select Check Out.
   - Repeat for the target table (e.g., "Applications").
2. **Open the source table's Model step**
   - Click the source table in Project Explorer.
   - In the transform pipeline, click the Model step.
   - The model workspace opens, displaying the Sankey diagram.
3. **Add a new allocation**
   - In the Sankey diagram, click Add Allocation under the Allocations heading.
4. **Configure the allocation settings**
   - **Allocate:** Select the metrics this allocation applies to (e.g., Cost,
     Budget).
   - **Using:** Select Weighted Value as the allocation type.
   - **To:** Select the target table (e.g., "Applications").
5. **Set up the weighting**
   - Under Weight By, select Table (the most common option).
   - Select the column that contains your weighting values (e.g., "Server Count").

   Tip: The weighting column must contain numeric values only. Non-numeric
   values cause the weighting to be ignored, resulting in even distribution
   instead.
6. **Preview the allocation**
   - Click Preview to see how costs will be distributed.
   - Review the preview table to verify the allocation percentages match your
     expectations.

   |  |  |  |
   | --- | --- | --- |
   | **Application** | **Server Count** | **Allocation Amount** |
   | App A | 50 | $125,000 (25%) |
   | App B | 80 | $200,000 (40%) |
   | App C | 30 | $75,000 (15%) |
   | App D | 25 | $62,500 (12.5%) |
   | App E | 15 | $37,500 (7.5%) |
   | **Total** | **200** | **$500,000** |
7. **Save the allocation**
   - Click Save to add the allocation to your model.
   - The Sankey diagram updates to show the allocation line connecting the source to the
     target.

## Expected Results

After saving:

- The Sankey diagram displays a line from the source table to the target table.
- The line width is proportional to the allocated amount.
- Hovering over the allocation line shows the total allocated value.
- The target table now contains allocated costs that can flow to subsequent tables.

## Distribution Options Explained

**Even Distribution (Default)**

- Distributes costs equally across all target rows.
- Use when no weighting factor exists or when equal distribution is intentional.
- Example: $100,000 allocated to 5 applications = $20,000 each.

**Weight By**

- Distributes costs proportionally based on a Table column, Metric, or Other Driver.
- Example: $100,000 allocated to applications weighted by user count.

**Data Relationship**

- Distributes costs to matching rows based on column value pairs.
- Use when source and target share a common key (e.g., Region, Department).
- Example: Regional datacenter costs allocated only to applications in the same
  region.

## Common Pitfalls

|  |  |  |
| --- | --- | --- |
| **Issue** | **Symptom** | **Solution** |
| Non-numeric weighting column | Costs distribute evenly instead of by weight | Check the weighting column for text values, blanks, or special characters |
| Negative weighting values | Allocation fails with error | Negative values block allocation. Use absolute values or segregate data. |
| Zero weighting for all rows | Even distribution occurs | Ensure at least some target rows have non-zero weighting values |
| Table not checked out | Cannot save allocation | Check out both source and target tables before configuring |

**Parent topic:** [Create Allocations](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
