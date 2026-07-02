---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Analyze budget variance"
breadcrumb: []
source_path: "planning/analyze-budget-variance.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Analyze budget variance

The tasks below can only be performed by users assigned to the Admin or Budget Process
Owner roles. For additional information on roles, see Frontdoor permissions and roles.

Note: The Variance Drivers feature is currently only accessible to Admin users and must be enabled.
See [Edit the Company
Profile](edit-company-profile.htm "(Opens in a new tab or window)"). The following instructions describe expected functionality when the Variance Drivers
feature is made available to other user roles.

Effective variance analysis includes identifying drivers causing disparity between a specific
forecast and its actuals. Identifying these drivers helps financial analysts interpret variances and
provokes questions that assist in better managing company resources.

Financial analysts, including those assigned to Budget Process Owner or Cost Center Owner roles,
can identify variance that meets a defined threshold, and then apply both a selected driver and a
free-form explanation to that variance. Variance analysis requires loading actuals for forecast
planning. See [Budget
planning and forecasting](budget-planning-forecasting.htm "(Opens in a new tab or window)").

The Variance Drivers feature offers the following advantages over spreadsheets and other
tools:

- X-ray the entire budget. Analyze every Cost Center and account.
- Use thresholds to focus on the variances that matter most.
- Engage budget owners to investigate and explain variances.
- Track the status of variance analysis from a birds-eye view.
- Analyze variance drivers with powerful reporting.

## Configure Variance Drivers

Complete the following tasks to enable the Dashboard and Variance Drivers feature, and populate
the required reference data dimensions.

1. On the Apptio planning menu, click the Settings button (![](../../resources/images/it%20planning_images/icon_gear.png)), then click Company
   Profile.
2. Select the Enable Dashboard and Variance Drivers checkbox.
3. Click Save and Exit. Budget Process Owners and Admins can now see the Dashboard
   view, and all users can now access the Variance Analysis page.
4. Define your Account Category dimensions to group your detailed general ledger accounts
   into a manageable list for variance analysis. See [Manage Account Category reference
   data](manage-financial-dimensions.htm#AcctCatRD).

   Note: You will need to update your Account reference data with the new Account Category Code. You
   cannot use the account category name when loading into the Accounts reference data.
5. Define your Variance Drivers' dimensions to create a configurable list of common variance
   drivers for your users. See [Manage
   Variance Drivers reference data](manage-financial-dimensions.htm#VDRD).
6. Update your baseline plans with the new reference data dimensions. See [Force a plan to use updated reference
   data](force-plan-use.htm "(Opens in a new tab or window)").

## Create and run a variance analysis

The Variance Drivers feature compares a new forecast plan to a baseline plan (either a budget or
forecast) and flags all variances over the threshold you set. Cost Center Owners provide variance
drivers for all flagged variances. Then, those Cost Center Owners (or other users assigned by the
Admin) provide variance drivers and explanations for all identified variances.

## Create the variance analysis

Variance drivers are used on forecasts in the New state.

1. Open a forecast. See [Open a
   plan or a forecast](open-plan-forecast.htm "(Opens in a new tab or window)").

   Note: When using a forecast for variance analysis, you cannot start the forecast in the first month
   of your fiscal year.
2. In the Plan sections menu, select All Plan Sections.
3. On the Component menu, select Planning. See [Navigate in Apptio planning
   applications](navigate-apptio-planning.htm "(Opens in a new tab or window)")..
4. Select ![](../../resources/images/icons/3-dots_18x20.png) > Variance
   Analysis.

   Tip: If you see "Variance analysis has not been created for this Forecast plan," ensure
   the variance drivers' reference data has been correctly created and updated for the plan. See [Manage Financial reference
   data](manage-financial-dimensions.htm "(Opens in a new tab or window)").
5. Enter your information in the Variance Analysis window. Options include:
   - Comparison Plan - Select a plan (like the finalized budget or previous forecast) to
     compare to the forecast for variance analysis. The comparison plan must be in the Final state. See
     [Finalize a plan or
     forecast](finalize-plan-forecast.htm "(Opens in a new tab or window)").
   - Variance Threshold - Enter both your financial and percentage values (both values are
     required for variance analysis). The Variance Drivers feature uses an Amount and Percentage approach
     to identifying variances. The financial value is an absolute value that applies to both favorable
     and unfavorable variance values.
   - Comparison Period - Select your time range for variance analysis. Only historical periods
     containing actuals can be analyzed.
   - Account Categories - All account categories are selected and cannot be changed.
6. Select Create.
7. On the Variance Analysis page, a red flag in the Drivers column indicates a variance is
   over the defined threshold. If a group is indicated, one or more items within that group are
   flagged:

   ![](../../resources/planning_images/itp_variance-analysis.png)
8. To adjust the thresholds (if, for example, too many or too few items are flagged), click
   Variance Analysis at the top of the page to repeat the process.

   Note: You will be warned that running variance analysis again will delete the prior variance
   analysis, and any explanations previously provided.
9. All active plans in Open and New states will be available in the Compare To Plan dropdown when
   configuring variance analysis. However, the Cost Center Owners will not have access to view variance
   analysis when comparing to a plan in the New state.

   ![](../../resources/images/it_planning_images/3.86a.jpg)

   From 3.88
   release, the "AND/OR" operation type is added in variance configurations to choose
   between:

   AND – Variance must meet both absolute value and percentage thresholds.

   OR –
   Variance must meet either the absolute value or percentage threshold.

   ![](../../resources/images/it_planning_images/3.88-3.jpg)

## Assign the variance drivers

Once you have created your variance analysis, you're ready to assign variance drivers, and
provide an associated explanation for each. You can do this when a forecast is in the New or
Open state (when it is available to all users).

1. On the Component menu, select Planning. See [Navigate in Apptio planning
   applications](navigate-apptio-planning.htm "(Opens in a new tab or window)"). > Variance Analysis.
2. Select a single Cost Object and Account Category with a flagged variance and click
   the flag to open the Variance Breakdown window:

   ![](../../resources/planning_images/itp_variance-analysis_breakdown.png)
3. This screen provides reporting tools to discover variance drivers and includes the following:
   - Summary tab - Drill in to get detailed information about the variance driver.
   - Actuals tab - View a table of actuals by month, as well as the details of the spend
     causing the variance.

   Variance drivers are displayed on the left side of the page. One or more variance drivers
   and optional details explaining their variance amount are displayed. Once an entire variance has
   been explained, the flag turns green.

Tip: Click the Close (X) button on the upper-right corner of the screen to close the
variance explanations window.

## Open the plan

Click Open Plan at the top of the page to open the plan and allow users access to the
forecast plan and Variance Analysis pages.

## Review the results

To display a summary view of variance drivers, navigate to Planning > Dashboard. On the
Dashboard, the IT Spend Variances section displays a rollup of the variance analysis by driver and
provides the option to save the variance analysis drivers information to a .csv file.

On the Dashboard, click a group (block) in the tree map chart to view the variance drivers for a
single department.

Note: When comparing to Forecast Periods, Admin users can select "Update Variance Analysis" to
refresh variance calculations, ensuring variance amounts reflect the latest forecast updates. This
option is available in the "..." menu on the Variance Analysis page.

![](../../resources/images/it_planning_images/3.86b.jpg)

## Enhancement in Planning 3.64 release

Prior to this release, when the user configured the variance threshold, and the expense was
present either in the Actuals or the Budget, the variance was not flagged in the variance analysis
report

![](../../resources/images/it%20planning_images/va-before.png)

However, from 3.64 release, the variance should be flagged if the expenses are beyond the
configured threshold in both the following scenarios:

- The expense is present in the Actuals but absent in the Budget.
- The expense is absent in the Actuals but present in the Budget.

![](../../resources/images/it%20planning_images/va-after.png)

On selecting the variance driver, both the Summary Chart and Actuals tab will show relevant data
for the user to enter the variance explanation.

![](../../resources/images/it%20planning_images/va-unexplained.png)

## Enhancement in Planning 3.68 release

Prior to this release, when the user configures the variance analysis with the plan that has
different start year than the compared Actual period year, the variance comparisons were reported by
aligning the comparison period from the start year of the comparison plan.

In the example below the variance is configured in FY2024 February Forecast plan, the comparison
plan here is FY2023 Budget 2Yr with years 2023 – 2024. The comparison period in the variance
analysis is Jan FY24.

The comparison amount reported in variance analysis for Apps – Back Office cost object is
$1,813,375.

![](../../resources/images/it%20planning_images/va-b4align.png)

In the plan FY2023 Budget 2Yr, this value is coming from Jan FY23. That is due to alignment using
plan start year.

![](../../resources/images/it%20planning_images/va-2.png)

But, it is now possible to align the comparison plan FY2023 Budget 2Yr by fiscal years. Select
the Align by Matching Fiscal Year checkbox to align comparison plan by matching fiscal year.
The info icon next to checkbox describes the expected behavior. To update variance analysis select
the Replace the existing variance analysis with the new settings checkbox and then click the
Update button.

![](../../resources/images/it%20planning_images/va-aligh.png)

Variance analysis gets updated with the comparison values from Jan FY24 period of the comparison
plan.

![](../../resources/images/it%20planning_images/va-afteralign.png)

You can also use option Align by Matching Fiscal Year during the new variance
configuration as well.
