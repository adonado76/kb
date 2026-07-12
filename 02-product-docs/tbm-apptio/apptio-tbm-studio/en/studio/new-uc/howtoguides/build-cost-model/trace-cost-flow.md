---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Trace Cost Flows Through the Model"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Build Cost Models"
  - "Advanced Modeling"
source_path: "studio/new-uc/howtoguides/build-cost-model/trace-cost-flow.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Trace Cost Flows Through the Model

## Objective

Use the model diagram and drill-down capabilities to trace cost flows and answer the
question: "Where did this cost come from?"

## When to Use This Procedure

Use cost tracing when:

- A stakeholder asks why a business unit or service received a specific cost amount
- You see unexpected allocation results and need to diagnose the cause
- You need to verify that costs are flowing through the correct path
- You are debugging unallocated costs
- You need to audit the allocation path for compliance or financial review

**Prerequisites**

- Model has been built and calculated (costs flowing through allocations)
- You know which model object or cost amount you want to trace

## Time Estimate

5-15 minutes (depending on model complexity)

## Understanding the Model Views

TBM Studio provides three complementary views for tracing cost flows:

- Single Object Modeler: Shows drivers and allocations for one table at a time. Best for
  detailed configuration and immediate upstream/downstream visibility.
- Diagram View: Displays all model objects and their connections in a visual layout. Best
  for understanding the full model structure and navigation.
- Model Report (Sankey View): Presents cost flows in a user-friendly tiered visualization.
  Best for stakeholder communication and end-to-end tracing.

## Method 1: Using the Diagram View

The diagram view provides a high-level visualization of the entire cost model, similar to a
Visio diagram.

1. In Project Explorer, expand the model and click on the model diagram (or access it from
   the View menu).
2. The diagram displays all model objects as rectangles with allocation lines connecting
   them. The width of each line is proportional to the value flowing through it.
3. Use zoom and pan controls to navigate large models.
4. Click on any model object (rectangle) to open the Single Object Modeler for that table,
   showing its inputs and outputs.
5. To trace a specific allocation path, click through the chain: Cost Source → Vendors →
   Technology Services → Solutions → Business Units.

## Method 2: Using the Single Object Modeler

The Single Object Modeler provides detailed tracing for a specific table's inputs and
outputs.

1. In Project Explorer, click the model object you want to trace and click the Model
   step.
2. The view displays: left column shows incoming drivers and allocations, center shows the
   current object, right column shows outgoing allocations.
3. Click on any incoming allocation (left side) to see what source is contributing cost and
   what matching/weighting criteria are applied.
4. Click on any outgoing allocation (right side) to see where costs flow downstream and
   what distribution method is used.
5. Click on a destination object to navigate to that object's modeler view, allowing you to
   trace further downstream.

## Method 3: Drilling Down to Detail

For granular tracing, use the drill-down feature to see allocation details at the row
level.

1. From the Model step view, click the menu icon (≡) on the table you want to drill
   into.
2. Click Drill Down and select a column (e.g., Data Center, Vendor Name, Cost Pool).
3. The view now shows each unique value in that column with its associated costs.
4. Click on a specific value (e.g., a particular data center) to see only allocations
   to/from that value.
5. To return to the table view, click the return arrow icon in the upper-left corner of the
   tier.

## Example: Tracing an Unexpected Cost

**Scenario**: A business unit owner asks why they received $50,000 in network costs when
they expected less.

1. Open the Business Units model object and locate the business unit in question.
2. Review the incoming allocations to see which upstream objects contributed network
   costs.
3. Click on the allocation from Technology Services to see the matching criteria and
   weighting.
4. Navigate upstream to the Technology Services object and trace back to Vendors.
5. Continue tracing until you identify the original cost source and understand the
   allocation path.

## Best Practices

- Use the diagram view for onboarding new team members and training
- Use traceability features to isolate unexpected allocations before modifying the
  model
- Check unallocated costs after changing matching logic—they often indicate configuration
  issues
- Document allocation paths for audit purposes using model reports

## Related Tasks

- [Create model reports](create-model-rep.html)
- [Handle Unallocated Costs](handle-unallocated-costs.html)
- [View the Model Diagram](view-model-diagram.html)

**Parent topic:** [Advanced Modeling](../../../../studio/new-uc/howtoguides/build-cost-model/adv-model.html)
