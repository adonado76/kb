---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "00-Administration-others"
source_files_count: 2
last_updated: "2026-07-13"
---

# 00-Administration-others

## Multi-Currency Service in Cloudability

<!-- sub-header -->
- **breadcrumb:** Administration > Multi-Currency Service in Cloudability
- **source_path:** SSVCLNQ/admin/multi-currency-cldy.html
- **original_file:** administration-multi-currency-service-in-cloudability.md
- **images:** []

## Multi-Currency Service in Cloudability

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

---

## Setting up Time Zone Preferences

<!-- sub-header -->
- **breadcrumb:** Setup > Setting up Time Zone Preferences
- **source_path:** SSVCLNQ/product/manage-profile.html
- **original_file:** setup-setting-up-time-zone-preferences.md
- **images:**
  - 03-media/apptio-cloudability-standard/share_and_subscribe_to_reports,_alerts,_and_emails_6.jpg
  - 03-media/apptio-cloudability-standard/share_and_subscribe_to_reports,_alerts,_and_emails_7.jpg
  - 03-media/apptio-cloudability-standard/share_and_subscribe_to_reports,_alerts,_and_emails_8.jpg
  - 03-media/apptio-cloudability-standard/share_and_subscribe_to_reports,_alerts,_and_emails_9.jpg
  - 03-media/apptio-cloudability-standard/Default_Cost_Metric_Config.png

## Setting up Time Zone Preferences

1. Click the User icon at the top right and select Manage Profile .
1. Click the PREFERENCES tab, and define the define default View and Time zone under the View and Timezone section . The timezone will be used as your Cloudability timezone.

Subscribe to Summary Emails

Send your most important cloud data to your email at time intervals you define.

1. To define how often you’d like to receive your emails, in the Cloud Spend Summary Emails section, select an option from the EMAIL FREQUENCY list: Daily, Weekly, Monthly, Quarterly or Off.
1. Select the PREFERENCES tab.
1. To define how often you’d like to receive your emails, in the Cloud Spend Summary Emails section, select an option from the EMAIL FREQUENCY list. Selecting Off opts you out of summary emails.
1. To set your cost metric, click the list under Cost Metric for Mail and select an option. When you have linked accounts within a Consolidated Billing account family, AWS includes a blended rate and unblended rate in your detailed billing reports. If you're using Reserved Instances, it may make sense for you to report based primarily on Unblended cost. NOTE : To use amortized costs, your default view cannot include a tag-based filter. Estimates will reflect Cost(Total) if Cost(Amortized) is selected.
1. To set your budget, click the drop-down under Budget for Mail and select an option. Your cloud spend summary email will look something like this:

Choice of delivery for delayed organizations

This is a custom setting for accounts using Cloudability Enterprise and must be enabled by the Cloudability Success team.

If your data is consistently delayed from AWS (due to data volume or parsing done before sending it to Cloudabiilty), this could create a scenario where users consistently get the new Data Delayed email. To prevent this, we've added an option that lets your users select when to receive their mail. They can choose to get their mail with the most up-to-date data (regardless of freshness) or opt to wait until we have the The last complete day . The former is the default.

- Month-to-Date Spend : See how much you've spent this month, then compare that to your spend on this date last month.
- Est. Monthly Spend : See how much you're estimated to spend this month based on a rolling average over a user-defined number of days, then compare that to last month's total.
- Yesterday's Spend : This number reflects your estimated spending for the day prior to your receipt of the email.
- Cost : This section of Daily Mail will list the AWS accounts and the AWS Services (such as RDS, Elastic Compute Cloud, etc.) which have generated the most spending this month to date.
- Month-to-Date Usage Hours : See how many hours of usage you've generated this month, then compare that to your usage hours on this date last month.
- Yesterday's Usage Hours : This number reflects how many hours of usage you generated for the day prior to your receipt of the email, and compare that total to the day before.
- Yesterday's Running Instance Count : See how many instances yesterday's usage hours spanned across, and compare that total to the day before.
- Usage : See the five most recent instances that have been started on your account.
- Email Settings : Drill into the data that matters to you with settings that allow you to filter by View, exclude certain spending types such as taxes or one-time costs, and choose whether your data is calculated using Blended or Unblended cost.

Configuring the default cost metrics for your org

Each module in Cloudability (eg: True Cost Explorer, Rightsizing etc.) supports a specific set of cost metrics like Cost (Total), Cost (List), Cost (Amortized) etc. While Cost (Total) is the default cost metric for these modules, an admin user can change this and set it to a different default cost metric by navigating to Manage Profile > Organization Settings page.

![screenshot for default cost metric config](../images/Default_Cost_Metric_Config.png)

This screen would display all Cloudability modules that support more than 1 cost metric, along with a drop down that contains the list of metrics that are currently supported for that respective module. As an admin user, you can choose your preferred cost metric for each of the modules and click Save Default Cost Metrics button at the bottom which will apply your changes across users in your entire Cloudability org.

---
