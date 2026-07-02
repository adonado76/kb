---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "View the Model Diagram"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Build Cost Models"
  - "Model Basics"
source_path: "studio/new-uc/howtoguides/build-cost-model/view-model-diagram.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# View the Model Diagram

|  |  |
| --- | --- |
| **Content Type** | How-To Guide |
| **Target Audience** | Business Analysts, IT Finance Teams, Administrators |
| **Time Estimate** | 5-10 minutes |
| **Prerequisites** | At least one table added to the model |

## Objective

View the model diagram to understand the overall structure of your cost model, see how
tables connect through allocations, and trace the flow of costs through your
organization.

## When to Use This Procedure

View the model diagram when you need to:

- Understand the end-to-end cost flow in your model
- Onboard new team members by showing them the model structure
- Debug allocation issues by tracing cost paths
- Document your model design for stakeholders
- Verify that newly added tables are connected correctly

## Available Model Views

TBM Studio provides three ways to visualize your model:

**1. Single Object Modeler (Sankey Diagram)**

This is the default view when you click the Model step in a table's transform pipeline. It
shows the selected table in the center, with its drivers on the left and allocation
destinations on the right. Use this view when configuring drivers and allocations for a
specific table.

**2. Modeled Metric View (Full Model Diagram)**

This view displays all model objects and their connections in a Visio-like diagram. It
shows the entire cost flow from source tables through intermediate layers to final
destinations. Use this view to understand the big picture of your model.

**3. Model Reports (Tiered Sankey View)**

Model reports present the model in a user-friendly format with defined tiers (such as
Financials, Cost Pools, Infrastructure, Services). These are designed for end-user
consumption and provide drill-down capabilities.

## Steps: View the Modeled Metric Diagram

To view the full model diagram showing all tables and their connections:

1. **Open any model object.** In Project Explorer, select a table that has a Model step,
   then click the **Model** step in the transform pipeline.
2. **Switch to the Modeled Metric view.** On the **View** menu, click **Modeled
   Metric**. The diagram expands to show all model objects and their relationships.
3. **Navigate the diagram.** Use zoom and pan controls to explore the model. Click any
   model object to highlight its connections and view its details.
4. **Select a metric to view.** Use the metric selector at the top of the diagram to
   switch between Cost, Budget, Forecast, or other metrics. The diagram updates to show
   values for the selected metric.

## Interpreting the Model Diagram

The model diagram uses a Sankey-style visualization where:

- Rectangles represent model objects (your tables)
- Lines between rectangles represent allocations
- Line width is proportional to value — thicker lines indicate more cost flowing through
  that path
- Value flows from left to right (or bottom to top in some views)

**Reading the flow:** Start at the leftmost (or bottom) objects — these are typically
your cost sources where money enters the model. Follow the lines rightward (or upward) to
see how costs distribute to intermediate objects and eventually reach final destinations
like Business Units or Services.

## Common Diagram Patterns

**Single source, multiple targets:** A cost source table allocating to several cost pool
categories (Labor, Facilities, Hardware). The allocation lines fan out from the source.

**Multiple sources, single target:** Several infrastructure components (Servers,
Storage, Network) all allocating to Applications. The lines converge at the target.

**Cascading allocations:** Cost Source → Vendors → Technology Services → Solutions →
Business Units. Each tier allocates to the next, creating a sequential flow.

## Using the Diagram for Troubleshooting

**Missing connections:** If a table appears isolated with no lines connecting it, the
allocation has not been configured. Check the table's Model step to add allocations.

**Unexpected thin lines:** If an allocation line is much thinner than expected,
investigate the allocation weights or driver data. There may be unmatched records causing
costs to remain unallocated.

**Tracing specific costs:** Click on a model object in the diagram to highlight its
connections. You can trace forward to see where costs go, or backward to see where they come
from.

**Tip:** The model diagram reflects the currently deployed model configuration. Changes
made to allocations will not appear until you save, check in, and the project
recalculates.

## Navigating from the Diagram

The diagram is interactive. Clicking on a model object opens its Single Object Modeler
view, where you can configure drivers and allocations. This makes it easy to drill from the
big picture into the details of a specific table.

## What's Next

- Configure allocations for tables that are not yet connected — see Section 3.2.2
- Create model reports to expose the model to end users — see Section 3.3
- Use drill-down features to trace specific cost items — see Model Studio Reference
  (Section 5.2)

## Related Concepts

- [Model Architecture](../../concepts-architecture/model-architecture/model-concepts-overview.html) — Understanding how allocations execute and metrics flow
- Model Reports (Section 5.2) — Creating end-user-facing model visualizations

**Parent topic:** [Model Basics](../../../../studio/new-uc/howtoguides/build-cost-model/model-basics.html)
