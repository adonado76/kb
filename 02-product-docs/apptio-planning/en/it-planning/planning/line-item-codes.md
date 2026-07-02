---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Line-Item Codes"
breadcrumb:
  - "Planning"
  - "Configuration and Administration"
source_path: "it-planning/planning/line-item-codes.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Line-Item Codes

Note: *Admin or Budget Process Owner roles are required to manage line item codes.*

**Line Item Codes** provide a unique identifier for every line item created in key
Planning tables. These codes make it easier to track changes, troubleshoot updates, and
reference specific lines across submitted plans, snapshots, and Event Log history.

Codes apply to the following line item tables:

- **Financials** (Summary and Other tabs)
- **Asset**
- **Contract**
  - **Labor**
- **Labor Activity**

## How Line Item Codes Work

Each Line Item Code is made up of two parts:

1. **Prefix** – identifies the line item type
2. **Numeric Code** – a system-generated unique number within the plan

Apptio Planning automatically assigns the numeric portion when a new line item is
created.

Baseline Plans

When creating a new plan from an existing plan:

- You may copy all Line Item Codes from the source plan, or
- Generate new Line Item Codes

For details on plan creation, see [Creating Plans](create-plan.html) .

## Default Prefixes

Each line item type has its own default prefix:

|  |  |
| --- | --- |
| **Line Item Type** | **Default Prefix** |
| Financials | **F-** |
| Asset | **A-** |
| Contract | **C-** |
| Labor | **L-** |
| Labor Activity | **LAP-** |

## Changing a Line Item Code Prefix

Changes to line item code prefixes apply across all plans.

1. Navigate to **Configuration** → **Line Item Code Prefix**.
2. Select the **Line Item Type** you want to update.
3. The **Edit Prefix** dialog opens.
4. Enter a new prefix, following these rules:
   1. Must be **1–10 characters**
   2. Cannot contain **digits**
   3. Cannot be **empty**
5. Select **Save**.

Changes take effect immediately for all plans in the tenant.

## Source Line Item Codes

A **Source Line Item Code**identifies the originating line item when a line is created from
another source, such as:

- **Delegations** (for Contracts or Assets) created by the original line item
- **Generated financials** (for Assets, Contracts, Labor, and Labor Activity)

Source Line Item Codes appear when a line item was not created manually. Generated
financials on the Summary tab do not receive Line Item Codes, but they do display a Source
Line Item Code that points back to the originating line item.

If [Summarize Labor Financials](labor-summarization.html "The Summarize Labor Financials feature enables you to determine how your labor cost data is aggregated and presented in the Summary tab. It controls which dimensions (e.g., Cost Center, Account, Location) are used to group and roll up labor cost lines, ensuring you get the right level of visibility and confidentiality for labor financials.") is enabled:

- A single summarized financial line may originate from multiple Labor lines
- In this case, the Source Line Item Code may display **“varies”**

## Source Plan

The **Source Plan**identifies the plan from which a line item was copied.

Example:

- Plan B is created from Plan A
- Plan C is created from Plan B

For line items originally created in **Plan A**, the Source Plan will still show
**Plan A** in both Plan B and Plan C.

## Line Item Codes in Change History

Line Item Codes appear in the **Event Log** under the **Details** column, allowing
you to track the exact line changed in a plan.

The Event Log displays the **prefix used at the time the event occurred**:

- Events **before** a prefix change show the *old* prefix
- Events **after** the change show the *new* prefix

This means two line items of the same type may display different prefixes depending on
when they were modified.

For more details, see [Change History](change-history.html "Change History provides an audit trail of key actions performed within your planning environment. It allows organizations to maintain transparency, support compliance requirements, and troubleshoot planning issues by tracking who changed what, when, and how.").
