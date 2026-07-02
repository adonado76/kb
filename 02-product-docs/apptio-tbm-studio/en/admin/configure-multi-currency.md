---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "admin"
title: "Configure multi-currency"
breadcrumb: []
source_path: "admin/configure-multi-currency.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configure multi-currency

Applies to: TBM Studio v12.1 and later

If your company has offices in more than one country, you should configure multi-currency. At the
very least, you should enter annual exchange rates. If you need more up-to-date figures, you can use
quarterly or monthly exchange rates.

- When you configure multi-currency for a project, the following features are enabled:
- The Admin select a base currency and locale for a project (use the Project tab,**Project Setup** group, Project Settings command).
- The Admin can enter exchange rates for any number of other currencies (Data tab > Currency
  Exchange table).
- All currency values on reports are displayed based on the exchange rates.
- When you define a metric, you can select a default multi-currency rate type. For example: if
  there are two rate types, Plan and Actual, you could choose Plan or you could choose
  Actual.

  Note: For multi-currency for Apptio Cloud products, the values in the Type column in the data
  that you load into the Currency Exchange table must be labeled as Actual in your raw data in order
  for the multi-currency feature to work.
- Users can select a currency and locale for their profile (click the user name in the
  header).
- Users can select a currency for a specific report and all values in the Ad Hoc components on the
  report will be displayed in the currency (click the multi-currency list in the report
  toolbar).![](../../resources/images/studio_images/studioimages/studio_report%20toolbar_multi-currency.png)
- In TBM Studio mode, values are always displayed in the base currency.
- Currencies are converted from the base currency.
- All time-aware reports use the currency rate of the appropriate month or the annual exchange
  rate. By using the monthly currency rate, changes in values can be linked to changes in exchange
  rates.
- You can add columns to Ad Hoc tables and select the currency and rate type for the column. A
  table can have columns that display values in different currencies.

For additional information related to using multi-currency for Apptio Cloud products, see [Configure multi-currency for Cloud](../../cost-transparency/configuration/multicurrency.html "(Opens in a new tab or window)").

## Supported currencies and locales

Currency determines the currency symbol (e.g.: €/$) and the three-letter international currency
code (e.g.: EUR/USD) displayed with values. Locale determines the format of the numbers. The two are
independent of each other. Locale determines the currency symbol placement and spacing but not by a
literal interpretation of the chart format template. So, $#,### is interpreted to mean "show as
currency," with "thousand" separators, zero precision, and the currency symbol positioned (prefix
vs. suffix, spacing) based on the locale.

The application supports all the currency codes listed in the International Organization for
Standardization ISO 4217 code list. The application supports the following locales. The matching
currency codes and the locale formats are listed next to each locale.

> Argentina | ARS | #.##0,##
>
> Australia | AUD | # ##0.##
>
> Austria | EUR | #.##0,##
>
> Belgium (Dutch) | EUR | #.##0,##
>
> Belgium (French) | EUR | #.##0,##
>
> Botswana | BWP | #,##0.##
>
> Brazil | BRL | #.##0,##
>
> Canada (French)| CAD | #.##0,##
>
> Canada (English) | CAD | #,##0.##
>
> China (mainland) | CNY | #,##0.##
>
> Colombia | COP | #.##0,##
>
> Czech Republic | CZK | #.##0,##
>
> Denmark | DKK | #.##0,##
>
> Ecuador | USD (formerly ECS) | #,##0.##
>
> Ethiopia | ETB | #,##0.##
>
> Finland | EUR | #.##0,##
>
> France | EUR | #.##0,##
>
> Germany | EUR | # ##0,##
>
> Ghana | GHS | #,##0.##
>
> Honduras | HNL | #,##0.##
>
> Hungary | HUF | # ##0,##
>
> Ireland (English) | EUR | #.##0,##
>
> Ireland (Irish) | EUR | #.##0,##
>
> Italy | EUR | #.##0,##
>
> Japan | JPY | #,##0
>
> Kenya | KES | #,##0.##
>
> Luxembourg (French) | EUR | #.##0,##
>
> Luxembourg (German) | EUR | #.##0,##
>
> Malawi | MWK | #,##0.##
>
> Mauritius | MUR | #,##0
>
> Mexico | MXN | #,##0.##
>
> Mozambique | MZN | #.##0,##
>
> Netherlands | EUR | #.##0,##
>
> Nigeria | NGN | #,##0.##
>
> Norway (Bokmal) | NOK | # ##0,##
>
> Norway (Nynorsk) | NOK | # ##0,##
>
> Panama | PAB | #,##0.##
>
> Peru | PEN | #,##0.##
>
> Poland | PLN | # ##0,##
>
> Portugal | EUR | #.##0,##
>
> Romania | RON | #.##0,##
>
> Slovakia | EUR | #.##0,##
>
> South Africa | ZAR | # ##0.##
>
> South Korea | KRW |#,##0 (added in R11.8.1.5)
>
> Spain (Catalan) | EUR | #.##0,##
>
> Spain (Spanish) | EUR | #.##0,##
>
> Swaziland | SZL | #,##0.##
>
> Sweden | SEK | # ##0,##
>
> Switzerland (French) | CHF | #'##0.##
>
> Switzerland (German) | CHF | #'##0.##
>
> Switzerland (Italian) | CHF | #'##0.##
>
> Tanzania | TZS | #,##0.##
>
> Uganda | UGX | #,##0.##
>
> United Arab Emirates | AED | #,##0.##
>
> United Kingdom | GBP | #.##0,##
>
> United States | USD | #,##0.##
>
> Vietnam | VND | #,##0

## Restrictions

Multi-currency has the following restrictions:

- In reports, only values based on modeled metrics of Costing and Pricing types can be displayed
  in the currency chosen by users. All other values will be displayed in the base currency or in the
  currency to which they have been converted.
- Multi-currency applies only to Ad Hoc tables and charts. It does not apply to legacy tables and
  charts.
- Editable tables are displayed in the currency assigned to the data set and cannot be
  changed.
- It does not apply to the legacy Budgeting and Forecasting application.
- Waterfall charts always are displayed in the base currency set for the project.
- When in TBM Studio mode, the session currency is switched to the base currency.

## Configure multi-currency

Key steps to configure multi-currency:

1. Enter exchange rates in the Currency Exchange table under the Other category. If
   the table is not in the Other category, set the Filter to Hidden to display the
   table's name.![](../../resources/images/studio_images/studioimages/studio_project%20explorer_currency%20exchange.png)
2. Assign default rate types to each cost and pricing metric.
3. Select a currency (and locale) for the project.

   Note: Currency determines the currency symbol
   (e.g.: €/$) and the three-letter international currency code (e.g.: EUR/USD) displayed with values.
   Locale determines the format of the numbers. The two are independent of each other.

## Enter exchange rates

Enter exchange rates in the Currency Exchange table. The base currency always is set to 1. The
Currency Code must be one of the standard three-letter international currency codes. The rate
should be a conversion multiplier of the base currency rate. The type is a short description for the
exchange rate. Two common descriptions are Plan for yearly values and Actuals for monthly values. A
sample Currency Exchange table is shown in the following image:

![](../../resources/images/studio_images/studioimages/studio_currency%20exchange_table.png)

You must enter the same rate types for each currency. For example, if you define Plan and Actual
rate types for the EUR currency, you also must define Plan and Actual rate types for all the other
currencies.

Note: The base currency does not have a type and can be displayed anywhere in the table.
It does not have to be the first entry in the table.

If you enter a currency code that is not matched by a locale, the three-letter currency code will
be displayed instead of the currency symbol. For example: CNL59,000.

## Assign a default rate type to each money metric

For reports to display correctly, you must define a rate type for each cost and pricing modeled
metric. Common rate types are Plan, Actual, Monthly, and Weekly. To assign a default rate type:

1. In the Project Explorer, click the metric.
2. From the Default Multi-Currency Rate Type field, select a rate
   type.![](../../resources/images/studio_images/studioimages/studio_cost%20ytd_formula%20metric.png)
3. Check that the Table Format field (see above) has an =Currency
   entry.

## Select a currency (and locale) for the project

1. Open the Project tab and click Project
   Settings.
2. Select a currency from the Base Currency field.
   - This controls the currency symbol (e.g.: €/$) and the three-letter international currency code
     (e.g.: EUR/USD) displayed with values.

     Note: When users are working in TBM Studio, all values will be
     displayed in the base currency regardless of the currency preferences the user has
     selected.
   - If you select Single Currency, multi-currency will not be active for the project.
3. Select a locale from the Locale field. Locale determines the format of
   the numbers. Locale is independent of the currency. Example locales:
   - United States: 12,345.67
   - France: 12 345,67
   - Germany: 12.345,67

## Convert data to base rate

If you are importing data in multiple currencies that you want to merge into a single data set,
you must first convert the data to the base currency for the project. For example, you may be
importing values from multiple general ledgers.

1. Import the data set.
2. Add a column to the transform data set using the [ConvertCurrencyToBase](../formulas-and-functions/functions/convertcurrencytobase.htm "(Opens in a new tab or window)") function.This column will contain the base currency values.
3. Append the data set to the merged data set.

   Note: There is also a function.
