---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Enter financial details and adjust baseline values"
breadcrumb: []
source_path: "planning/enter-financial-details.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Enter financial details and adjust baseline values

![](../../resources/images/it%20planning_images/icon_video.png):

Watch this video from Apptio Education Services: [Editing the Expenses
View](https://community.apptio.com/videos/1618 "(Opens in a new tab or window)").

Or see all [Apptio planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)").

Financials are captured on the Expenses page, Other tab. This tab allows budget owners to capture
OpEx and CapEx information from the general ledger that was not captured in the Contracts, Labor, or
Assets tabs. This tab allows you to view all other expenses that need to be captured by your
organization, and to forecast operational and capital expenditures for your departments, and if
enabled, services.

## Enter and display financial details

1. In the plan menus at the top right, select a plan, a Cost Object category, and a cost object or
   cost object group.

   [Learn more about
   navigating in Planning](navigate-apptio-planning.htm#Toolbar)
2. Navigate to Planning > Expenses.
3. Select the Other tab.
4. Enter or edit financial details as needed. The following columns are available:
   - Cost Center - Displays the department's corresponding Cost Center.
   - Account - Specifies the code for the general ledger account that will incur the
     cost.
   - Account Expense - Classifies if the account is used as an operational or capital
     expenditure. The value is automatically populated based on the account's definition within reference
     data (see [Manage
     Financial Dimensions reference data).](manage-financial-dimensions.htm "(Opens in a new tab or window)")
   - Vendor - Displays the available options for this dimension (see [Manage Financial Dimensions
     reference data).](manage-financial-dimensions.htm "(Opens in a new tab or window)")
   - Location - Displays the available options for this dimension (see [Manage Financial Dimensions
     reference data).](manage-financial-dimensions.htm "(Opens in a new tab or window)")
   - Description - Displays a summary of the expense.
   - Comment - Displays notes.
   - Currency - Visible only if the support for multiple currencies is enabled (see [Support for multiple
     currencies)](support-multiple-currencies.htm "(Opens in a new tab or window)").
   - Time periods - (months, quarters, and years). Displays the expected spend for each time
     period for that expense item.

## Adjust baseline values

After creating a plan or forecast based on an historical baseline plan, a Budget Process Owner
may need to adjust the plan. Adjustments can be global in scope or limited to specific Cost
Centers.

1. Using the previous instructions, open the Expenses page, Other tab.
2. Select Actions > Adjust Amounts.
3. Select an Adjustment Type:
   - Percentage - A percent of the original value.
   - Absolute - A specific currency. This option is disabled if support for multiple
     currencies is enabled (see [Support for multiple currencies)](support-multiple-currencies.htm "(Opens in a new tab or window)").
4. Enter a value in the Adjustment Amount box:
   - If you selected Percentage as the Adjustment Type, then enter a percentage value
     as a whole number. For example, enter 10 for a 10% adjustment. To enter a negative adjustment, enter
     a negative value. For example, -5 will result in a -5% adjustment.
   - If you selected Absolute as the Adjustment Type, then enter a specific currency
     amount.
5. Click the Apply To list and select a set of line items (Cost Object and Account) to
   adjust. Apply the adjustment to one Cost Object, a group of Cost Objects, or all of the Cost Objects
   (for example, All Departments). The same applies for selecting Accounts to adjust.
6. Select a start and end period in the Period Range.
7. Select Adjust.
   - If needed, you can adjust individual accounts manually by going to the child Cost Object and
     editing the monthly amount for the desired account.
   - To adjust a plan, the plan must be in the New state.
   - There is no undo for this action.
