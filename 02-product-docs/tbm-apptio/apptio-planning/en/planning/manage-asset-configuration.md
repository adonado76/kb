---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Asset Configuration reference data"
breadcrumb: []
source_path: "planning/manage-asset-configuration.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Asset Configuration reference data

The tasks below can only be performed by users assigned to the Admin or Budget Process Owner
roles. For additional information on roles, see Frontdoor permissions and roles.

Watch this video from Apptio Education Services: [Configuring Reference
Data: Contract & Asset Dimensions](https://community.apptio.com/videos/1994 "(Opens in a new tab or window)").

Or see all [Apptio planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)").

Dimensions are the essential data categories in budget line items. Many built-in dimensions have
dependencies on other dimensions (see [Reference data attribute and dimensions dependencies](manage-reference-data.html) for more information). You
can import dimensions reference data from a .csv file or from Costing Standard and export dimensions
reference data templates and table data (see [Manage dimensions](manage-reference-data.dital "(Opens in a new tab or window)")).

Asset Class reference data controls how capital asset purchases and
depreciation are accounted for in OpEx and CapEx budgets. For example, you can specify that a given
asset class always accrues to a specific CapEx purchase account and an OpEx depreciation
account.

1. Enable Assets (see [Edit the Company Profile](edit-company-profile.dita "(Opens in a new tab or window)")).
2. In the navigation menu, select Configuration > Reference Data > Asset Class.
3. Select ![](../../resources/images/icons/3-dots.png) in the top right corner of the
   table, select Export > Export All.
4. Open the downloaded .csv file and update the data values as required:
   - Asset Class - Asset class category name
   - Depreciation Account - OpEx account that accrues the depreciation expense
     of the selected asset class
   - Depreciation Method - Model used to predict the decline in value over
     time for the asset class. For more information, see Plan for decreasing asset values with
     Depreciation Methods.
   - Purchase Account - The CapEx account that accrues the purchase expense of
     the selected asset class
   - Asset Life (months) - The standard depreciation lifespan of the asset
     class
   - Residual Value % - The percentage of purchase price to be calculated as
     residual value for the asset class
   - Balance Rate (%) – The declining balance rate to be applied for annual
     declining balance depreciation. For this depreciation method, the balance rate will be applied to
     the asset’s value each year. For example, an asset with a purchase price of $100,000 that
     depreciates with a balance rate of 40% would depreciate $40,000 in its first year.
5. Now, Configuration > Reference Data > Asset Class, and then import the updated .csv
   file.

Tip: You can add custom attributes to asset dimensions to capture supplemental
information about assets to enhance your analysis and reporting capabilities. To learn more, see
[Add and manage custom attributes of
reference data (dimensions and line-item tables)](manage_schema.dita "(Opens in a new tab or window)").

## Formulas to calculate amortization for each of the listed depreciation methods

**Straight Line uses the formula:**

- Depreciation Amount = (Asset Price \* (1 - Residual Value)) / Asset Life
- Asset Life = Duration in Months or Days

**Double Declining uses the formula:**

- Depreciation Amount = 2 \* ( 1 / Asset Life) \* Beginning Period Book Value
- Asset Life = Duration in Months or Days
- Beginning Period Book Value = Asset Price - Accumulated Depreciation

**Declining Balance uses Balance Rate to calculate each period:**

- Depreciation Amount = Asset Balance \* Balance Rate / 12
- Newly calculated at beginning of each year: Asset Balance = Asset Balance - Asset Balance \* (
  Balance Rate / 12 ) \* # Months Depreciated in previous year

## Example

Asset Price = $40K

Asset Life = 12 months

In Service Date = 1/15/2024

Straight Line (P1 FY24) = $40K \* (1 - 0) / 12 = $3333

Double Declining (P1 FY24) = 2 \* (1/12) \* ($40K - $0) = $6667

Double Declining (P2 FY24) = 2 \* (1/12) \* ($40K - $6666) = $5556 (edited)

Note: Double Declining calculates the Book Value at the beginning of each period instead of at the
beginning of the year. So if you want to model a standard Double Declining (twice the rate of
straight line) then you should use Declining Balance with a Balance Rate = 200%.
