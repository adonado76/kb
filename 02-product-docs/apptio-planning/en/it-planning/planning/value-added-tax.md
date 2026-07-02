---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Value Added Tax"
breadcrumb:
  - "Planning"
  - "Contract Planning"
source_path: "it-planning/planning/value-added-tax.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Value Added Tax

Apptio Planning supports modeling **Value Added Tax (VAT)** for contract line items,
allowing organizations to accurately represent total contract spend, inclusive or exclusive of
tax. VAT is a consumption tax applied to goods and services, and depending on your
organization’s accounting policies, it can be either recoverable or non-recoverable.

This feature enables users to:

- Include VAT as part of total contract costs.
- Track VAT separately from the base contract amount.
- Configure how VAT should be calculated and displayed in contract line items.

## Key Concepts

**Amount**

Represents the pre-tax cost of the contract or line item (e.g., software subscription fee,
hardware lease).

**VAT Rate**

Specifies the tax percentage applied to the base amount.

Examples:

- 0% — Non-taxable
- 10% — Reduced VAT rate (e.g., certain services)
- 20% — Standard VAT rate

**Amount with VAT**

Represents the overall cost inclusive of VAT.

Calculated as: **Amount with VAT**= Amount + (Amount × VAT Rate)

## How VAT is Calculated

VAT is calculated based on the **Location** selected on each contract line item:

- When a contract line item is entered and a **Location** is specified,
- Apptio Planning will **look up the VAT Rate** from the reference data table,
- And automatically calculate the **Amount with VAT** (calculated as: *Amount +
  (Amount × VAT Rate)*)
- VAT is not amortized — only the original (pre-VAT) amount is used for amortization.

Example

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Contract Name** | **Contract Amount** | **VAT Rate** | **VAT Amount** | **Amount with VAT** |
| Software License | $10,000 | 20% | $2,000 | $12,000 |
| Maintenance Contract | $8,000 | 10% | $800 | $8,800 |
| Consulting Services | $5,000 | 0% | $0 | $5,000 |

## Configure Value Added Tax

To enable VAT calculations, go to **Settings → Company Profile** and enable the
**Include Value-Added Tax (VAT)** option. Enabling this setting will automatically
create a **VAT Rates** reference data table.

**Setup Steps**

**Before importing VAT Rates**, ensure your **Location
reference data** includes all relevant locations where VAT should apply.

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

**Apply VAT to Contract Line Items** 

When entering or importing contract
data:

1. Specify the contract **Amount** for each line item.
2. Select a **Location.**
3. The **VAT Rate** automatically populates based on your configured VAT Rates.
4. Apptio Planning calculates the **Amount with VAT** automatically**.**
