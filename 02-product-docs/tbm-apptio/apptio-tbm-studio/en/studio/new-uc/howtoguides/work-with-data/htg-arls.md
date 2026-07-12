---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How-To Guide 1: Apply Row-Level Security to Tables"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Data Security"
source_path: "studio/new-uc/howtoguides/work-with-data/htg-arls.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How-To Guide 1: Apply Row-Level Security to Tables

## Objective

Configure row-level security on a transform table so users only see rows they are
authorized to view.

## When to Use

When you need to restrict data visibility based on organizational boundaries (e.g.,
business unit, cost center, region, department) or when implementing multi-tenant data
restrictions.

## Time Estimate

30-45 minutes for initial setup; 10-15 minutes for additional tables

## Prerequisites

- A transform table that has been modeled (has a Model step)
- Mapping table(s) uploaded to the Row-Level Security project (see How-To Guide 2)
- Appropriate permissions to edit tables and the Row-Level Security project

## Step 1: Access the Row-Level Security Project

1. Open the **Settings** menu (gear icon in the top navigation).
2. Click **Configure Row-Level Security**.
3. The Row-Level Security project opens. This is a dedicated project that stores all
   mapping tables for your domain.

Tip: The Row-Level Security project is automatically installed when your Apptio
instance is created. It serves all projects in your domain, so mapping tables you create
here can be used across multiple projects.

## Step 2: Verify Your Mapping Tables Exist

Before configuring RLS on your data tables, ensure the mapping tables are in place:

1. In the Row-Level Security project, navigate to the **Project Explorer**.
2. Locate your mapping table(s). You should see tables that contain user IDs and the items
   each user can access.
3. If mapping tables don't exist, see **How-To Guide 2: Control Access with User
   Mapping** to create them before proceeding.

A typical mapping table for business unit access might look like this:

|  |  |
| --- | --- |
| **User ID** | **Business Unit** |
| bob@acme.com | BU 2 |
| rachel@acme.com | BU 1 |
| rachel@acme.com | BU 3 |
| tom@acme.com | BU 1 |

Note: Rachel has access to two business units, so she appears twice in the mapping
table.

## Step 3: Open the Table to Secure

1. Navigate to your working project (not the Row-Level Security project).
2. In the **Project Explorer**, locate the table you want to secure.
3. Check out the table if it isn't already checked out.
4. Double-click to open the table in the transform editor.

## Step 4: Insert a Row-Level Security Step

1. In the transform pipeline panel (left side), right-click where you want to add the RLS
   step.
2. Select **Insert Step** > **Row-Level Security**.
3. The Row-Level Security configuration panel appears.

Tip: Adding a Row-Level Security step will automatically add a Model step if one
doesn't exist. Only Modeled Tables and Editable Tables can have Row-Level Security applied
to them.

## Step 5: Configure the Security Filter

The RLS filter has four fields that create the security rule. Configure each field as
follows:

1. **First field (Column to filter):** Select the column in your data table that
   contains the values to be filtered. For example, if you're filtering by business unit,
   select your "BU" or "Business Unit" column.
2. **Second field (intersects):** Select the mapping table from the Row-Level Security
   project that defines user access permissions.
3. **Third field (Item column):** Select the column in the mapping table that contains
   the values users are permitted to view (e.g., the "Business Unit" column in the mapping
   table).
4. **Fourth field (where user is):** Select the column in the mapping table that
   contains user IDs (e.g., "User ID" or "Email").

This configuration creates a rule: *"Show rows where the data table's [Column] value
matches the mapping table's [Item column] for the current user's ID in [User ID
column]."*

## Step 6: Add Additional Rules (Optional)

You may need multiple rules to handle different access scenarios. For example, you might
want certain users (like finance directors) to see all data regardless of business unit.

1. Click **Add Entry** to create an additional rule.
2. Configure the new entry following the same four-field pattern.
3. Multiple entries use **OR** logic: if any entry is true for a user, they see the
   row.

**Example:** To give "full access" users visibility to all rows, create a second mapping
table (e.g., "BU Full Access") with an "Is Admin" flag set to "Yes" for those users. Add a
formula column to your data table with the value "Yes", then create an RLS entry that
matches this column to the "Is Admin" column where the user appears in the Full Access
table.

## Step 7: Test the Security Configuration

Before saving, verify that your RLS configuration works correctly:

1. In the RLS step, locate the **Preview Filter** field.
2. Enter a user's email address (e.g., "bob@acme.com") to see what data they would
   see.
3. Review the preview pane to verify only the expected rows appear.
4. Test multiple users, including users with restricted access, users with multiple access
   grants, and (if configured) users with full access.

Tip: The impersonate feature is useful for testing in reports. You can view the
report as a specific user to verify the RLS is working correctly.

## Step 8: Save and Check In

1. Click **Save** to save your changes to the table.
2. Check in the table to make the RLS configuration available in staging and
   production.

## Expected Results

- The table now has an RLS step visible in the transform pipeline.
- Users viewing reports that include this table see only rows matching their access
  permissions.
- Aggregations in reports (sums, counts, averages) reflect only the user's filtered
  data.
- The preview filter shows the expected subset of data for each test user.

## Common Pitfalls and Troubleshooting

**User sees no data:**

- Verify the user ID in the mapping table exactly matches the user's login email
  (case-sensitive).
- Check that the values in the mapping table's item column exactly match the values in
  your data table.

**User sees all data (no filtering):**

- Confirm the table has a Model step. RLS only works on modeled tables.
- Verify the RLS step is properly configured and all four fields are set.

**RLS not applied to related tables:**

- Remember that RLS does not inherit. Each table requiring security must have its own RLS
  step configured.

**Parent topic:** [Data Security](../../../../studio/new-uc/howtoguides/work-with-data/data-security.html)
