---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Manage contracts"
breadcrumb: []
source_path: "planning/manage-contracts.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Manage contracts

Use Apptio planning applications to help your organization accurately account for the
financial impact of contracts on budgets.

![](../../resources/images/it%20planning_images/icon_video.png)

Watch this video from Apptio
Education Services: [Editing the Contracts Plan](https://community.apptio.com/videos/1637 "(Opens in a new tab or window)").

Or see all [Apptio planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)").

Apptio
planning applications include the following contract planning features:

- Budget Process Owners can define contract types to align contracts with general ledger account
  codes. Contract type names can be set by Cost Center Owners to relate to the context of their
  budgets, while general ledger account codes come from your financial organization. You can define
  multiple contract types that all map to the same general ledger account code.
- Budget owners can record the contract details including amortization treatment and see the
  resulting charges in the OpEx budget.
- For contracts that might be extended in the current plan year, budget owners can see financial
  discretionary spend and how it impacts their budgets.
- A value-added tax (VAT), also known as a goods and services tax, can also be calculated for
  contracts. The VAT is based on the contract line-item Location value in
  reference data (see [Manage VAT Rate reference data](https://help.apptio.com/en-us/it-planning/planning/manage-contract-configuration.htm#Manage "(Opens in a new tab or window)")).
- Model the long-term budget impact of contracts (see [Plan for multiple years](https://help.apptio.com/en-us/it-planning/planning/plan-multiple-years.htm "(Opens in a new tab or window)")).
- Budget owners can add or review contract details in their budget. When they do, they assign the
  Cost Object to a contract type, which allocates the contract to the correct general ledger account
  code as specified by the Budget Process Owner. See [Manage Contract reference data](https://help.apptio.com/en-us/it-planning/planning/manage-contract-configuration.htm "(Opens in a new tab or window)").

## Manage contracts

Enable the Contracts feature. See [Edit the Company Profile](edit-company-profile.dita "(Opens in a new tab or window)").

## Create a contract plan

1. In the plan menus at the top right, select a plan, a Cost Object category, and a cost object or
   cost object group.

   [Learn more about
   navigating in Planning](navigate-apptio-planning.html)

   Note: Cost Center Owners can only edit their assigned Cost Centers.
   See [Manage Cost Object Permissions
   reference data](manage-cost-object.dita "(Opens in a new tab or window)").
2. Navigate to Planning > Expenses.
3. Select the Contracts tab.
4. Enter or edit asset details as needed. Options include:
   - Cost Object - The unique identifier per Cost Object, organized across columns that correspond to
     each Cost Object type (Departments, Services, or Projects). Cost Object reference data may be
     organized into parent and child hierarchical relationships between Departments, Services, and
     Projects.
   - Contract Type - The unique agreement between your organization and an external party.
   - Account - Specifies the general ledger account code to which you want to charge labor costs
     derived from this rule. The available options are provided by the Accounts reference data (see [Manage Financial Dimensions reference data)](https://help.apptio.com/en-us/it-planning/planning/manage-financial-dimensions.htm "(Opens in a new tab or window)").
   - Vendor - Specifies the vendor associated with the contract. Later you can review contracts per
     vendor.
   - Location - Displays available options for this dimension (provided by the Location reference
     data).
   - Description - Summarize the nature of the contract.
   - Comment - Capture notes.
   - Currency - Visible only if multiple currency support has been enabled (see [Support for multiple currencies](https://help.apptio.com/en-us/it-planning/planning/support-multiple-currencies.htm "(Opens in a new tab or window)")).
   - Amount - Enter the full contract amount. Even if the contract duration started prior to or ended
     after the current plan year, enter the full amount. Note that contract amounts will change when you
     import actuals and update the contract amount. However, financials generated for forecast periods on
     the Summary page will not change (see [Import and publish actuals](https://help.apptio.com/en-us/it-planning/planning/import-publish-actuals.htm "(Opens in a new tab or window)")).
   - Start Date - Enter the first month the contract accrues expenses, even if the date precedes the
     current plan year. The contract expense is accrued to the full month, regardless of the start
     day.
   - End Date - Enter the last month the contract accrues expenses, even if it is after the current
     plan year.
   - Duration - The calculated span of time, in full months, between the contract start date and end
     dates. If you choose to amortize, the contract amount is amortized across this number of
     months.
   - Extend - If the contract can extend beyond the end date of the current plan year, select this
     checkbox. You can then specify an extension adjustment percentage and see the financial impact of
     extending the contract per month. This allows you to model contract extensions and see the financial
     impact both by contract and across your budget. The Extension Total KPI at the top of the page sums
     the amounts of all extended contracts. Since this amount is not yet committed to your budget, it may
     be considered discretionary spend for contracts. To extend contract with compounding extension
     adjustment with flexibility to define different extension adjustment percentage, refer [Variable Contract Extension Adjustment](https://help.apptio.com/en-us/it-planning/planning/vrbl-cntc-ext-adj.htm "(Opens in a new tab or window)").
   - Amortize - Select this checkbox if the contract expense should be amortized per month. Clear
     this checkbox if you want the full amount of the contract to accrue on the contract's start date
     (see [Manage Contract reference data](https://help.apptio.com/en-us/it-planning/planning/manage-contract-configuration.htm "(Opens in a new tab or window)")). You can display the
     amortization method column in the contract line items table (see [Customize, save, and share table layouts](https://help.apptio.com/en-us/it-planning/planning/customize-save-share.htm "(Opens in a new tab or window)")).
   - Extension Adjustment - If the contract may extend, enter a percentage adjustment for the cost of
     the extension. 5. Submit your changes. 6. Capture supplemental information about contracts by adding
     custom attributes to contract dimensions. See Add and manage custom attributes of reference data
     (dimensions and line-item tables). This allows you to enhance your analysis and reporting
     capabilities.
5. Submit your changes.
6. Capture supplemental information about contracts by adding custom attributes to contract
   dimensions. See [Add and manage custom
   attributes of reference data (dimensions and line-item tables)](manage_schema.dita "(Opens in a new tab or window)"). This allows you to enhance
   your analysis and reporting capabilities.

## View delegated project costs

If Project Financial Planning Project Financial Planningis enabled, Project Owners can delegate
project costs to department and service owners. All of these owners can show or hide delegated costs
from their financials. See [Delegate project costs](pfp/delegate-project-costs.dita "(Opens in a new tab or window)").
