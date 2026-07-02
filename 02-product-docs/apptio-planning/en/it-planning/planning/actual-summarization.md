---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Actual Summarization Settings"
breadcrumb:
  - "Planning"
  - "Spend Management"
source_path: "it-planning/planning/actual-summarization.html"
images:
  - "resources/images/it_planning_images/act-sum.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Actual Summarization Settings

This feature describes how the actuals line items are segregated, based on the columns
that are chosen for summarization.

Note: Admin or Budget Process Owner roles are required to modify Actual Summarization
settings.

When creating a Forecast plan, you can choose how actuals should be summarized (aggregated)
before they are imported into the plan. Actual Summarization allows you to control the level
of granularity at which actuals are brought in — ensuring the data aligns with how your team
plans and analyzes spend.

## What it does

Actual Summarization groups actuals by the dimensions you select, then aggregates the
actual line items accordingly.

This is especially useful if your actuals are more granular than your planning model — for
example, if your actuals include transaction-level detail, but your forecast plan only needs
to be summarized at a Department and Account level.

You can summarize actuals using standard dimensions (e.g., Department, Account, Cost
Center) and/or custom dimensions, as long as those dimensions exist in both the Actuals and
Financials schemas.

## How to Configure Actual Summarization

- Go to **Settings (Gear icon)** → **Company Profile**.
- In the **Summarize Actuals** section, select the **dimensions** you want actuals
  to be aggregated by.
- Click **Save and Exit**.

**Important Notes:**

- These settings will apply only to newly created plans going forward.
- For existing plans, you must create a new plan to apply the updated summarization
  settings.
- Dimensions are available for summarization only if they exist in both the Actuals and
  Financials schemas.

![image of actual summarization](../../../../../03-media/apptio-planning/resources/images/it_planning_images/act-sum.png)
