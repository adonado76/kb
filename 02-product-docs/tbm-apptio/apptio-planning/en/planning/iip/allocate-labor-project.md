---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Allocate Labor to Project using Role or Name"
breadcrumb: []
source_path: "planning/iip/allocate-labor-project.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Allocate Labor to Project using Role or Name

Integrated Investment Planning allows project owners and cost center owners to allocate
resources to a project as role-based allocation or name-based allocation.

Labor allocation to project is done from Planning > Expenses > Labor Activity view.

1. Select Project for labor activity allocation.

   The Cost Center dropdown menu shows cost centers
   applicable to the selected project.
2. Select a Cost Center.

   Typically, this Cost Center is the funding source for the
   project.

   Cost Center Cost Object is filled automatically as configured in the reference
   data.
3. Select a Resource Cost Center.

   This is the Cost Center which provides labor resources to work
   on the project.
4. To allocate resources to a project as role based, select Project Labor Role to choose which
   resource role you want.

   For example, there is the Developer project labor role and that is the
   role you have allocated, which means any resource of that role can be assigned to work on the
   project.
5. To allocate resources to a project as name based or specific labor resource from the Resource
   Cost Center, select specific resource from the Resource dropdown menu.

   Resource menu automatically
   filters to only resources from the selected Resource Cost Center.
6. Select Activity Type.

   Setting activity on the line sets the Charge Cost Center Account and
   Cross Charge Account based on the reference data configuration for Labor Activity Account.

   To
   learn more, see [Configure
   cross-charge](configure-cross-charge.htm "(Opens in a new tab or window)")
7. Select Hours or FTEs from the FTE/Hours toggle button above the Labor Activity
   Expenses table. Enter the allocated labor either using FTE unit or Hours unit as per the
   selected toggle.Note: Data imported into this tab will honor the selected toggle. Ensure the
   alignment between that the data available in CSV and the selected toggle (FTEs/Hours).
8. Data entered as FTE will be converted to Hours using the Working Calendar for the allocated
   resource.

To learn more about configuring working calendar, see [Configure a working calendar](../configure-working-days.htm "(Opens in a new tab or window)").

To learn more about using calendars in labor planning, see [Labor Allocation using Working
Day Calendar.](planning-labor-allocation.htm "(Opens in a new tab or window)")

Project labor activity expenses are generated on the Expenses > Summary view.

## Resource Allocation for Submitted Resource Cost Center

Resource allocation is not allowed when a Resource Cost Center is locked or submitted.

The expected behavior for the Expenses > Classic/Old View and Expenses > New
View when selecting a Resource Cost Center that is in locked or submitted state is explained
below.

Resource Cost Center "Apps-Back Office" is in submitted/locked state and resource cost center
"Apps-Line of Business" is not submitted.

Scenario 1: Remove the resource cost center that is submitted/locked on the Labor Activity
line.

## Expenses > Classic/Old View

From Expenses > Labor Activity tab, change the resource cost center from "Apps-Back
Office" to "Apps-Line of Business". The line item is highlighted in red and the error message
appears as shown.

![](../../../resources/images/it%20planning_images/layout-err_1363x582.png)

## Expenses > New View

Select the Resource Cost Center dropdown. You can see the indicator and information that the Cost
Center is locked.

![](../../../resources/images/it%20planning_images/layout-new-view_1367x589.png)

If you still choose the locked Cost Center, a validation error message appears as shown:

![](../../../resources/images/it%20planning_images/layout-new-view-1_1367x566.png)

Scenario 2: Assign the resource cost center that is submitted/locked on the Labor Activity
line.

## Expenses > Classic/Old View

From Expenses > Labor Activity tab, change the resource cost center from "Apps-Line
of Business" to "Apps-Back Office" to . The validation error message appears as shown:

![](../../../resources/images/it%20planning_images/layout-new-view-3_1382x459.png)

## Expenses > New View

From Expenses > Labor Activity tab, change the resource cost center from "Apps-Line
of Business" to "Apps-Back Office" to . The validation error message appears as shown:

![](../../../resources/images/it%20planning_images/layout-new-view-2_1373x470.png)

In all the above scenarios, the change will not be saved.
