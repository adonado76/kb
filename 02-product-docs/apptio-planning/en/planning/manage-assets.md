---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Manage assets"
breadcrumb: []
source_path: "planning/manage-assets.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Manage assets

Use Apptio planning applications to assist in accounting for asset purchase and
depreciation costs.

![](../../resources/images/it%20planning_images/icon_video.png)

Watch this video from Apptio Education Services: [Editing the Assets
Plan](https://community.apptio.com/videos/1632 "(Opens in a new tab or window)").

Or see all [Apptio planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)").

Asset
financial specialists working as or with a Budget Process Owner can define rules per asset class
that control how to account for a current asset. This can include CapEx purchase and OpEx
depreciation details that align with your financial reporting practices and accounting rules. Budget
owners can see how assets impact their OpEx and CapEx budgets. They can assign the asset to asset
classes and set up rules for those classes to apply the correct financial accounting treatment to
the asset purchase price and depreciation. This way, they can stay focused on assets in their budget
context.

Tip:

You can model the long-term budget impact of asset depreciation when [planning for multiple years](plan-multiple-years.dita "(Opens in a new tab or window)").

## Configure assets

1. Enable Assets. See [Edit the
   Company Profile](edit-company-profile.dita "(Opens in a new tab or window)").
2. Manage Asset reference data. See [Manage Asset Configuration reference data](manage-asset-configuration.dita "(Opens in a new tab or window)").

## Create an asset plan

1. In the plan menus at the top right, select a plan, a Cost Object category, and a cost object or
   cost object group.

   [Learn more about
   navigating in Planning](navigate-apptio-planning.html)
2. Navigate to Planning > Expenses.
3. Select the Assets tab.
4. Select Existing for compensation adjustments for current assets.
5. Select Planned for labor compensation adjustments for planned assets.
6. Select All for consolidated adjustments of both planned and existing assets in a single unified
   view. The All tab is displayed only in the [New View](enable-apex-line-item-table.html).
7. Edit or enter details in cells. Columns include the following:
   - Quantity - A number amount for assets measured in multiple units.
   - Currency - Visible only when support for multiple currencies is enabled (see [Support for multiple
     currencies](support-multiple-currencies.dita "(Opens in a new tab or window)")).
   - Purchase Price - Enter a per-unit amount for the asset that is planned to be purchased in
     the current plan year.
   - Purchase Date - Enter an expected date for the asset that is planned to be purchased in
     the current plan year. If the financial rules for your organization for asset accounting include
     CapEx purchases, this is the month for which the purchase price will be recorded in CapEx.
   - In-Service Date - Enter the date the asset is to go into service (something other than
     the purchase date). If the financial rules of your organization for asset accounting include OpEx
     depreciation, this is the beginning month of depreciation.
   - Asset Class - Assign the asset to the correct asset class. Asset reference data controls
     how capital asset purchases and depreciation are accounted for in OpEx and CapEx budgets (see [Add and manage custom attributes of reference
     data (dimensions and line-item tables))](manage_schema.dita "(Opens in a new tab or window)").
   - Depreciation Method - see [Plan for decreasing asset values with Depreciation Methods](depreciation-method.dita "(Opens in a new tab or window)").
8. Select the Summary tab to review asset line items in the context of your overall OpEx or
   CapEx budget.

You can add custom attributes to asset dimensions to capture supplemental information about
assets to enhance your analysis and reporting capabilities. See [Add and manage custom attributes of reference data (dimensions and
line-item tables)](manage_schema.dita "(Opens in a new tab or window)").

## Importing Assets

When importing asset line items, the Asset Class will determine how depreciation expense is
handled. In order to import depreciation expense amounts, the Asset Class depreciation method must
be set to Manual Depreciation; if not, then any depreciation expense values will be ignored and
instead will be calculated using the Purchase Price and Asset Class depreciation method.

It is also possible to import asset line items as externally managed. See discussion of external
line items in [Enter or import
line-item data](enter-import-line.dita "(Opens in a new tab or window)") for more details. Doing so will allow budget owners to view, but not edit,
asset details or depreciation expense amounts (if asset uses the Manual Depreciation method).

To bring in current asset detail with depreciation expense amounts from your Fixed Asset /
Inventory Management system, use the Import External Assets option (in the table Actions menu) on
the Existing Assets tab. Be sure all asset line items you are importing are tagged with an Asset
Class that uses the Manual Depreciation method.

## View delegated project costs

If Project Financial Planning Project Financial Planningis enabled, Project Owners can delegate
project costs to department and service owners. All of these owners can show or hide delegated costs
from their financials. See [Delegate project costs](pfp/delegate-project-costs.dita "(Opens in a new tab or window)").
