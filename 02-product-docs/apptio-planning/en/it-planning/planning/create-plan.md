---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Creating Plans"
breadcrumb:
  - "Planning"
  - "Creating and Managing Plans"
source_path: "it-planning/planning/create-plan.html"
images:
  - "resources/images/icons/icon-add.png"
  - "resources/images/it_planning_images/settings-icon.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Creating Plans

Note: Admin or Budget Process Owner roles are required to manage plans.

Apptio Planning enables you to create and manage financial plans that support both budgeting
and forecasting. Plans provide a central workspace for building budgets, adjusting forecasts,
and aligning investments across departments, projects, and resources.

## Plan Types

Apptio Planning supports two types of plans:

- **Budget Plan**– A plan without actuals. All periods are editable, allowing you to
  build a plan from scratch or reset projections without historical data.
- **Forecast Plan** –A plan that includes actuals for historical periods (sourced
  from Spend Management). Only future periods are editable, so you can adjust projections
  based on past performance.

## Creating a plan

1. From the navigation menu, select **Planning** > **Plans**
2. Select the ![add button](../../../../../03-media/apptio-planning/resources/images/icons/icon-add.png) button.
3. Choose a **Plan Type** (Budget or Forecast)
4. Enter the following details:

   |  |  |
   | --- | --- |
   | **Item** | **Description** |
   | Plan Start Year | Select the starting year for the plan. |
   | Plan Length | Select the plan duration (up to ten years). |
   | Forecast Start Period  (Forecast only) | Select the first editable period for the forecast. Historical periods will be pre-populated with actuals. To create a forecast plan using only actuals data for the selected plan duration, select **None** as the Forecast Start Period. |
   | Baseline Reference | Optionally copy data from an existing plan to use as a baseline. |
   | Copy Over Line Item Codes | Choose to copy Line Item Codes from the baseline or generate new codes.  Learn more about [Line Item Codes](line-item-codes.html). |
   | Auto Fill Plan Data | If the baseline and new plan include different fiscal years, this option fills in missing values with data from the final year of the baseline. |
   | Plan Name | Enter a unique name for the plan. |
5. Click the **Create Plan** button.

   When plan creation begins, the plan appears in the
   Plans page with a **Pending** status. Once complete, you’ll see a confirmation
   message, and the plan becomes available for selection across Planning.

   Note: Creating a
   plan from a baseline may take several minutes if large volumes of data are being
   copied.

## Plan Modules

Plans can be extended with additional modules to cover a variety of planning needs:

- **Financial Planning** – Plan operating expenses (OpEx) and capital expenses
  (CapEx). This module is enabled by default in all plans.
- **Labor Planning** – Plan for labor headcount and costs.
- **Contract Planning** – Plan for vendor contracts with amortization options.
- **Asset Planning** – Plan for asset purchases and depreciation.
- **Project Planning** – Plan for project expenses (build vs. run).
- **Project Labor Activity Planning** – Capture labor effort and costs for projects.

**To enable modules**:

1. In the upper right, navigate to **Settings** (![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/settings-icon.jpg) ) > **Company
   Profile**.
2. Select the modules you want to enable:
   - Labor Headcount
   - Contracts
   - Assets
   - Enable Integrated Investment Planning
   - Labor Activity (requires Integrated Investment Planning)
