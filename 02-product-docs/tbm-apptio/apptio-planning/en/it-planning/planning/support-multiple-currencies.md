---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Multiple currencies"
breadcrumb: []
source_path: "it-planning/planning/support-multiple-currencies.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Multiple currencies

Apptio Planning applications support the planning, reporting, and analysis needs of organizations
that work with multiple currencies. Features that support multiple currencies include the
following:

- A single, common currency used for all currency conversions. The common currency is usually the
  organization's currency of record. All currency conversion rates are set against this currency, and,
  unless another is specified, it is the default display currency per Cost Center. For more
  information, see [Set the common currency](set-common-currency.html "A single, common currency is used for all currency conversions. The common currency is usually the organization's currency of record. All currency conversion rates are set against this currency, and, unless another is specified, it is the default display currency per Cost Center.").
- Support for all currencies that use an ISO code. For more information on the list of
  internationally recognized codes, see [https://www.iso.org/iso-4217-currency-codes.html](https://www.iso.org/iso-4217-currency-codes.html "(Opens in a new tab or window)"). The ISO code
  specifies the three-letter currency abbreviation (for example, USD for the US Dollar), and the
  correct display of the currency (for example, the $ symbol and comma and decimal positioning). An
  Administrator can select to display currency ISO codes rather than currency symbols and can enable
  features to support multiple currencies.
- Optional assignment of a local currency for group or individual cost centers. The local currency
  codes of Cost Centers are managed as Cost Center reference data. If no local
  currency code is specified, it defaults to the company code.
- Separate currency conversion rate tables for plan (budget and forecast) and actuals financial
  data. Conversion rate tables define currency conversion (FX) rates against the common currency, and
  are managed as reference data. Time-boxed conversion rates for actuals can help distinguish real
  variance from plan versus variance due to currency fluctuations.
- Support for time-boxed conversion rates per currency in rate tables. Specify conversion rates at
  any scale, from daily to yearly. Conversion rates per currency allow for entering budget amounts in
  a local currency for the Cost Center, then converting to the common currency (or any other supported
  currency) when summarized.

## Enable multi-currency features

Users assigned to the Administrator or Budget Process Owner roles can enable
multi-currency features. Choose to show or hide multiple currency support features. Multiple
currency support is set in the Company Profile section, and applies to all
users of the currently selected tenant. For more information, see [Edit the Company Profile](edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning.").

1. On the Apptio Planning menu, click the Settings button, then click
   Company Profile.
2. In the Settings section, select Enable Multi
   Currency.

   Note: If you want to switch the display of currency values from a currency
   symbol to a three-letter ISO currency code, select Show ISO Currency Codes instead of
   Symbols. For example, a currency value CA$30.68M, can be displayed as 30.68M CAD. This
   provides clarity to organizations and users who work with a variety of currencies.
3. Select Save and Exit.

Attention: After the multi-currency features are enabled, complete the following tasks:

- [Set the common currency](set-common-currency.html "A single, common currency is used for all currency conversions. The common currency is usually the organization's currency of record. All currency conversion rates are set against this currency, and, unless another is specified, it is the default display currency per Cost Center.")Set the common currency for your organization
- [Reference Data Requirement](import-publish-currency.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.")Import and publish currency rates
- [Enter or display line-item values in different currencies](enter-display-line.html "When support for multiple currencies is enabled, a Currency list on the upper right of the page allows you to display line-item budget plan or forecast financial values in a currency value other than the company currency.")Enter or display line-item values in different
  currencies
