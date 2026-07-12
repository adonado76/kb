---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Build Report Collections"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Report Customization"
  - "Build Report Collections"
source_path: "SSWRJM/studio/new-uc/howtoguides/create-reports/build-rc.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Build Report Collections

Objective: Create and manage report collections that group related reports for easy navigation and access control.

When to use: Use report collections when you want to:

- Group related reports (for example, all monthly finance reports)
- Provide intuitive navigation between reports on similar topics
- Control access by role at the collection level
- Organize reports by department, function, or time period

Prerequisites:

- Admin role (only Admins can create or delete collections)
- Reports already created that you want to group
- Understanding of which user roles should access each collection

Time estimate: 10-15 minutes to create a collection; 2-5 minutes per report to add

## Understanding Report Collections

Report collections group related reports so users can easily navigate between them. When users access a report in a collection, they see a report collection navigator at the top of the report—a horizontal bar showing all reports in that collection with easy one-click navigation.

Key points:

- Only Administrators can create and delete report collections
- Collections are project-wide once created
- Any user with appropriate permissions can add or remove reports from existing collections
- A report can belong to only one collection at a time
- Administrators can set role-based permissions at the collection level
- You can hide reports in a collection without deleting them—useful for reports not yet ready

Step-by-Step: Create a Report Collection

1. On the Project tab, in the Project Data group, click Report Collections .
1. In the Manage Report Collections dialog, click Add Collection .
1. A new entry appears named "New report collection" and is selected in the Selected Collection field.
1. To rename the collection, click the entry in the list, then click the name in the Selected Collection field and type a new name (for example, "Monthly Finance Package" or "Executive Dashboards").
1. Click outside the name field to save.

## Step-by-Step: Add a Report to a Collection

1. In the Project Explorer , navigate to and select the report you want to add.
1. On the Report tab, in the Grouping group, click Assign to Collection .
1. From the drop-down list, select the collection where you want to add the report.

The report is now part of the collection. When users view the report, they'll see the collection navigator.

Note: A report can only belong to one collection. If you assign it to a new collection, it's removed from the previous one.

## Step-by-Step: Remove a Report from a Collection

Method 1: From the Report

1. Navigate to the report and check it out.
1. On the Report tab, in the Grouping group, click Assign to Collection .
1. In the menu, click the red X next to the collection name.

Method 2: From Manage Report Collections

1. On the Project tab, click Report Collections .
1. Select the collection from the Available Collections list.
1. Find the report in the list on the right.
1. Click the red X on the right side of the report's row.

## Step-by-Step: Hide or Show Reports in a Collection

You may want to temporarily hide a report—for example, an out-of-the-box report you haven't configured yet, or a report under development.

To hide a report:

1. On the Project tab, in the Project Data group, click Report Collections .
1. Select the collection containing the report.
1. Find the report in the list on the right.
1. Clear the Show in navigator checkbox next to the report name.
1. Click Close .

To show a hidden report: Follow the same steps, but select (check) the Show in navigator checkbox.

Important: Never delete out-of-the-box reports from a collection. Instead, hide them until you're ready to enable them.

## Example: Creating a Monthly Reporting Package

A common use case is grouping all reports that finance teams review each month:

1. Create a collection named "Monthly Finance Package".
1. Add these reports to the collection: Cost Summary by Business Unit, Vendor Spend Analysis, Budget vs. Actual Variance, IT Tower Cost Breakdown, Chargeback Detail Report.
1. Arrange the reports in logical order (users see them in the order shown in the collection).
1. If the Chargeback Detail Report isn't ready yet, hide it by clearing Show in navigator .

Now when finance users open any of these reports, they see the collection navigator and can easily move between all monthly reports.

## Common Pitfalls

- Forgetting collection limits visibility: If a report belongs to a collection, users who can't access that collection won't see the report—even if they have permission to the report itself.
- Deleting OOTB reports: Never delete out-of-the-box reports; hide them instead. Deleting can cause upgrade issues.
- Disorganized collections: Too many reports in one collection makes navigation cumbersome. Consider splitting large collections by sub-topic.
