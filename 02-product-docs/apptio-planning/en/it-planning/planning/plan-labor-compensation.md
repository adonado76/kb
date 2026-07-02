---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Labor Compensation Adjustments"
breadcrumb:
  - "Planning"
  - "Labor Planning"
source_path: "it-planning/planning/plan-labor-compensation.html"
images:
  - "resources/images/it_planning_images/comp3.png"
  - "resources/images/it_planning_images/comp4.png"
  - "resources/images/it_planning_images/comp5.png"
  - "resources/images/it_planning_images/newview.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Labor Compensation Adjustments

Labor Compensation Adjustments allow organizations to model compensation increases (or
decreases) over time within Apptio Planning. This feature provides a structured way to account
for planned salary adjustments such as merit increases, market adjustments, promotions, or
cost-of-living changes.

When enabled, users can define adjustment percentages and effective dates that automatically
update base compensation values for existing or planned headcount. Adjustments are applied
forward from the effective date and flow through to financial calculations, including fully
burdened labor costs and departmental allocations.

## Prerequisites

Before you can use this feature:

- **Labor Headcount** planning must be enabled in **Settings → Company Profile**.
- Budget Owners need the **View Sensitive Financials** and **View Sensitive
  Columns** permissions to see adjustment fields.

## Configure Compensation Adjustments

1. Go to **Settings → Company Profile → Labor Planning**
2. Toggle on **Variable Compensation Adjustments**.
3. **Define Default Compensation Cycles**
   1. Specify your organization’s default **Compensation Cycles**, typically aligned
      with merit or market increase schedules.
   2. Select the periods where compensation adjustments are allowed.
   3. These defaults can later be modified at the plan level.

   ![image of variable compensation adjustment cycle](../../../../../03-media/apptio-planning/resources/images/it_planning_images/comp3.png)
4. **Configure Per Plan**
   - Navigate to **Plan → Settings → Labor Compensation Adjustment**.
   - Select the **Compensation Cycle** button and review or adjust the cycles for the
     current plan.

   ![image of configuring plan](../../../../../03-media/apptio-planning/resources/images/it_planning_images/comp4.png)
5. **Define Default Adjustment Rates**
   - The **Labor Compensation Adjustment** table pulls in default rates from the
     **Labor Rates** reference data table.
   - For each Role combination (Role, Vendor, Location, Employee Type), specify a default
     adjustment percentage for each defined compensation cycle (e.g., 2% in March, 1% in
     September).
   - Optionally, export a template, update the adjustment percentages, and re-import it.

   ![image of default adjustment rates](../../../../../03-media/apptio-planning/resources/images/it_planning_images/comp5.png)
6. **Review Adjusted Rates**
   1. The **Adjusted Base Rate** field displays the new compensation amount after the
      adjustment takes effect.
   2. In the **New View**, the **Adjustment** field will appear for each labor line
      item, allowing you to apply or override rates directly in the Labor tab.
   3. Changes are automatically saved and reflected in the plan’s calculations.

## Permissions

You can control who can view or edit compensation adjustments:

- **ITPCompensationAdjustmentEdit** — Allows overriding default percentages for
  defined compensation cycles.
- **ITPCompensationAdjustmentAllPeriodsEdit** — Allows editing percentages across all
  periods.
- **canEditPlanSettings** — Required to modify the **Plan Settings** page.
- **canViewPlanSettings** — Required to view the **Plan Settings** page.
- By default, these permissions are granted to **Admin** and **Budget Process
  Owner** roles.
- If you want **Budget Owners** to manage compensation adjustments, grant them the
  appropriate permissions based on your governance model.

## How to Plan a Compensation Adjustment

You can model compensation changes directly in your labor plan—either using **New View**
for interactive, period-based adjustments or **Legacy View** for a simpler annual
adjustment model.

***In New View***

1. **Open the Plan**
   1. Select your plan and choose the appropriate **Department**.
   2. Navigate to **Planning → Expenses → Labor**.
2. **Open the Adjustments Drawer**
   1. In the Labor table, select the **Adjustment** button in the **Adjustments**
      column for the labor row you want to update.
   2. The **Adjustments drawer** displays default percentages if they were configured
      in the **Plan Settings → Labor Compensation Adjustment** table.
3. **Review and Modify Adjustments**
   1. You can override default percentages for specific periods if you have the required
      permissions.
   2. The drawer shows the **fully burdened labor cost by Account** for the selected
      labor line—these accounts align with your configured **Labor Allocation Rules**.
   3. Adjustments automatically update the total labor cost, allowing you to see the
      financial impact in real time.

![image adjustment review](../../../../../03-media/apptio-planning/resources/images/it_planning_images/newview.png)

Note: If Variable Labor Compensation Adjustments
are enabled, labor adjustments cannot be modified in the legacy view. If this feature is
enabled, the only way to restore labor adjustments in the legacy view is to disable the
feature in Company Profile and manually recreate the plan (this will remove item codes)..

***In Legacy View***

1. **Open the Plan**
   1. Select your plan and choose the appropriate **Department**.
   2. Navigate to **Planning → Expenses → Labor.**
2. **Enter Adjustment Details**
   1. **Adjustment Effective Date** – The date when the adjustment begins.
      1. If the plan spans multiple years, the adjustment compounds year-over-year from
         that date.
   2. **Adjustment %** – The rate of increase (positive) or decrease (negative).
3. **Review Results**
   1. The system applies the adjustment downstream for the remainder of the plan period.
   2. You can review the updated cost impact in the **Summary** tab, where the
      adjusted financial line items are reflected based on configured **Labor Allocation
      Rules**.

**Interaction with Plan-Level Time-Effective Allocation Rules**

When plan-level time-effective **Labor Allocation Rules** are configured, compensation
adjustments use the allocation rate that is effective for the corresponding period in the plan.

The **fully burdened cost** displayed in the **Adjustments** drawer reflects the
applicable time-effective allocation rate for each period, rather than the global default rate. This
ensures that compensation adjustments remain aligned with the allocation assumptions defined in the
plan.

For example, if a plan defines a benefit rate of **7% in Year 1** and **8% in Year
2**, a compensation adjustment applied in Year 2 will be calculated using the **8% benefit
rate**. As allocation rates change over time, compensation adjustments automatically use the rate
effective for the period in which the adjustment is applied.
