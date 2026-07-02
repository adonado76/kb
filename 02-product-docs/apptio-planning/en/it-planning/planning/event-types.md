---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Event Types"
breadcrumb:
  - "Planning"
  - "Workflows and Collaboration"
  - "Change History"
source_path: "it-planning/planning/event-types.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Event Types

Change History captures a wide range of system events within Apptio Planning, allowing
you to review who did what, when, and how. Each event is categorized by type, area, container,
item type, and attribute changes.

Note: Admin or Budget Process Owner roles are required to access Change History.

Below is a summary of the key event categories.

## 1. Plan Management Events.

These relate to major plan lifecycle changes.

- **Create Plan** — A new plan was created.
- **Rename Plan** — The plan name was changed (old name → new name).
- **Delete Plan** — A plan was removed.
- **Archive/Restore Plan** — Plan was archived or brought back.
- **Finalize/Reopen Plan** — A plan moved to Final state or back to Open.
- **Submit/Approve/Reject Cost Object** — Status changes for individual departments
  or cost objects.

## 2. Line Item Events

These events track changes to individual lines in your plan.

- **Add Line Item** — A new line item was added.
- **Update Line Item** — An existing line item was updated (shows “before” and “after”
  values).
- **Delete Line Item** — A line item was removed.
- **Import/Export Line Items** — Bulk upload or download actions.

## 3. Actuals & Spend Management Events

These capture the import/export of actuals data and spend management operations.

- **Import Actuals** — Actual data was uploaded into a plan.
- **Export Actuals** — Actuals data was exported for reporting or integration.

## 4. Configuration & Reference Data Events

These relate to changes in the underlying data model or setup.

- **Add/Update/Delete Column Configuration** — Layout or schema column was
  added/modified/removed.
- **Change Identifier** — A find-and-replace operation on a dimension code or
  identifier across plans.
- **Publish/Revert/Import/Export Reference Data** — Actions taken on dimensions like
  Departments, Accounts, Asset Classes, etc.
- **Add/Update/Delete Custom Lists or Dimensions** — Modifications to custom
  dimension structures.

**Parent topic:** [Change History](../../it-planning/planning/change-history.html "Change History provides an audit trail of key actions performed within your planning environment. It allows organizations to maintain transparency, support compliance requirements, and troubleshoot planning issues by tracking who changed what, when, and how.")
