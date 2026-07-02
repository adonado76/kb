---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "services-bu-data.html"
title: "Add services and business unit budget data"
breadcrumb: []
source_path: "services-bu-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Add services and business unit budget data

Add services and business unit budget data only if you installed theBilling Standard
- Plan Variance component. The data will be used to compare the planned spend against
the actual spend. If you have not installed theBilling Standard - Plan
Variance component, do not perform this step. If you already have a budget model
configured in your Cost Transparency project, use that Budget model and allocate from IT Resource
Towers into Consumption Feed.

Data requirements

The data must include the columns described below.

- Service ID - Must match the Service IDs in the Service Library
  table.
- Total budget for the service by month - If you are loading an entire
  year of data, include separate columns for each month of the year. After uploading the data, add a
  Date partition step to the transform pipeline.
- Business Unit ID (optional) - Must match the Business Unit IDs in
  the Business Services table.

When you upload the table, name it `Service and Business Unit Budget Data` and
place the table in the General category.

Use the data in models

To use the services and business unit budget data in models, perform the following tasks.

1. Add a model step to the Service and Business Unit Budget Data table.
2. In the Budget and Business Budget models, add a unit driver based on the budget column in the table.
     
   If you want to compare cost and charge to separate budgets, add two drivers: one for Business Budget, and one for Budget.
3. Add an allocation to the Business Services model object.

**Parent topic:** [Billing Standard](home.html)
