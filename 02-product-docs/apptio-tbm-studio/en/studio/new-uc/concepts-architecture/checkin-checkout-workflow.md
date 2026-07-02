---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Check-Out and Check-In Workflow"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Build and Deployment Lifecycle"
source_path: "studio/new-uc/concepts-architecture/checkin-checkout-workflow.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Check-Out and Check-In Workflow

In TBM Studio, all elements—including data tables, metrics, perspectives, models, and reports—are
documents. To edit any document, you must first check it out. This exclusive lock mechanism prevents
conflicts when multiple users work on the same project.

**Checking Out a Document**

When you check out a document, you establish an exclusive lock that prevents others from editing
it simultaneously. To check out a document:

1. Select the document in Project Explorer.
2. On the Home tab, in the Document group, click Check Out.
3. A check-out icon appears next to the document name, and the document name will be displayed in
   orange text in the tab at the bottom of the workspace.

While checked out, you can save changes without triggering a recalculation. This lets you make
multiple edits efficiently before sharing them with the team.

**Checking In a Document**

When you check in a document, it releases your lock and triggers a recalculation. Your changes
become visible to others in the Staging environment. To check in a document:

1. On the Home tab, in the Document group, click Check In.
2. The document is submitted to Staging, and calculations begin.

Warning:

Always validate your changes before checking in. Review data tables for errors, verify allocation
impacts, and test affected reports. Poorly validated check-ins can cause performance issues or
incorrect calculations in Staging.

**Undo, Redo, and Revert**

While documents are checked out, you have several options to manage changes:

**Undo and Redo** are useful for rolling back small, discrete changes such as:

- Positioning of reporting elements within a report
- Discrete edits to element configuration (button text, HTML contents)
- Edits to formulas in a table's formula step

**Revert Changes** abandons all changes to selected checked-out documents and discards the
check-out entirely. To revert:

1. On the Home tab, in the Document group, click Revert Changes.
2. Select the documents you want to revert and click Revert Check Out.

**Best Practices for Check-In**

Following a consistent check-in discipline helps maintain project stability:

|  |  |
| --- | --- |
| **Practice** | **Why It Matters** |
| Review data before upload | Confirm files have content, are correctly delimited, and have expected columns |
| Enable cardinality validation | Catches data quality issues early before they propagate through the model |
| Validate allocation impacts | Changes to data or configuration can affect allocations in unexpected ways |
| Test affected reports | Verify reports load correctly and show expected values |
| Coordinate check-ins | Agree on check-in times (e.g., lunch and end of day) to minimize calculation queuing |
| Don't check in during promotions | Ensure no one is waiting to promote to Production before your check-in |
