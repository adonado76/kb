---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Contract Extensions"
breadcrumb:
  - "Planning"
  - "Contract Planning"
source_path: "it-planning/planning/vrbl-cntc-ext-adj.html"
images:
  - "resources/images/it_planning_images/2ndlast-ve.png"
  - "resources/images/it_planning_images/last-var-ext.png"
  - "resources/images/it_planning_images/new-ext.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Contract Extensions

Apptio Planning supports extending contracts beyond their original end date — with
different capabilities depending on whether you are using the **Legacy View** or the **New
View**.

## Legacy View (Basic Extension)

In the legacy experience, when you click **Extend** and enter an **Extension Adjustment
(%)**, Apptio Planning will:

- Increase the **contract amount** by the specified percentage
- Automatically **extend the contract to the end of the plan**
- Apply the **adjustment rate** across the full extension period

This provides a simple uplift but does **not** support compounding or multiple staged
extensions.

Steps to Extend a Contract (Legacy View) 

1. Navigate to **Expenses → Contracts** tab
2. In the contract line item, check the **Extend box**.
3. Enter the **Extension Adjustment (%)** to increase the contract amount for the
   extension period.
4. Select the **Extension Offset** value as either **Next Day** or **Next Month**. This
   option is configurable when the Contract Amortization Method is set to **Straight-Line by
   Duration** or **Straight-Line by Duration Custom Calendar**.
   1. **Next Day** – The contract extension begins on the day immediately following the existing
      contract end date.
   2. **Next Month** – The contract extension begins in the month following the existing contract
      end date.

## New View (Compounding Extensions)

The new view introduces flexible, compounding extensions. You can now:

- Apply **multiple contract extensions**, each with its own rate
- Choose whether adjustments should **compound over time**
- Precisely model multi-year renewal patterns or price escalations

This allows more realistic modeling of real-world contracts — especially those with annual
renewals, tiered pricing, or escalating vendor rates.

Steps to Extend a Contract (New View) 

1. Go to **Expenses → Contracts** tab with New View enabled.
2. In the contract line item, check the **Extend box**.
3. This enables the **Extend button** in the **Extension Settings** column — click
   it.
4. The **Configure Extension** dialog will appear. Enter the following:
   1. **Extend Until** — the new contract end date
   2. **Extension Adjustment (%)** — uplift rate to apply to the extension
   3. **Extension Offset**
      - Configurable if the Contract Amortization method is **Straight Line By Duration** or
        **Straight Line Duration Custom Calendar**
      - **Next Day** – The contract extension begins on the day immediately following the existing
        contract end date.
      - **Next Month** – The contract extension begins in the month following the existing contract
        end date.
   4. **Enable Compounding** — toggle on if each extension should build on the prior
      adjusted value
5. Click **Apply** to generate the extension schedule.
6. The system will create an extension table showing calculated start/end dates.
7. You may optionally **add comments for each extension period**.
8. If **compounding is enabled**, you can adjust the rate individually per extension.
9. Click **Submit** to finalize and apply the extension.

![image of new extensions](../../../../../03-media/apptio-planning/resources/images/it_planning_images/new-ext.png)

Note: If you extend a contract using the New View and then switch back to the Legacy
View, modifying the extension in Legacy View will revert it to the basic (non-compounding)
extension model — any compounding extensions previously configured will be lost.

Steps to Import and Export Contract Extensions (New View)

***Export Contracts & Extensions***

1. **Switch to the New View**. (Contact your Admin if this is not enabled.)
2. Go to **Expenses → Contracts** tab.
3. Open the **Ellipses table****menu → Export contracts… → Export for
   Re-Import**
4. You will receive **two files**:
   1. **\*\_Contract.csv** — core contract data
   2. **\*\_Contract-Extensions.csv** — all extension periods and adjustment rates

***Import Contracts***

Contract details and extension details must be imported separately:

**Step 1 – Import Contract Details**

1. Go to **Expenses → Contracts** tab with New View enabled.
2. Open the **Ellipses (...) menu** on the table→ **Import contracts... →
   Contract Details**
3. Choose **Replace All** (clears all contracts) *or***Update Data**
   (updates matching Line Item Code / External Code)
4. Click **Import**

**Step 2 – Import Contract Extension Details**

1. Open the **Ellipses (...) menu** on the table→ **Import contracts... →
   Extension Details**
2. Choose **Replace All** (clears all contract extensions) *or***Update
   Data** (updates matching Line Item Code / External Code)
3. Click **Import**

Note: Importing contract details alone does *not* import extensions.
Extensions must always be uploaded separately.

![image of variable extension](../../../../../03-media/apptio-planning/resources/images/it_planning_images/2ndlast-ve.png)

***Contract Extension File Format***

Each row should include:

- **Line Item Code** — links extension to a specific contract
- **Extension Number** — in sequential order (1 = first extension, 2 = second,
  etc.)
- **Contract Extend Until** — must be the **same for all extensions of that
  contract**
- **Enable Compounding** — TRUE to allow multiple adjusted periods
- **Adjustment Percentage** — entered as a decimal (e.g. 0.05 for 5%)
- **Extension Comment** — optional notes per extension

![image of last var extension](../../../../../03-media/apptio-planning/resources/images/it_planning_images/last-var-ext.png)

**Optional:** Extension Start Date — if omitted, Apptio will calculate it
automatically.
