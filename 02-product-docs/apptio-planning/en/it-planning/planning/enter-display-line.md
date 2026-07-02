---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Working with Different Currencies"
breadcrumb:
  - "Planning"
  - "Working with Plans"
source_path: "it-planning/planning/enter-display-line.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Working with Different Currencies

Apptio Planning supports multi-currency setups that allow you to enter, display, and
reconcile financial data across different currencies. This is especially useful for global
organizations that manage budgets in various regions.

## Enabling Multi-Currency

Note: Admin or Budget Process Owner roles are required to edit Company Profile
settings.

1. Click the **Gear** icon and open **Company Profile**.
2. In the **Currency** section, check **Enable Multi-Currency**.
3. Set the default **Currency** for your environment.
4. *(Optional)* Enable **Show ISO Currency Codes instead of Symbols** if you prefer
   ISO codes (e.g., USD, EUR) over currency symbols.
5. Click **Save** to apply your changes.

## Setting Up Multi-Currency Exchange Rates

Once multi-currency is enabled, you’ll need to configure exchange rates so the system can
accurately convert values between currencies.

Apptio Planning uses two separate exchange rate tables:

- **Actuals Currency Rate** — applied to historical periods
- **Plan Currency Rate** — applied to plan and forecast period

**Steps to configure exchange rates:**

1. Go to **Configuration > Reference Data > Actuals Currency Rate** or **Plan Currency
   Rate**.
2. Open the **Ellipses menu** and choose either:
   1. **Export Template** to download a blank template, or
   2. **Export** to download existing rate data for update.
3. Populate the file and define the following fields:
   1. **From Currency** – ISO code of the base currency (default currency defined in
      the Company Profile)
   2. **To Currency –** ISO code of the target currency
   3. **Rate** — the conversion rate
   4. **Effective From** — start date for the rate. Use YYYY-MM-DD or MM-DD-YYYY date
      format.
4. Ensure to define the **base rate** by setting the **default currency** to itself —
   e.g., USD → USD with a rate of 1.
5. **Import** the updated file and **publish** the changes.

## Entering Line Item Values in Different Currencies

- When multi-currency mode is enabled, each line item will include a **Currency**. Line
  items can only be edited when the **global Currency menu** (in the top navigation bar)
  is set to **Original**.
- You can enter values in any defined currency on a per-line-item basis.
- To view converted values, select a currency from the **global Currency menu** — the
  Expenses table and dashboards will automatically convert all values to the selected
  currency using the appropriate **exchange rate** for that period and data type (Actuals
  or Plan).

## Configure Default Currencies per Department

Note: Admin or Budget Process Owner roles are required to manage Reference Data.

You can define adefault currency for each Department to ensure data entry is aligned with
local or regional financial requirements.

**Steps:**

1. Open the **Department** reference data table.
2. **Export** the Department data and enter the desired **default currency code**
   in the **Currency** column for each Department.
3. **Re-import** the updated file and **publish** the changes.

If a Department does not have a currency defined, the **default currency**(defined in
the Company Profile) will be used when accessing that department.
