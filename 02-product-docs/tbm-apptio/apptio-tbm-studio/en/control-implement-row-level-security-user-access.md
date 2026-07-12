---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Implement Row-Level Security for User Access"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Manage Users and Permissions"
  - "Access Control"
  - "Implement Row-Level Security for User Access"
source_path: "SSWRJM/studio/new-uc/howtoguides/manage-users-permission/implement-rls.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Implement Row-Level Security for User Access

| Objective | Configure user-to-data mappings so users see only the rows they are authorized to view |
| --- | --- |
| Objective | Configure user-to-data mappings so users see only the rows they are authorized to view |
| Time Estimate | 30-45 minutes for initial setup; ongoing maintenance as users change |
| Prerequisites | Admin or Power User role; users configured in the project; understanding of your data segmentation requirements |

## When to Use This Procedure

Use row-level security when users should see different subsets of data based on their identity. Common scenarios include business unit managers viewing only their department's costs, regional managers accessing only their regional data, or distributed cost center owners reviewing their own budgets.

This guide focuses on the user-mapping aspect of RLS. For the complete technical implementation including transform pipeline configuration, see Section 3.1.4: Data Security .

## Understanding RLS Architecture

Row-level security in TBM Studio consists of two main components:

- Mapping tables: Define which users can access which data items (e.g., user bob@acme.com can see Business Unit 2)
- RLS filters: Applied to transform tables to enforce the mapping rules when users view reports

Mapping tables are stored in the Row-Level Security project, which is installed automatically when a new TBM Studio instance is created and applies across all projects in a domain.

## Steps

## Step 1: Plan Your RLS Structure

Before creating mapping tables, determine:

- What dimension will you filter on? (e.g., Business Unit, Cost Center, Region)
- Which users need access to which values of that dimension?
- Are there users who need access to all data? (You may need a separate "full access" mapping table)

## Step 2: Create the Mapping Table

1. Open the Settings menu and click Configure Row-Level Security .
1. Create a new table (or prepare one externally in Excel/CSV format) with two required columns: ID: The user ID (email address matching the Users table) Item: The value the user can access (e.g., "BU 2", "North America")
1. Populate the mapping table with user-to-item associations. For example: ID BU bob@acme.com BU 2 rachel@acme.com BU 1 rachel@acme.com BU 3 Tip: If a user needs access to multiple values, include multiple rows for that user (as shown for rachel@acme.com above).
1. Upload the mapping table to the Row-Level Security project.

## Step 3: Create a Full-Access Mapping (Optional)

For users who need to see all data (e.g., executives, finance admins), create a separate full-access table rather than listing every possible value:

| ID | Is Admin |
| --- | --- |
| ID | Is Admin |
| sally@acme.com | Yes |

This approach ensures full-access users automatically see new data items without updating their mapping.

## Step 4: Apply RLS Filters to Tables

Once mapping tables exist, apply them to your data tables. For detailed instructions on configuring RLS pipeline steps, see Section 3.1.4: Data Security .

## Step 5: Test RLS Configuration

- Use the Preview Filter in the RLS step to test what specific users will see
- Use the Impersonate feature to view reports as a specific user
- Verify that users with full access see all data
- Verify that restricted users see only their authorized data

## RLS Behavior Across Features

Understanding how RLS behaves across different TBM Studio features:

- Transform tables: RLS filters rows before data appears in any downstream usage
- Editable tables: RLS restricts which rows users can see AND edit. Users can only modify visible rows.
- Reports: Aggregations reflect only the filtered data visible to the user
- Publishing: When users publish editable tables, hidden rows are preserved—not deleted
- Model overview reports: Each tier reflects only the RLS applied to that specific tier; values may not sum to totals shown at higher tiers

## Common Pitfalls

- Mismatched user IDs: The ID column in your mapping table must exactly match the user ID in the Users table. Even minor differences (case sensitivity, extra spaces) cause RLS to fail.
- Admin bypass: Do not rely on RLS to secure data from Admin users. They can access Studio mode and modify RLS configuration.
- Allocated costs: If costs are allocated from restricted areas to visible areas, users may see costs that originated outside their authorized scope.
- Missing RLS on drill tables: Ensure RLS is configured on all tables that appear in drill-through reports.

## Related Tasks

- Configure RLS pipeline steps
- Load RLS data via DataLink (Section 5.1)
- Understand the Security Model (Section 4.4)
