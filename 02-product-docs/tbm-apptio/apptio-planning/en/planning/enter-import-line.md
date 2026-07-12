---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Enter or import line-item data"
breadcrumb: []
source_path: "planning/enter-import-line.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Enter or import line-item data

After a budget plan or forecast has been opened, budget owners receive an email
notification and can begin to enter line-item data and submit plans. Department Owners, Service
Owners, and Project Owners can enter or import their line-item data and submit their
plans.

For more information, see [Open a plan or a
forecast](open-plan-forecast.html "After you create a budget plan or forecast, optionally adjust the baseline values, set the targets, and open the plan so that the budget owners can edit line items. Budget owners cannot see a plan when it is in the New state. When you open a plan, an email notification is sent to budget owners and all users who have the Edit & Submit permission associated with the Cost Objects in that plan.").

## Manually enter line-item data

1. In the plan menus at the top right, select a plan, a Cost Object category, and a cost object or
   cost object group. For more information, see [Learn more about navigating in Planning](navigate-apptio-planning.html).

   Note: Cost Center Owners can only edit
   their assigned Cost Centers. For more information, see [Manage
   Cost Object Permissions reference data](manage-cost-object.html).
2. In the plan menus at the top right, select a plan, a Cost Object category, and a cost object or
   cost object group.
3. Select the required view from the navigation menu under Planning.
4. If your view includes tabs, select a tab.
5. Enter or edit asset details as needed.
6. Submit a plan or forecast. For more information, see [Learn more about submitting a plan or forecast](submit-plan-forecast.html "After you enter your plan or forecast information, you can submit it for approval. The budget owner can submit their plan from the Status or the Expenses page.").

Tip:

- To speed up data entry and review, you can customize the table layout. For more information, see
  [Customize, save, and share table layouts](customize-save-share.html).
- When entering data in a table, you can enter a quarterly or annual value and that amount will be
  proportionally distributed between months.
- Speed up data entry by typing `K` (for thousands) or `M` (for
  millions).
- You can add custom attributes to the table which can help capture supplemental information to
  enhance analysis and reporting. For more information, see [Add and
  manage custom attributes of dimensions](manage_schema.html).

## Import and publish line item tables

Admins or Budget Process Owners can import line-item details for the entire organization, and
budget owners can do so for their specific Cost Objects. When you import line-item details, you can
either replace or append to existing line-item details in your plan, based on the time period.

There are two available Import Types:

Replace All Data
:   Removes existing lines and replaces them with lines from the imported file. A new Line Item Code
    is generated for each imported line.

Update Data
:   Updates existing lines and adds new lines.

1. In the plan menus at the top right, select a plan, a Cost Object category, and a cost object or
   cost object group. For more information, see [Learn more about navigating in Planning](navigate-apptio-planning.html).
2. Select the required view from the navigation menu under Planning.
3. If your view includes tabs, select a tab.
4. Click Edit at the top of the page.
5. At the upper right of the page, click Actions and select the
   Import option.
6. Set your import options and click Import to import the .csv file
   data.
7. Follow the on-screen information to complete the data import process. Examine and verify your
   imported data.
8. If your data looks correct and you want to make it available in plans, select
   Publish.
9. If you see problems with your data and need to troubleshoot before publishing, select
   Revert.

Note: When importing a file at a group level into a plan that is in the Open state,
the file only modifies cost objects that are contained in the line item table.

Tip: To download and populate a layout template for import, see [Export and populate line item tables or layouts](export-populate-line.html).
