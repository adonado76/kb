---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Spend Management Overview"
breadcrumb:
  - "Planning"
  - "Spend Management"
source_path: "it-planning/planning/spend-management.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Spend Management Overview

Spend Management enables you to manage actual data by importing monthly transactions
into Apptio Planning. By integrating actuals, you can align your plan and forecast models with
real performance, enabling better visibility, variance tracking, and decision-making.

## Sources of Actual Data

- **CSV Import** — Upload actual transactions via CSV files (e.g., from your ERP or GL
  system).
- **Apptio Costing Integration** — Import actual transactions automatically from Apptio
  Costing if configured.
- Regardless of the source, the imported data enters Spend Management and can be used to
  create forecast plans.

## Steps to Import Actuals via CSV

1. Go to **Spend Management → Transactions** from the left navigation.
2. Use the **top navigation bar** to select the time period you want to import actuals
   for.
3. Click **Actions → Import Actuals...** or select **Export Template** to download a
   CSV template.
4. Choose an **Import Type**:
   1. **Replace All Data** — overwrites all existing data in the selected period.
   2. **Append Data** — adds new rows without deleting existing data.
5. Upload your **CSV file**containing the required fields.
6. Click **Import**, then choose **Import** or **Import with Issues** to finalize
   the upload.
7. The imported transactions will immediately appear in the **Transactions table**.

## Steps to Import Actuals from Apptio Costing

1. Verify the data connection is configured in **Settings** (Gear Icon) **→ Apptio
   Costing Integration**.
2. Navigate to **Spend Management → Transactions.**
3. Use the **top navigation bar** to select the time period you want to import actuals
   for.
4. Click **Actions → Import from Apptio Costing...**
5. Click **Import**.
6. The imported transactions will appear in the **Transactions table**.

   For more
   information, see [Import Actuals](import-publish-actuals.html)

## Spend Management Period States

Each accounting period in Spend Management has one of the following states: **New**,
**Open**, or **Final**.

**Open a Period** 

1. Click **Open Month** in the upper-right corner.
2. The period status changes from **New → Open**.

**Finalize a Period** 

1. Click **Close Month** in the upper-right corner.
2. The period status changes from **Open → Final**.

**Reopen a Period**

1. Click **Reopen Month** in the upper-right corner.
2. The period status changes from **Final → New**.

***Behavior Notes***

- **New** and **Open** states function the same — data can be imported or
  modified.
- Once a period is marked **Final**, no further imports or edits are
  allowed—including data automatically imported fromApptio Costing.
- Budget Owners can view transactions for any Departments they have access to,
  regardless of the period state.
- After importing data into a period, if any reference data (e.g., Accounts, Cost
  Centers, etc.) is updated, you must click **Update Reference Data** to apply those
  changes to the period.
- The structure of the **Transactions table** can be managed under **Configuration →
  Schema → Actuals**.
