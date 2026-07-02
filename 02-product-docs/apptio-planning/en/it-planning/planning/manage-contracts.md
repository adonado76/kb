---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Contract Planning Overview"
breadcrumb:
  - "Planning"
  - "Contract Planning"
source_path: "it-planning/planning/manage-contracts.html"
images:
  - "resources/images/it_planning_images/vatinfo.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Contract Planning Overview

The Contract Planning module enables you to budget, forecast, and manage vendor and
supplier contracts within your IT financial planning model. By modeling contracts — their
commitment, cost accrual, and amortization — you gain greater visibility into fixed and
recurring obligations, supporting better decision-making around renewals, spend commitments, and
expense timing.

**Why It Matters**

- Contracts often make up a major portion of IT operating expense.
- Without modeling contracts, planning can omit long-term commitments or hide future
  obligations until renewal time.
- With Contract Planning you can:
  - Capture contract start and end dates, amounts, and amortization methodology
  - Forecast how contract expenses will hit over time (not just at point of purchase)
  - Align contract obligations to cost centers, accounts, departments, and financial
    plans

## Configure Contract Planning

Note: Admin or Budget Process Owner roles are required to perform these tasks.

Before you start entering contract line items, you’ll need to enable Contracts and set up
reference data so contracts behave consistently in your model.

Enabling contract planning activates the related Reference Data tables and adds the
**Contracts** tab to the Expenses table.

Setup Steps 

1. Go to **Settings** (Gear icon) **→ Company Profile**.
2. Enable **Contracts** and click **Save and Exit**.
3. Navigate to **Configuration → Reference Data → Contract Type**.
4. Export the template and populate key fields:
5. **Contract Type –**A classification or label used to identify the category or
   nature of the contract.
6. **Contract Amortization Method** (e.g., Straight Line Even Periods, Straight Line
   Using Calendar Days, Straight Line Prorate First and Last, Straight Line By Duration,
   Manual Amortization). Refer to [Amortization Methods](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-amortization-methods "(Opens in a new tab or window)").
7. **Account** — the GL account where the contract cost will accrue
8. Import the updated CSV and **Publish** the changes so they are available for new
   plans.

## Configure Value Added Tax (VAT)

Note: Admin or Budget Process Owner roles are required to perform these tasks.

Apptio Planning can automatically calculate **value-added tax (VAT)** — also known as
goods and services tax — for contract line items.

To enable VAT calculations, go to **Settings → Company Profile** and enable the
**Include Value-Added Tax (VAT)** option. Enabling this setting will automatically
create a **VAT Rates** reference data table.

VAT is calculated based on the **Location** selected on each contract line item:

- When a contract line item is entered and a **Location** is specified,
- Apptio Planning will **look up the VAT Rate** from the reference data table,
- And automatically calculate the **Amount with VAT**.
- VAT is not amortized — only the original (pre-VAT) amount is used for amortization.

Refer to [Value Added Tax](value-added-tax.html "Apptio Planning supports modeling Value Added Tax (VAT) for contract line items, allowing organizations to accurately represent total contract spend, inclusive or exclusive of tax. VAT is a consumption tax applied to goods and services, and depending on your organization’s accounting policies, it can be either recoverable or non-recoverable.") for more details

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/vatinfo.png)

**Setup Steps**

**Before importing VAT Rates**, ensure your **Location reference data** includes all
relevant locations where VAT should apply.

1. Go to **Settings** (Gear icon) **→ Company Profile**.
2. Enable **Include Value-Added Tax (VAT)** and click **Save and Exit**.
3. Navigate to **Configuration → Reference Data → VAT Rates**.
4. Export the template and populate key fields:
5. **Location** — The location identifier used to determine the applicable VAT rate.
6. **VAT Rate** — The tax rate to apply, entered as a decimal (e.g., enter 0.20 for
   20%).
7. Import the updated CSV
8. Click the **Ellipses menu** and **Publish** the changes so they are available
   for plans.

![image of value added tax](../../../../../03-media/apptio-planning/resources/images/it_planning_images/vatinfo.png)

## Entering & Managing Contract Line Items

- Open your plan and navigate to the **Contracts** tab within the **Expenses** page.
- Add a new contract by either:
  - Using the **empty row** at the bottom of the table, or
  - **Right-clicking** and selecting **Insert Row**
- Provide required information for each contract:
  - **Contract Type** - The category or classification of the contract, which
    determines default accounting rules such as amortization method.
  - **Cost Center****-** The cost center financially responsible for the
    contract’s cost and amortization.
  - **Vendor** (optional) - The supplier or external party providing the contracted
    service. Useful for reporting and vendor spend analysis.
  - **Location** (optional) - Used to determine the applicable VAT Rate if VAT is
    enabled. VAT is calculated based on this location.
  - **Contract Amount -** The total committed contract value to be amortized over the
    selected contract term.
  - **Start Date** - The date when the contract becomes active and expense
    recognition (amortization) begins.
  - **End Date** - The date when the contract term ends and expense recognition
    stops.
  - **Amortization Method**- The method used to spread the contract cost across time
    periods. This is automatically populated based on the Contract Type but can be
    overridden if needed.
  - **Amortize** (checkbox) -
    - Enabled (true): Spreads the contract amount evenly over the full contract term.
    - Disabled (false): Recognizes the full contract amount in the first period of the
      contract start date.
- Review the amortization schedule generated by the system and verify that it fits your
  expectations (e.g., cost distributed across months accordingly).

Once the contract is entered, Apptio Planning automatically calculates the amortization
expense based on the contract details and selected amortization method. The expense is then
distributed across the time period columns in the Contracts tab.

In the **Summary** tab, Apptio Planning generates the corresponding financial entry for
the amortization expense using the configured **Amortization Account**.

## Delegate Contract Expense to a Different Cost Center

If the amortization expense should be charged to a different cost center than the one that
owns the contract, you can populate the **Delegation Cost Center** and **Delegation
Start Date** fields. This redirects the expense to another cost center starting on the
specified date.

This is useful in scenarios such as when a contract is purchased by a Project cost center,
but ongoing costs should be charged to a different operational cost center.

In this setup, the contract remains owned by the original cost center, but the financial
impact is applied to the delegated cost center.
