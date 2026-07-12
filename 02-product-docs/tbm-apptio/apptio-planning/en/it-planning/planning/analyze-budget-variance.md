---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Variance Analysis Overview"
breadcrumb:
  - "Planning"
  - "Variance Analysis"
source_path: "it-planning/planning/analyze-budget-variance.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Variance Analysis Overview

The Variance Analysis feature helps you compare a current forecast plan against a
baseline (budget or previous forecast), identify significant differences, and build a commentary
trail that explains the drivers behind variances.

## Key Benefits

- Analyze variances by cost center, account, or department at scale.
- Flag only meaningful variances using defined thresholds to focus effort.
- Assign variance drivers and commentary to build audit-ready explanation trails.
- Export commentary for integration with reporting tools.

## Configure Variance Analysis

Note: Admin or Budget Process Owner roles are required to configure Variance Analysis.

Step 1: Enable the Feature

1. Go to **Settings** (Gear icon) **→ Company Profile**
2. Enable **Dashboard and Variance Drivers**

Step 2: Define Variance Drivers

1. Go to **Configuration → Reference Data → Variance Driver**
2. Upload a list of variance driver values (e.g., *project timing*, *accounting
   timing*, *unplanned spend*)
3. **Publish** the changes

Step 3: Define Account Categories

1. Go to **Configuration → Reference Data → Account Category**
2. Upload a list of **Account Categories** to group GL accounts into high-level
   groupings
3. Note: Variance Analysis is performed at the Account Category level
4. **Publish** the changes

Step 4: Map Accounts to Categories

1. Go to **Configuration → Reference Data → Accounts**
2. In the **Category** column, map each **GL Account** to an **Account Category
   Code**
3. Import the updated Accounts table and **publish** the changes

Step 5: Configure Variance Analysis for the Plan

1. Open your plan and go to **Variance Analysis** from the left navigation
2. Click the **Ellipses menu** → **Configure Variance Analysis**
3. In the modal, configure the settings:

   |  |  |
   | --- | --- |
   | **Field** | **Description** |
   | Compare To Plan | Select the comparison plan. All non-archived plans will be available for selection.    Note: Plans in the NEW state will not be visible to Cost Center Owners. |
   | Comparison Period | Choose the time period (e.g., last month, last quarter, full year or custom) |
   | Plan Alignment | Align plans by **Matching Fiscal Year** or **Plan Start Year** |
   | Variance Threshold $ | Minimum **currency difference** requiring explanation |
   | Operator | Choose AND or OR to determine how the currency and percentage variance thresholds should be applied:    AND — both thresholds must be met    OR — meeting either threshold is sufficient |
   | Variance Threshold % | Minimum **percentage variance** requiring explanation |

Step 6: Generate the Analysis

- Click **Preview** to review the results
- Click **Create** to generate the variance analysis

Once crated, variances exceeding the thresholds will be flagged for explanation and
commentary.

## Running a Variance Analysis

Note: Variance Analysis is only available for Forecast-type plans.

1. Open your **forecast plan**.
2. Go to **Plan → Variance Analysis** from the left navigation.
3. In the table, look for **red variance flags** — these indicate Account Categories
   where the variance exceeds the defined threshold.
4. Select a flagged **Account Category** for a specific Department to drill into
   variance details.
5. Use the **Summary** and **Actuals** tabs to review the variance as a waterfall
   chart and transactions details.
6. Assign one or more **Variance Drivers** and enter a free-form explanation for the
   variance.
7. Click the **X** to exit the variance detail view.
8. Once all variances have assigned drivers and explanations, the **status flag will turn
   green**.

## Edit Variance Analysis Configuration

Note: Admin or Budget Process Owner roles are required to edit Variance Analysis
settings.

**Update Thresholds or Comparison Settings**

1. Click the **Ellipses menu** in the Variance Analysis page
2. Select **Configure Variance Analysis**
3. Adjust the settings (plan, alignment, thresholds, etc.)
4. Click **Update** to apply changes

Important: Updating the configuration willremove all existing variance
explanations.

**Refresh Variances for Active Forecasts**

If you are comparing against forecast periods (e.g., full-year comparison between two
plans), you may need to refresh variance values when plan data changes.

1. Click the **Ellipses menu**
2. Select **Update Variance Analysis**
3. The dialog will display which line items need to be updated along with the last update
   date
4. Click **Update** to recalculate the variance table using the latest forecast
   values.

Important: Updating the analysis may remove variance drivers and
explanations if those variances have changed.

## Export & Reporting

- From the **Actions** menu on the Variance Analysis page you can select **Export
  Variance Commentary** to export to csv. The export includes all drivers, commentary,
  and variance records.
- On the **Dashboard**, navigate to *Spend Variances* to view a treemap and
  breakdown by drivers and departments.
