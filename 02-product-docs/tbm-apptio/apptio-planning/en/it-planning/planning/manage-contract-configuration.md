---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Configure Contracts"
breadcrumb: []
source_path: "it-planning/planning/manage-contract-configuration.html"
images:
  - "resources/images/icons/3-dots.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configure Contracts

The tasks below can only be performed by users assigned to the Admin or Budget Process
Owner roles. For additional information on roles, see Frontdoor permissions and roles.

Dimensions are the essential data categories in budget line items. Many built-in
dimensions have dependencies on other dimensions (see [Reference data attribute and dimensions
dependencies](manage-reference-data.html) for more information). You can import dimensions reference data from a
.csv file or from Costing Standard and export dimensions reference
data templates and table data (see [Manage
dimensions](manage-reference-data.html)).

![see icon](../../resources/images/it%20planning_images/icon_video.png)

## Manage Contract Type reference data

A Budget Process Owner or Admin can define rules to control how contract types are accounted for
in OpEx budgets. You can specify that a given contract type always accrues to a specific OpEx
account with a specific amortization method.

1. Enable the Contracts and VAT features in the Company Profile (see [Edit the Company Profile.](edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning.")
2. In the navigation menu, select Configuration > Reference Data > Contract Type.
3. Select ![more icon](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) in the
   top right corner of the table, select Export > Export All.
4. Update the data table values as required in the .csv file:
   - Contract Type - Provide a name for the combination of the general ledger account and
     amortization method. Meaningful contract type names can help Cost Center Owners allocate their
     contract expenses to the correct general ledger account codes.

     For example, contract types with names that are meaningful to the Cost Center Owner, such as
     Hardware Maintenance, can all map to the same Vendor Services general ledger account code.
   - Contract Amortization Method - Specifies how your contract will be amortized over the
     life of the contract. The amortization of contracts allows you to spread costs over the course of
     the life of a contract instead of accruing the full amount of the contract on the start date of that
     contract. Amortization Start Offset delays the beginning of amortization, changes the number of
     periods, and keeps the same end date for contracts. Because it delays the start date, the number of
     periods in the amortization schedule change. However, the final period of the schedule does not
     change. All calculations for each day are based on the standard Gregorian calendar. The following
     methods are available:
     - Manual Amortization - allows you to manually import, enter and edit the per period
       amortized expense amounts for a contract.
     - Straight Line Even Periods - (Default method) Amortizes expenses evenly for each period.
       The amortization period is defined by the start and end month of the contract.
     - Straight Line By Duration - Amortizes expenses evenly for each period. The amortization
       period is defined by the number of months in the contract.
     - Straight Line Prorate First and Last - Amortizes equal amounts for periods other than the
       first and the last period. For the first and last period, amounts are prorated based on the number
       of days in each period.
     - Straight Line Using Calendar Days - Amortizes amounts individually for each period based
       on the number of calendar days in each period.
   - Account - Specifies the general ledger account code where the contract will accrue. The
     available options are provided by the Chart of Accounts reference data.
5. Now, Configuration > Reference Data > Contract Type, and then import the updated .csv
   file

## Contract amortization example

The following example uses these starting values:

- Amount - $400.00
- Start Date - August 20, 2017
- End Date - December 19, 2017
- Duration calculated using month only (used by Even Periods method) - 5 months
- Duration calculated using month and day (used by Duration method) - 4 months

| Amortization method | Aug. | Sept. | Oct. | Nov. | Dec. | Total |
| --- | --- | --- | --- | --- | --- | --- |
| Straight Line Even Periods | $400 / 5 = $80 | $400 / 5 = $80 | $400 / 5 = $80 | $400 / 5 = $80 | $400 / 5 = $80 | $400 |
| Straight Line By Duration | $400 / 4 = $100 | $400 / 4 = $100 | $400 / 4 = $100 | $400 / 4 = $100 |  | $400 |
| Straight Line Prorate First and Last | 12 / 122 $400 = $39.34 | $298.36 / 3 = $99.45 | $298.36 / 3 = $99.45 | $298.36 / 3 = $99.45 | 19 / 122 $400 = $62.30 | $400 |
| Straight Line Using Calendar Days | 12 / 122 $400 = $39.34 | 30 / 122 $400 = $98.36 | 31 / 122 $400 = $101.64 | 30 / 122 $400 = $98.36 | 19 / 122 $400 = $62.30 | $400 |

Note:

- Amounts calculate to exact values. The amounts round to the nearest whole unit of currency (for
  example, USD).
- Add custom attributes to capture supplemental information about contracts to enhance your
  analysis and reporting capabilities (see [add custom attributes to contract dimensions)](manage_schema.html "Schemas define the structure of data in Apptio Planning. They specify the tables, fields, and relationships that determine how information is stored, linked, and surfaced across Expense tabs such as Labor, Contracts, Assets, and Financials.").
- The supported amortization method for custom calendars are Straight Line Even Period, Straight
  Line Using Calendar Days, Manual Amortization, and Straight Line By Duration Custom Fiscal
  Calendar.

## Manage VAT Rates reference data

Once the Budget Process Owner or Admin enables the contract planning and VAT features, the Apptio Planning application can calculate a value-added tax (VAT), also known as a goods and services tax,
for contracts and manage the VAT Rate. See [Edit the Company Profile](edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning."). The VAT Rate (a built-in dimension) specifies the
taxed percentage applied to each location. VAT is based on the contract line-item Location value in
reference data. Therefore, before importing VAT Rates reference data, you must update the Location
reference data to include all locations for which you plan to enter a VAT Rate. See [Reference data
dimensions](manage-reference-data.html).
