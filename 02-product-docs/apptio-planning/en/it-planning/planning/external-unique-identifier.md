---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "External Codes"
breadcrumb:
  - "Planning"
  - "Configuration and Administration"
source_path: "it-planning/planning/external-unique-identifier.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# External Codes

When you import or refresh expense data (e.g. labor, labor activity, contracts, assets)
from external systems (HR systems, vendor databases, etc.), you need a consistent, unique
identifier to match lines in your plan with records in the source system.

By default, Apptio uses its own internal identifiers ([Line
Item Codes](line-item-codes.html)) — but those do not match external systems. The **External Code**
feature solves this gap. When enabled, each expense line can carry an externally defined
unique identifier (like Employee ID, Vendor ID, Position ID, etc.). This ensures imported or
refreshed data maps correctly back into existing lines — avoiding duplicates, missing records,
or data mismatches.

## Enable External Code

Note: *Admin or Budget Process Owner roles are required to perform this task.*

1. Go to **Settings (Gear icon) → Company Profile**.
2. Check **Enable External Code**.
3. Click **Save & Exit**.

   After enabling, the External Code column becomes
   available in expense tables.

## How External Codes Work

- A new column **External Code** becomes available in expense tabs (Labor, Labor
  Activity, Contracts, Assets, Other). It may be hidden by default — you can show it in the
  view.
- In the **Summary** tab, you'll see new columns: **External Code** and **Source
  External Code.**
- **External Code** values entered in the Expenses tabs (Labor, Labor Activity, Contracts,
  Assets, Other) will be summarized in the **External Code** column of the **Summary** tab.
- You can rename the External Code column via **Configuration → Schema** — but this
  applies to all plans.
- External Code can be made **mandatory**in the Schema if you want to enforce that
  every line has a unique external reference.
- When creating a new plan from a baseline, existing External Code values carry over.

Note: Since External Code is used to aggregate generated financials in the Summary tab, the
uniqueness constraint for External Code is not enforced in the Summary and Other tabs. For all other
tabs, the system enforces unique IDs for External Code data.

**Source External Codes**

A **Source External Code**identifies the
originating line item’s External Code when a line is created from another source, such as:

- **Delegations** (for Contracts or Assets) created by the original line item
- **Generated financials** (for Assets, Contracts, Labor, and Labor Activity)

Source External Codes appear when a line item is not created manually. Source External Code
points back to the originating line item.

If [Labor
Summarization](labor-summarization.html "The Summarize Labor Financials feature enables you to determine how your labor cost data is aggregated and presented in the Summary tab. It controls which dimensions (e.g., Cost Center, Account, Location) are used to group and roll up labor cost lines, ensuring you get the right level of visibility and confidentiality for labor financials.") is enabled:

- A single summarized financial line may originate from multiple Labor lines
- In this case, the both the External Code and Source External Code may display **“varies”**

## Permissions for Editing External Code

- Only users granted the **canEditExternalCode** permission may add or modify External
  Code values. By default, users with Admin and Budget Process Owner roles have this
  permission.
- If you want to restrict editing, assign this permission selectively. This prevents
  unauthorized changes or incorrect identifiers being used.

## Using External Code with Data Imports

When importing expense data via CSV:

- Use **Update Data** mode (not Replace All) — this allows row matching based on
  External Code (or Line Item Code when present).
- Matching logic:
  - If a line in the upload matches an existing Line Item Code, updates happen based
    on that.
  - If Line Item Code is missing but External Code matches, the system updates based
    on External Code.
- External Codes must be **unique per expense line type** within a plan. Imports will
  be rejected if duplicates are found.

## Aligning Actuals and Forecast Using External Code

Actuals are imported into Apptio Planning from external ERP systems, while budgets and forecasts
are created within Apptio Planning. This separation can make it challenging to align Actuals with
Forecast or Budget line items.

The **External Code** feature addresses this by allowing you to define user-specific unique
identifiers that can be consistently used across systems. For example, if an *Asset ID* is used
as the External Code in budget or forecast lines, and the same Asset ID exists in Actuals from the
ERP system, it enables accurate alignment of Actuals with Forecasts using this common identifier.

**Steps to Enable and Use External Code for Alignment**

1. Enable the **External Code** feature in the Company Profile.
2. Enable [Actual Summarization Settings](actual-summarization.html "This feature describes how the actuals line items are segregated, based on the columns that are chosen for summarization.")
   **by External Code**.
3. Assign External Codes to expense line items in your plan.
4. Ensure the same External Codes are present in the Actuals data from your ERP system.
5. In the Forecast Plan, navigate to **Expenses > Summary** and group line items by the External
   Code column to view Forecast vs Actuals alignment.

## External Codes in Change History

External Codes appear in the **Event Log** under the **Details** column when a line
with an External Code is changed.

When a line originates from another line (e.g., generated from labor, assets or contracts),
the Source External Code is shown — linking back to the original line.

For more details, see [Change History](change-history.html "Change History provides an audit trail of key actions performed within your planning environment. It allows organizations to maintain transparency, support compliance requirements, and troubleshoot planning issues by tracking who changed what, when, and how.").
