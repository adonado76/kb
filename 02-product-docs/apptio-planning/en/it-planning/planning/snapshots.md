---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Snapshots (Versioning)"
breadcrumb:
  - "Planning"
  - "Workflows and Collaboration"
source_path: "it-planning/planning/snapshots.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Snapshots (Versioning)

A snapshot is a read-only, time-stamped copy of a plan version. Snapshots preserve historical
views of a plan so you can compare submitted, approved, or otherwise finalized plans against
earlier versions.

Snapshots are especially useful for:

- Tracking changes between submissions
- Comparing current budget values to prior versions
- Auditing updates over the planning cycle

Snapshots are **non-editable** and are only available for **leaf Departments**.

## When Snapshots Are Created Automatically

Apptio Planning automatically creates snapshots during key points in the planning process:

- When a plan is **submitted**
- When a plan’s status changes from **New → Open**

These automatic snapshots ensure a baseline version is always available for comparison.

## Create a Snapshot Manually

You can create additional snapshots at any time for your own comparison or analysis needs.

**Steps to Create a Snapshot**

1. From the **Plan** menu, select the plan you want to work on.
2. Navigate to **Plan → Expenses**.
3. In the **Department** dropdown, select a **leaf Department**.
4. Open the **Plan Versions** dropdown.
5. Select **Save Snapshot**.
6. Enter a **name** for the snapshot.
7. Click **Create**.

Your snapshot is now saved and can be accessed at any time.

## Accessing Saved Snapshots

To view existing snapshots:

1. Follow the same navigation path: **Plan → Expenses**.
2. In the **Plan Versions** dropdown, you’ll see all saved snapshots available for the
   selected leaf Department.

Snapshots are always read-only to preserve historical accuracy.

## Using Snapshots for Comparison

Snapshots can be selected when adding **comparisons**on the Expenses page. This allows
you to:

- Compare current values to a previous plan snapshot
- Highlight changes across planning iterations
- Support variance discussions during budget reviews

## Restoring Department to Previous Snapshot Version

You can restore a previous snapshot and make it the current (Latest) version of plan data for a
department. This allows you to quickly recover from unwanted changes and continue planning from a
known, trusted point in time.

Restore a Snapshot as the Latest Version

To restore a snapshot as the latest version, follow the steps below:

1. In the **Expenses** view, navigate to the required **leaf department** using the
   **Departments** dropdown.
2. From the **Plan Version** dropdown, select the **snapshot** you want to restore as the
   latest version.
3. In the **Restore Snapshot** confirmation dialog, enter a **snapshot name**. This name will
   be used to save a copy of the current Latest Version before restoration.
4. Click **Restore**.

**Result**

When the restore operation is performed:

- The existing **Latest Version** is first saved as a **new snapshot** using the provided
  snapshot name.
- Data in the **Latest Version** is then cleared.
- Data from the selected snapshot is copied and set as the new **Latest Version**.

**Note:** This operation cannot be performed if the department is **not in the In Progress
state**.
