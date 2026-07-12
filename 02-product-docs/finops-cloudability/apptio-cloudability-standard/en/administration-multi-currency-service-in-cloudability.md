---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Multi-Currency Service in Cloudability"
breadcrumb:
  - "Administration"
  - "Multi-Currency Service in Cloudability"
source_path: "SSVCLNQ/admin/multi-currency-cldy.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Multi-Currency Service in Cloudability

Multi-Currency Service offers a centralized platform to manage currency exchange tables for your Apptio products. The service simplifies administration and eliminates the need to maintain separate tables for individual products. You can upload the currency exchange tables from a common interface and configure the different Apptio products to use the same tables for currency calculations.

For more information, refer to https://www.ibm.com/docs/en/apptio-platform/multi-currency-service/saas?topic=multi-currency-service .

The Multi Currency Service allows you to use a common currency across all of Cloudability , regardless of the cloud service provider or currency they are billed in. Organizations can operate and communicate in their preferred currency without the need to convert currencies outside of Cloudability.

An organization's Cloudability Billing Contact can designate a preferred currency for users to view reports and dashboards and define exchange rates used for currency conversion.

Only users with the role Cloudability Billing Admin or the permission OrgCurrencyFeatureAccess assigned to their role can configure currency preferences

How to enable multi-currency configuration in Cloudability

In Cloudability , multi-currency configuration can be enabled only by users with the role Cloudability Billing Admin or the permission OrgCurrencyFeatureAccess assigned to their role (henceforth called the "Billing Admin").

First, the Billing Admin needs to set the Preferred Currency with below steps:

1. Access Cloudability home page.
1. Select the Profile icon at the top-right corner of the page, and select Manage Profile .
1. On your profile page, select CURRENCY tab.
1. Under the CURRENCY menu, select your preferred currency.
1. Under the LOCALE menu, select the preferred locale. A preview of the set currency is displayed dynamically.
1. Select Save Currency settings.

This is a one-time configuration, applicable only during the initial setup.

After this, Billing Admin should go to multi-currency configuration screen from the Settings (gear icon) menu at the upper right corner for the Apex Shell, select Multi-Currency Configuration. This will open the Manage Currency Exchange page.

When you click on Upload New Currency Exchange Table, you will find an option on the right pane to download a sample currency exchange table. You may create your currency exchange table using this file.

You can create a currency exchange table using a text editor or a spreadsheet application. Multi-Currency Service supports .xls , .xlsx , .csv , and .tsv file formats.

Your currency exchange table must include the following three columns:

- currrencyCode: Specifies the three-character ISO 4217 Currency Code, for example, USD, CAD, JPY, and GBP. currencyCode cannot be blank.
- currencyRate: Specifies the conversion rate between this currency and your base currency. The base currency will always have a currencyRate: of 1. currencyRate: must be numeric and cannot be blank.
- rateType: Specifies whether the currency exchange rate is type is Plan or Actual. You may use Plan rates with budget/planned costs and Actual rates are for actual / historical costs that have actually been incurred. While this column is required, the cells can be blank. Leave this cell blank for the base currency.

The following example shows a sample currency exchange table.

| currencyCode | currencyRate | rateType |
| --- | --- | --- |
| EUR | 0.96 | Actual |
| EUR | 0.91 | Plan |
| CAD | 1.33 | Actual |
| CAD | 1.2 | Plan |
| GBP | 0.85 | Actual |
| GBP | 0.75 | Plan |
| USD | 1 |  |

After creating the table, drag and drop the file into the drop area. Alternatively, select Browse for a file , and from the file explorer, select the file.

Under Effective From , select the month and year for which your exchange rates need to be effective from

Select Save .

After the upload is completed, the new currency exchange table is added to the table on the Manage Currency Exchange page. You can select the table title to view the data stored in the table. The Base currency (global) field is updated to reflect the base currency defined in the currency exchange table. Please note that the currency with exchange rate set to 1 are considered as Base Currency.

Displayed Currencies list is updated to include all the other currencies specified in the currency exchange table. You can open the Displayed Currencies list, and clear the checkboxes for the currencies that you do not want to show to the end-users.

Once these steps are done, it may take up to 24 hours for the changes to take effect.

List of Currency Codes Supported in Cloudability

| Currency Name | Currency Code |
| --- | --- |
| Argentine Peso | ARS |
| Australian Dollar | AUD |
| Brazilian Real | BRL |
| Canadian Dollar | CAD |
| Swiss Franc | CHF |
| Chinese Yuan | CNY |
| Chilean Peso | CLP |
| Czech Koruna | CZK |
| Danish Krone | DKK |
| Euro | EUR |
| British Pound Sterling | GBP |
| Hong Kong Dollar | HKD |
| Indonesian Rupiah | IDR |
| Israeli Shekel | ILS |
| Indian Rupee | INR |
| Japanese Yen | JPY |
| South Korean Won | KRW |
| Mexican Peso | MXN |
| Malaysian Ringgit | MYR |
| Norwegian Krone | NOK |
| New Zealand Dollar | NZD |
| Polish Zloty | PLN |
| Russian Ruble | RUB |
| Saudi Riyal | SAR |
| Swedish Krona | SEK |
| Singapore Dollar | SGD |
| Thai Baht | THB |
| Turkish Lira | TRY |
| Taiwan Dollar | TWD |
| US Dollar | USD |
| Vietnamese Dong | VND |
| South African Rand | ZAR |
