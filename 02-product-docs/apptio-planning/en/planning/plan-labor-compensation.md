---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Plan for labor compensation adjustments"
breadcrumb: []
source_path: "planning/plan-labor-compensation.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Plan for labor compensation adjustments

Budget Process Owners or users with owner permissions for a Cost Object can account for
planned adjustments to labor compensation rates. This can be done for current or planned labor. You
can specify a percentage change to base compensation per labor resource, and the date at which the
change will become effective.

Before begin labor compensation planning, ensure you enable the labor planning features. For more
information, see [Edit the Company
Profile](edit-company-profile.html)

**Plan for a labor compensation adjustment**

1. In the plan menus at the top right, select a plan, a Cost Object category, and a cost object or
   cost object group.

   [Learn more about navigating in Planning](navigate-apptio-planning.html#Toolbar).

   Note: Cost Center Owners can only edit their assigned Cost Centers. For more information, see [Manage Cost Object Permissions reference
   data](manage-cost-object.html).
2. Navigate to
   Planning > Expenses.
3. Select the Labor tab.
4. Select Existing to plan labor compensation adjustments for current
   labor.
5. Select Planned to plan labor compensation adjustments for planned labor.
   - In the Adjustment Effective Date cell, enter the date to begin the
     adjustment. Note that when working with multi-year plans, labor compensation adjustments will apply
     from the Adjustment Effective Date through the duration of the plan.
   - In the Adjustment % cell, enter an adjustment percentage value. A
     positive value will result in a compensation increase and a negative value will result in a
     compensation decrease.

Tip: When working with multi-year plans, current or planned labor costs with no end
date, or an end date beyond the plan, dates will extend throughout the plan. Labor compensation
adjustments are annually recurring. For example, a 3% increase effective as of April 1 in the
current year would result in a 3% year-over-year increase. For more information, see [Plan for multiple years](plan-multiple-years.html).

## Setting up Variable Labor Compensation

Note: This feature can be seen only in New Expenses View. The users must have permission to **View
Sensitive Financials** and **View Sensitive Columns** to view the **Adjustment** field.

1. Navigate to **Company Profile** and enable the **Variable Labor Compensation Adjustments**
   option.

   ![](../../resources/images/it_planning_images/vca1.jpg)
2. Select the periods to establish your organization’s default Compensation Cycles. These settings
   can be adjusted for each plan individually.

   ![](../../resources/images/it_planning_images/vca-adjcycl.jpg)

   A
   Compensation Cycle Period refers to a defined time period which labor compensation adjustments, such
   as merit increases, are planned and applied within an organization. These periods are typically
   aligned with an organization’s compensation review schedule to ensure consistent and predictable
   updates to wages or salaries.

   Once enabled, any newly created plan will include the Variable
   Labor Compensation Adjustments feature.

   Note: If a plan is created from a baseline, the new plan
   will inherit either the legacy compensation adjustment model or the variable labor compensation
   model, depending on what is used in the baseline plan.
3. Navigate to **Plan** > **Settings**.

   ![](../../resources/images/it_planning_images/vca-compadju.jpg)
4. Select the **Compensation Cycle** button to see the default periods configured in the [Company Profile](https://help.apptio.com/en-us/it-planning/planning/edit-company-profile.htm "(Opens in a new tab or window)") settings.

   ![](../../resources/images/it_planning_images/vca-com-cycle.jpg)
5. You can update the Compensation Cycles to add or remove periods. Only users with appropriate
   permissions can edit/view the Plan Settings. To know more, see [User Permissions.](https://help.apptio.com/en-us/it-planning/planning/bp-handling-labor-compensation.htm "(Opens in a new tab or window)")
6. In Plan Settings, set the compensation adjustment percentage for each labor rate
   rule.

   **NOTICE**: The Default Adjustment Rate table is driven by the Labor Rates configured in
   Reference Data.

   ![](../../resources/images/it_planning_images/vca-set-percentage.jpg)
7. Navigate to **Expenses** > **Labor** tab, and select New view toggle.

   ![](../../resources/images/it_planning_images/vca-adj-main.jpg)
8. Select the **Adjustment** for a labor line item to view or update the compensation
   adjustments.

   ![](../../resources/images/it_planning_images/vca-final.jpg)

Note:

- Users must have permission to **View Sensitive Financials** and **View Sensitive Columns**
  to view generated labor financial line items.
- Users with the *ITPCompensationAdjustmentEdit* permission can override the default
  adjustment percentages for the defined Compensation Cycle periods.
- Users with the *ITPCompensationAdjustmentAllPeriodsEdit* permission can edit the adjustment
  percentages for all periods within the plan.
- If Variable Labor Compensation Adjustments are enabled, labor adjustments cannot be modified in
  the legacy view.
