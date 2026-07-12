---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Add a Table to the Model"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Build Cost Models"
  - "Model Basics"
  - "Add a Table to the Model"
source_path: "SSWRJM/studio/new-uc/howtoguides/build-cost-model/add-tables.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Add a Table to the Model

| Content Type | How-To Guide |
| --- | --- |
| Content Type | How-To Guide |
| Target Audience | Business Analysts, IT Finance Teams |
| Time Estimate | 5-10 minutes per table |
| Prerequisites | Transform table created in Data Studio with data uploaded |

## Objective

Add a transform table to the cost model so it can participate in allocations and appear in model reports.

## When to Use This Procedure

Use this procedure when you have prepared a table in Data Studio and want to include it in your cost model. Common scenarios include:

- Adding your Cost Source table that contains general ledger or financial data
- Adding target tables like Business Units, Applications, or Services
- Adding intermediate tables like Vendors, Infrastructure, or IT Towers
- Bringing in driver tables that will be used to weight allocations

## Background: Transform Tables vs. Model Objects

In TBM Studio, creating a table in Data Studio and adding it to the model are separate steps. A transform table is where you prepare, clean, and structure your data. A model object is when that table participates in the cost model — with drivers, allocations, and metric flows.

Adding a Model step to a table's transform pipeline converts it into a model object. Until you do this, the table exists only in Data Studio and cannot receive or allocate costs.

## Steps

1. Check out the table. In the Project Explorer, locate the table you want to add to the model. Right-click and select Check Out , or select the table and click Check Out on the Home tab.
1. Open the transform pipeline. Click on the table name to open it. You will see the transform pipeline on the left side of the workspace, showing the sequence of steps applied to your data (Source, Import, Formula steps, etc.).
1. Add a Model step. Click Add Step at the bottom of the transform pipeline. In the step type selector, choose Model . The Model step is added to your pipeline.
1. View the model workspace. Click on the new Model step in the pipeline. The workspace now displays a single-table view showing your table in the center, with spaces for drivers on the left and allocation destinations on the right. This is the Sankey diagram view.
1. Save your changes. Click Save on the Home tab to preserve your changes.
1. Check in the table. When finished, click Check In to make your changes available to others and to the model calculations.

## Expected Results

After completing these steps:

- The table appears in the Model step view with its name displayed in the center column
- The table is now a model object that can receive drivers and participate in allocations
- You can view the table in the model diagram (View > Modeled Metric) alongside other model objects
- The table is available as a source or target when creating allocations from other tables

## Common Pitfalls

Table has no data for the current period. Model calculations are period-specific. If your table has no data uploaded for the currently selected time period, it will appear empty in the model. Verify that data exists by checking the table in the Output step before adding the Model step.

Forgetting to check out before adding the Model step. You must check out a table before you can modify its transform pipeline. If you try to add a step without checking out, you will receive an error.

Model step placement. The Model step should typically be the last step in your pipeline (or near the end, before any Row-Level Security step). Adding transformation steps after the Model step may cause unexpected behavior.

## What's Next

- Add unit drivers to bring value into your cost source tables
- Create allocations to flow value between tables
- View the model diagram to see how your table fits into the overall cost flow.

## Related Concepts

- Model Architecture — Deep dive into how the modeling engine works
- Data Architecture — Understanding the relationship between Data Studio and Model Studio
