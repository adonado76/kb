---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Best practices: Forecasting"
breadcrumb: []
source_path: "planning/bp-forecasting.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Best practices: Forecasting

In a forecast, historical months are replaced with actuals to provide a single, hybrid
view of performance to date and an outlook for the remainder of the year. This document covers best
practices for forecasting, including examples and specific tasks for creating forecasts.

For more information on the broad who-does-what workflow of forecasting in Apptio planning
applications, see [Budget
planning and forecasting](budget-planning-forecasting.htm "(Opens in a new tab or window)").

## Example: Create the first forecast of 2018

In this example, we assume a quarterly forecasting cadence and a fiscal year aligned to the
calendar year.

Previously, a finalized budget named FY2018 Budget was created for FY18. Now, it is April 2018,
so it is time to create the first quarterly forecast of FY2018. This will be the Q2 Forecast. This
example includes the following tasks:

- [Task 1: Validate actuals](#best_practices_forecasting__Validate-actuals)
- [Task 2 (optional): Update targets in the baseline budget](#best_practices_forecasting__Update-baseline-budget)
- [Task 3: Create a forecast plan](#best_practices_forecasting__forecast-plan)
- [Task 4: Enable plan features for the forecast](#best_practices_forecasting__features-4-forecast)
- [Task 5 (optional): Update labor, contracts, and assets](#best_practices_forecasting__labor-contracts-assets)
- [Task 6: Enable budget owners to make updates](#best_practices_forecasting__budget-owners-updates)

## Task 1: Validate actuals

In Spend Management, ensure that the actuals are correctly loaded into
January 2018, February 2018, and March 2018. For more information, see [Import and publish actuals](import-publish-actuals.htm "(Opens in a new tab or window)").

## Task 2 (optional): Update targets in the baseline budget

Targets provide the ability to store a year-end OpEx, CapEx, and Headcount target for each
Department. KPIs and graphs throughout the application provide convenient comparisons to targets.
Because targets are copied forward into new plans, storing the approved budget amounts as targets in
the baseline budget provides an easy way to carry those forward into future forecast plans. See
[Set financial
targets](set-financial-targets.htm "(Opens in a new tab or window)").

## Task 3: Create a forecast plan

When creating a forecast, note the following and see also [Create a plan or forecast](create-budget-plan.htm "(Opens in a new tab or window)"):

1. `Forecast Start Period` - Specifies the first month of the forecast that does not
   contain actuals. Because the Q2 Forecast has actuals for January, February, and March, in this case,
   set the forecast's start period to April.
2. `Baseline` - Specifies which plan from which to copy plan data. All data (for
   example,Contracts,Assets,Labor,Targets,Other Expenses, and so on), except financial amounts for
   actuals months, will be copied from the specified plan into the new plan. Because this is the first
   forecast of FY2018, use the FY2018 Budget for the baseline.
3. `Summarize actuals down to the following dimensions and/or attributes` - Only
   columns that are checked will be pulled through from Spend Management into the new forecast. It is
   recommended that you check most or all of these values to maximize the granularity of actuals data
   in the new forecast. The following example shows how selecting various options to summarize impacts
   the granularity of the actuals data in the new forecast:
4. `Rolling forecasts` - If a rolling forecast was used, creating a two- or
   three-year plan to ensure that the forecast contains 4-6 future quarters.
5. `Reference data usage` - The new forecast will use the latest published version
   of all Reference data dimensions, so:
   - Actuals pulled into the forecast will use the latest Reference data regardless of the version
     being used in Spend Management.
   - Plan data pulled into the forecast from the baseline plan will use the latest Reference data
     regardless of the version in the baseline plan.

## Task 4: Enable plan features for the forecast

Configure Variance Drivers on the forecast with the following options:

- `Compare Plan` - The original budget, FY2018 Budget
- `Comparison Period` - Because this is the first forecast of the year, choose Q1
  FY18

When editing line items, use the Compare Shortcuts feature to add a
comparison to the FY2018 Budget so that users can see a comparison to the original budget.

## Task 5 (optional): Update labor, contracts, and assets

It might be more efficient to make some broad-based forecast updates before opening the plan to
all budget owners.

1. Labor updates
   - `Updates for new hires:`
     1. Add the new hires to the
        Expenses > Labor > Existing
        tab.
     2. Remove the filled open headcount from the
        Expenses > Labor > Planned
        tab.
   - `Updates for delayed hires` - Update the open headcount Start
     Date on the
     Expenses > Labor > Planned
     tab.
   - `Updates for canceled hiring` - Update the open headcount
     Quantity to 0 on the
     Expenses > Labor > Planned
     tab.
   - `Updates for employee departures` - Update the employee End
     Date to the termination date on the
     Expenses > Labor > Existing
     tab.
2. Assets updates
   - `Updates for new purchases:`
     1. Add the actual purchase to the
        Expenses > Assets > Existing
        tab.
     2. Remove the planned purchase from the
        Expenses > Assets > Planned
        tab.
   - `Updates for delayed purchases:`
     1. Update the planned Purchase Date (and In Service
        Date, if appropriate) with the future date on the
        Expenses > Assets > Existing
        tab.
   - `Updates for canceled purchases` - Update the planned purchase
     `Quantity` to 0 on the
     Expenses > Assets > Existing
     tab.
3. Contracts updates
   - `Updates for delayed contracts:`
     1. If the contract start date was delayed, update the planned contract Start
        Date on the
        Expenses > Contracts tab.
     2. If the contract started on time, but amortization/invoicing was delayed, update the existing
        contract Amortization Start Offset on the
        Expenses > Contracts tab.
   - `Updates for canceled contracts` - Update the planned contract
     Amount to 0 on the
     Expenses > Contracts tab.

Budget owners are also able to make any of these updates when the plan is opened.

## Task 6: Enable budget owners to make updates

After you open the forecast, budget owners can make updates to the future periods of the plan,
but not to actuals periods, which are read-only.

Use the Compare feature against the original FY19 Budget to ensure
alignment with the budget for each department, account, or cost pool, and so forth, when reviewing
and approving changes from the users.

Note: The Headcount Compare feature is currently available on the Summary
page, Headcount tab only.

## Create subsequent forecasts for the year

Eventually, it will be time to create the second major quarterly forecast of the year. Actuals
will be loaded for April, May, and June, thereby enabling the creation of the Q3 Forecast.

The tasks are the same as with the first forecast of year above, except for the choice of the
baseline plan.

To ensure that you include updates made in the Q2 Forecast, use the Q2 Forecast as the baseline
for the Q3 Forecast. This means that all data (except for actuals financial amounts, which are
loaded from Spend Management) will be copied from the Q2 Forecast into the
new Q3 Forecast.

## Budget variance analysis strategies

There are two common approaches (and several variations) for performing variance analysis on
forecasts throughout the year.

1. Variance analysis to previous forecast
   - `Compare plan` - Q2 Forecast.
   - `Compare period` - Q2, since those new actuals are being compared to the forecast
     updates that were made in the Q2 Forecast.
   - `Evaluate year-end totals vs. the baseline budget` - Specify a Compare
     Shortcut of the FY2018 Budget.
2. Variance analysis to original budget
   - `Compare plan` - FY2018 Budget.
   - `Compare period` - YTD (Q1-Q2) because the cumulative effect of all actuals is
     being compared to the original budget.
   - `Evaluate year-end totals vs. the baseline budget` - Specify a Compare
     Shortcut of the FY2018 Budget.

## Run monthly reviews

Many organizations perform forecasts on a monthly frequency. Organizations that perform forecasts
on a quarterly frequency can benefit from a monthly review as soon as actuals are available. You can
do this by following the previous forecast creation steps, skipping tasks as appropriate, and then
not opening the plan.
