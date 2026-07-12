---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Enter or display line-item values in different currencies"
breadcrumb: []
source_path: "planning/enter-display-line.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Enter or display line-item values in different currencies

When support for multiple currencies is enabled, a Currency list on the upper right of
the page allows you to display line-item budget plan or forecast financial values in a currency
value other than the company currency.

## About this task

Examples of other currencies include your local currency, or the currency in which a vendor was
paid. The currencies in which you can enter line item values per cost center must have the following:

- A currency conversion rate table published in the application. (For more information, see [Import and publish currency
  rates](import-publish-currency.html)).
- A currency code specified in the Cost Center reference data. (For more information, see [Manage Financial reference
  data](manage-financial-dimensions.html)).

## Procedure

- **Enter line-item values in a local currency**

  To use multiple currencies in your budget planning:

  1. In the navigation menu, select
     Planning > Expense.
  2. Enter a line item in any of these tabs: Summary,
     Labor, Contracts, Assets,
     Others.
  3. Select the Currency column > Select currencies from
     the drop down that has been published to the plan.

  ![](../../resources/images/it%20planning_images/currency-dropdown.png)

  If a specific date range has been specified in the rate table, the transaction date is used to
  determine the correct currency conversion rate. See [Import and publish currency rates](import-publish-currency.html).
- **Display financial values in different currencies**

  A Currency list on the upper right of the Summary and Expense page under
  Planning in the left navigation allows you to convert displayed financial
  values to the currency of your choice. The available currencies you can use must have published
  currency conversion rate tables. For more information, see [Import and publish currency rates](import-publish-currency.html). The selected currency remains
  in effect across views until it is changed.

  On the Summary page, the Apptio planning application converts the following financial values to
  your selected currency:

  - Summary KPI values (upper left)
  - Group and individual values in all charts
  - Line-item values in all Cost Center line-item details

  When viewing line items in a table, the following financial values are converted to your selected
  currency:

  - Line-item KPI values (upper left)
  - Individual row line items per month and line-item total values
  - Per month and all up line-item totals (bottom row)
