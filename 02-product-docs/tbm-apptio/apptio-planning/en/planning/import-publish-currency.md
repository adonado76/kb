---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Reference Data Requirement"
breadcrumb: []
source_path: "planning/import-publish-currency.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Reference Data Requirement

The tasks below can only be performed by users assigned to the Admin or Budget Process
Owner roles. For additional information on roles, see Frontdoor permissions and roles.

Apptio planning applications support two distinct rate tables:

- Plan currency conversion rate table - Use for all currency conversions in
  budget plans and forecasts
- Actuals currency conversion rate table - Use for converting actuals
  recorded in various local currencies to one common currency for summarized views of actuals

Plan and Actual currency conversion rates are part of built-in dimensions that you manage in
Reference data. See [Manage
currency conversion rate tables reference data](manage-multi-currency.htm "(Opens in a new tab or window)"). Specify the conversion rate between the
common currency of your organization and another currency. See [Set the common currency](set-common-currency.htm "(Opens in a new tab or window)"). Optionally, you can specify a period
of time for which a specific conversion rate will apply.

## Download and populate the currency conversion rate table template

To create a reference data:

1. Ensure support for multiple currencies is enabled (see [Support for multiple
   currencies](support-multiple-currencies.htm "(Opens in a new tab or window)")).
2. In the navigation menu, select Configuration > Reference
   Data. You have two currency rates: Actuals Currency Rate and
   Plan Currency Rate.
   - Actuals Currency Rate reference data defines the currency conversion
     rates used to convert multiple currencies to a common currency. This allows you to see summarized
     views of actuals:

     ![](../../resources/images/it%20planning_images/actuals-currency.png)
   - Plan Currency Rate reference data defines the currency conversion rates
     used to convert multiple currencies to a common currency in budget plans and forecasts:

     ![](../../resources/images/it%20planning_images/plan-currency.png)

     See [Manage Multi-Currency Conversion Rate
     Tables reference data](manage-multi-currency.htm "(Opens in a new tab or window)").

     Note: You need to export a template for Actuals Currency and Plan
     Currency. If your Apptio planning application is integrated with Costing Standard, you must use the
     same actuals currency rate table for both applications.
3. Open the .csv template file. Don't change the column headings or structure of this
   template.
4. Enter your conversion rate values. Options per currency value include:
   - A single conversion rate that spans all time periods.
   - Time-box-varied conversion rates per currency value. Specify an Effective From start period for
     a specific conversion rate. Then, specify the start dates for other time periods for that same
     currency value.
5. Optionally, include a row for the common currency with a conversion rate of 1. If you don't, an
   alert will appear, and this will be done for you when you import the rate
   table.TIP: Your Apptio planning applications will work with the rate table
   data in any row order, but the headings must remain in row 1. When editing the .csv file, you can
   sort it by any column heading (for example, sort by date or by currency code). The sort order you
   use will be applied to the currency rate table after it is imported into your Apptio planning
   application.
6. Save the template in .csv format for import.

For example, the rate table values that set per-month currency rates for the US Dollar company
currency and the Euro:

![](../../resources/planning_images/itp_currency-converion-rate-table-example.png)

In this example table, all US Dollar/Euro conversions prior to Jan. 1, 2016 (1) use the 0.88
conversion rate. Then, the rate adjusts per month as shown (2). Since no later conversion rates are
specified, all conversions after March 1, 2016 will use the 0.91 rate (3).

When you publish the rates, they will be available here: In the left navigation, select
Planning > Expenses > Summary,
and the published rates are available in each of these tabs: Summary,
Labor, Contracts, Assets,
Others. . Also you will be able to select any views based on those currencies
being published.

## Import and publish currency rate tables

To upload and publish the currency rate tables reference data, see [Manage Multi-Currency Conversion Rate
Tables reference data](manage-multi-currency.htm "(Opens in a new tab or window)").

## Troubleshooting

In this section, you can find some
frequent errors and solutions to them.

[Your KPI or values in a plan display the #REF error](ts_ref-error-kpi-plan.htm "(Opens in a new tab or window)")
