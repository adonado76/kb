---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Create Model Reports (Sankey Diagrams)"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Build Cost Models"
  - "Advanced Modeling"
source_path: "studio/new-uc/howtoguides/build-cost-model/create-model-rep.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create Model Reports (Sankey Diagrams)

## Objective

Create a model report that visualizes cost flows through your model in a Sankey diagram
format, enabling stakeholder communication and auditability.

## When to Use This Procedure

Create model reports when:

- You need to communicate cost flows to non-technical stakeholders
- You want to provide an intuitive visualization of how costs cascade through the
  model
- You need to support financial audits or transparency initiatives
- You want end users to explore cost flows interactively without accessing Model
  Studio
- You are presenting IT finance data to business unit leaders

**Prerequisites**

- Model has been built with allocations flowing between objects
- Tables you want to include in the report have Model steps
- You have determined the tiers (layers) you want to display

## Time Estimate

20-30 minutes for initial setup; 5-10 minutes for modifications

## Understanding Sankey Diagrams

In a Sankey diagram, value flows from left to right. The width of each allocation line is
proportional to the value it represents. This visual metaphor makes it easy to see:

- Which sources contribute the most cost (widest lines)
- How costs split as they flow through the model
- The relative proportion of costs reaching each destination

## Steps to Create a Model Report

1. In Project Explorer, right-click on the Models folder under Reports and select New Model
   Report.
2. Enter a name for your model report (e.g., "IT Cost Flow" or "Labor Cost Model").
3. The report opens in the model report editor. Check out the report for editing.
4. Click the View menu on the Home tab and select Show Tier Editor.
5. In the Tier Editor, click the Add Tier icon to create your first tier.
6. Click in the Name field at the top of the tier and enter a descriptive name (e.g.,
   "Financials", "Cost Pools", "Infrastructure", "Services").
7. From Project Explorer, drag a modeled table into the tier. Repeat to add multiple tables
   to the same tier if needed.
8. Alternatively, expand a table in Project Explorer and drag a specific column to create a
   tier focused on that dimension (e.g., drag Cost Pool column instead of the full
   table).
9. Repeat steps 5-8 to create additional tiers representing each layer of your model.
10. Use the Rearrange icon to drag tiers into the correct left-to-right order.
11. Click View > Show Document to preview your model report.
12. Save and check in the report.

## Configuring Tiers

Tiers control the layout and granularity of your model report. Consider these options:

- Table tier: Shows the entire table. Users can click the menu and select Drill Down to
  see individual columns.
- Column tier: Shows a specific dimension (e.g., Cost Pool, Vendor Name). Provides focused
  analysis.
- Multi-table tier: Contains multiple tables at the same level. Useful for showing
  parallel cost flows.

Note: A tier can contain a single column OR one or more tables, but not both.

## Interacting with Model Reports

Once created, users can interact with model reports in these ways:

- Click a table element to see its drivers and allocations
- Continue clicking table elements to trace the flow of value through the model
- Open the menu in a table and click Drill Down to see values by a specific column
- Click on allocation lines to view underlying transaction-level detail

## Adding Model Reports to Report Collections

In TBM Studio 12.2.2 and later, you can add model reports to report collections for easier
access:

1. Open the model report and check it out.
2. Click the Modeling tab in the ribbon.
3. Click Assign to Collection.
4. Select the target report collection from the dropdown.
5. Save and check in the report.

## Best Practices

- Use clear, business-friendly tier names ("IT Infrastructure" not "Tier 3")
- Limit tiers to 4-6 for readability—too many tiers overwhelm viewers
- Create multiple focused model reports rather than one comprehensive report
- Use column tiers when you want to highlight a specific dimension (e.g., Cost Pool
  flow)
- Add model reports to report collections so end users can easily find them

## Related Tasks

- [Trace Cost Flows Through the Model](trace-cost-flow.html)
- [Build Report Collections](../create-reports/build-rc.html)
- [View the Model Diagram](view-model-diagram.html)

**Parent topic:** [Advanced Modeling](../../../../studio/new-uc/howtoguides/build-cost-model/adv-model.html)
