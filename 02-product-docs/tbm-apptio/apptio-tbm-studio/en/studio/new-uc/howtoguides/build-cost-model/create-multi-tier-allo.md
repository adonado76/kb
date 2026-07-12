---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Create Multi-Tier Allocations"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Build Cost Models"
  - "Create Allocations"
source_path: "studio/new-uc/howtoguides/build-cost-model/create-multi-tier-allo.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create Multi-Tier Allocations

**Objective:** Build a complete cost flow that allocates costs through multiple layers
of your organization—from source costs through intermediate objects to final business
consumers.

**When to use:** Your cost model requires multiple allocation steps to accurately
reflect how costs flow through your organization. Most TBM implementations use 4-6
tiers.

**Time estimate:** 45-60 minutes for a four-tier model

## Understanding Multi-Tier Cost Flows

In enterprise cost modeling, costs rarely flow directly from source to final destination.
Instead, they pass through intermediate layers that add business context and enable granular
reporting.

**Common TBM Cost Flow Pattern:**

|  |
| --- |
| **Cost Source Actuals**  *(General ledger, invoices, labor costs)*  ▼  **Labor │ Vendors │ Facilities** (Tier 1)  ▼  **Technology Services** (Tier 2)  *(Compute, Storage, Network, End User)*  ▼  **Applications** (Tier 3)  *(SAP, Salesforce, Custom Apps)*  ▼  **Business Units** (Tier 4)  *(Sales, Marketing, Operations, HR)* |

## Step-by-Step: Build a Four-Tier Allocation Model

**Scenario:** Create a complete cost flow from Cost Source through Labor, Services,
Applications, to Business Units.

## Phase 1: Set Up the Model Structure

1. **Ensure all tables have Model steps**
   - Each table in the cost flow needs a Model step added to its transform pipeline.
   - Tables: Cost Source, Labor, Technology Services, Applications, Business Units.
2. **Plan the allocation sequence**
   - Cost Source → Labor (by expense type = "Labor")
   - Cost Source → Facilities (by expense type = "Facilities")
   - Labor → Technology Services (by time allocation %)
   - Technology Services → Applications (by service consumption)
   - Applications → Business Units (by app ownership)
3. **Check out all tables**
   - Check out every table involved in the allocation chain.

## Phase 2: Configure Tier 1 Allocations

From Cost Source, create separate allocations for each first-level object:

1. **Labor allocation:** Add From filter for Expense Type = "Labor"
2. **Facilities allocation:** Add From filter for Expense Type = "Facilities"
3. **Vendors allocation:** Add From filter for Expense Type NOT IN ("Labor",
   "Facilities")

## Phase 3: Configure Tier 2 Allocations

From each first-level object, allocate to Technology Services:

- Labor → Technology Services: Data Relationship = Role Type → Service Category, Weight By
  = Time Allocation %
- Facilities → Technology Services: Weight By = Square Footage
- Vendors → Technology Services: Data Relationship = Contract Category → Service
  Category

**Phase 4: Configure Tier 3 and 4 Allocations**

- **Technology Services → Applications:** Using = Consumption, Consumption Column = Units
  Consumed, Capacity Column = Total Capacity
- **Applications → Business Units:** Data Relationship = App Owner → Business Unit Code,
  Weight By = User Count

**Phase 5: Validate the Complete Flow**

1. **View the model diagram**
   - Open the model diagram view to verify all allocation lines are connected.
   - Check for any orphaned objects or missing connections.
2. **Trace a cost through the model**
   - Select a single cost item from Cost Source.
   - Use the traceability feature to follow it through each tier.
3. **Run a model calculation**
   - Execute a model calculation for the current period.
   - Review the Model Report (Sankey view) to visualize cost flow.

## Multi-Tier Best Practices

**Allocate downward, not upward**

- Always flow costs from Cost Source downward through the model.
- Reverse flows create complexity and potential circular references.

**Maintain consistent granularity**

- Each tier should have consistent granularity within its level.
- Avoid mixing highly detailed and highly aggregated data in the same tier.

**Document the model**

- Add descriptions to each model object explaining its purpose.
- Create a visual diagram of the intended cost flow for stakeholder communication.

**Parent topic:** [Create Allocations](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
