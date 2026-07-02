---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Compare Versions or Plans"
breadcrumb:
  - "Planning"
  - "Working with Plans"
source_path: "it-planning/planning/compare-versions-plans.html"
images:
  - "resources/images/it_planning_images/compver1.png"
  - "resources/images/it_planning_images/compver2.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Compare Versions or Plans

You can compare the financial data between two periods or versions of the same plan or
between two different plans. These comparisons surface differences across time periods and line
items to help you understand changes and variances.

## Period to Period Comparison

Note: Requires Expenses New View.

Enables comparing periods within the same plan—year‑over‑year, quarter‑over‑quarter, or
month‑over‑month, making it easier to analyze trends and changes over time.

To compare plan using Period to Period Comparison, follow the steps below:

1. Navigate to **Expenses > New View**.
2. Select the **Expenses tab** you want to compare.
3. From the **Period column**, open the **menu** and select **Add Comparison**.The **Add
   Comparison** dialog opens.
4. Select the **Period to Period** radio button.
5. Choose the comparison period based on where the comparison is invoked:
   1. **When invoked from the Month column**
      - **Single-year plan**: Select the comparison **month**.
      - **Multi-year plan**: Select the comparison **year** and the corresponding **month**
        within that year.
   2. **When invoked from the Quarter column**
      1. **Single-year plan**: Select the comparison **quarter**.
      2. **Multi-year plan**: Select the comparison **year** and the corresponding **quarter**
         within that year.
   3. **When invoked from the Year column**
      1. **Single-year plan**: The **Period to Period** option is not available.
      2. **Multi-year plan**: Select the comparison **year**.
6. Click **Compare** to run the comparison.
7. Review the comparison results in the table, which show **Total**, **Variance**, and
   **Variance %**, grouped by common attributes such as **Cost Object** and **Account**.
8. To remove the comparison, open the **period-level menu** from the **source column** and
   select **Remove Comparison**.

## Plan to Plan Comparison

Enables comparing periods or versions between two plans, making it easier to analyze differences
between different financials years and what-if scenarios.

## Comparison Alignment Method

When comparing plans, you can choose between two alignment methods. You must select one
when adding a comparison from the Expenses table or using Comparison Shortcuts.

1. Plan Start Year

   Aligns the plans based on their starting fiscal years.

   Example:
   - **Plan A** covers FY2019–2020
   - **Plan B** covers FY2020–2021
   - Using this method, **FY2019 of Plan A** is compared to **FY2020 of Plan B**.
2. **Matching Fiscal Year**

   Aligns the plans by comparing the **same fiscal year** across both
   plans.

   Example:
   - **Plan A** covers FY2019–2020
   - **Plan B** covers FY2020–2021
   - Using this method, it compares **FY2020 of Plan A** to **FY2020 of Plan
     B**.

## How to compare versions or plans

1. Open the plan you want to compare from the **Plan** menu.
2. In the Expenses table, hover over a **Month**, **Quarter**, or **Fiscal Year**
   column and open the **column header menu**, then select **Add Comparison...**
3. Choose the **version or plan** to compare against. *Note: versions are only
   available when viewing leaf Departments.*
4. Select the Alignment Method: **Plan Start Year** or **Matching Fiscal Year**.
5. *(Optional)* Enable **Include Quarters** or **Include Year** to bulk-add
   comparisons across multiple time periods.
6. Click **Compare**.
7. New **Total**, **Variance**, and **Variance %** columns will appear next to the
   selected time period to display the comparison results.
8. To adjust the comparison granularity, change the **table grouping** — by default,
   comparisons are shown by **Cost Object and Account**.

   Note: Legacy View supports
   comparison functionality for the Other and Summary tabs across all periods, and for the
   Labor tab only within the FY total columns. To add comparisons in Contracts, Assets,
   Labor, and Labor Activity across all periods, please use the New View.

## Comparison shortcuts

Comparison shortcuts allow you to quickly compare your current plan against up to four
other plans. Administrators can also choose to enable a default comparison plan for all
users. Users can turn comparisons on or off anytime from the Compare To menu.

## How to set comparison shortcuts

Note: Users with **ManagePlan** permission — such as Admins or Budget Process Owners — can
configure comparison shortcuts.

1. From the **Ellipsis menu**, select **Compare Shortcuts**.
2. In the **Manage Compare Shortcuts** window, choose the plans you want to compare
   against and select an Alignment Method for each.
3. Optionally, enable **Show by default** to auto-display the comparisons for all users.
4. Click **OK** to save your settings.

![image of comparing versions](../../../../../03-media/apptio-planning/resources/images/it_planning_images/compver1.png)

Once configured, users can toggle comparisons at any time from the **Compare To** menu.
Comparisons will automatically appear on all visible Quarter, Year, and YTD columns. Compare
shortcuts are configured per plan, meaning you can set different comparison plans for each
individual plan.

![image of comparing versions](../../../../../03-media/apptio-planning/resources/images/it_planning_images/compver2.png)
