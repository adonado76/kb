---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "View Updated Line Items"
breadcrumb:
  - "Planning"
  - "Workflows and Collaboration"
source_path: "it-planning/planning/view-upd-li.html"
images:
  - "resources/images/it_planning_images/vuli.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# View Updated Line Items

The **View Updated Line Items** feature allows you to quickly identify what has changed in
a plan since the last **submission** or **snapshot**. When enabled, the system filters
the table to display only the line items that were added, updated, or deleted—making reviews
and approvals faster and more accurate.

This view is available on the **Expenses** page. When a Group Department or multiple
Departments are selected, the updated view compares each leaf Department’s **latest
snapshot** to its **previous snapshot** and displays the differences.

**Key Benefits:**

- Quickly isolate changes from large datasets
- Improve review accuracy by focusing only on modified line items
- Speed up collaboration and approvals by highlighting what needs attention
- Provide transparency into who made changes and when

## How It Works

1. Enable the **View Updated** toggle on the Expenses page.
2. The table immediately refreshes to show only line items that changed since the last
   snapshot.
3. Each displayed line includes an **Action** column describing the type of update,
   along with **Modified By** and **Last Updated** columns to show who made the
   change and when.

   |  |  |
   | --- | --- |
   | **Action** | **Description** |
   | **New** | A new line item was added. |
   | **Updated** | An existing line item was modified. |
   | **Deleted** | A line item was removed. |

![image of updated line items](../../../../../03-media/apptio-planning/resources/images/it_planning_images/vuli.png)

**Additional Notes:**

- **Imported line items** are marked as **New** and display the timestamp and
  username of the import.
- **Generated financials** (Labor, Labor Activity, Contracts, Assets) are marked as
  **Updated** and reflect the latest updates made to their source data.
- Changes applied through **Update Reference Data** or **Update Actuals** donot
  appear in View Updated mode.
- Plans created from a baseline retain the baseline’s **Last Updated** values for
  those items.
