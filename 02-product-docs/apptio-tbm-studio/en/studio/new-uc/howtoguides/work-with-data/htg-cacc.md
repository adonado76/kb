---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How-To Guide 2: Control Access with User Mapping"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Data Security"
source_path: "studio/new-uc/howtoguides/work-with-data/htg-cacc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How-To Guide 2: Control Access with User Mapping

## Objective

Create and manage mapping tables that define which users can access which data, enabling
granular row-level security controls.

## When to Use

Before implementing RLS on any data table. Also use when adding new users to the system,
when organizational boundaries change, or when implementing different access tiers (e.g.,
regional vs. global access).

## Time Estimate

20-30 minutes for initial setup; 5-10 minutes for updates

## Prerequisites

- Access to the Row-Level Security project
- List of users and their access permissions
- Understanding of the data dimensions you want to filter (e.g., business units, cost
  centers)

## Step 1: Plan Your Mapping Table Structure

Before creating tables, plan your access control strategy:

- **Identify the security dimension:** What column(s) in your data will you filter on?
  Common examples: Business Unit, Cost Center, Region, Department.
- **Determine access patterns:** Will some users have restricted access while others
  have full access? Do any users need access to multiple values?
- **Decide on table organization:** You may need multiple mapping tables for different
  access scenarios (e.g., one for standard users, one for "full access" users).

A mapping table requires only two columns:

|  |  |  |
| --- | --- | --- |
| **Column** | **Description** | **Example** |
| User ID | The user's login email. Must exactly match the user name in the Users table. | bob@acme.com |
| Item | The value the user can access, as it appears in your data tables. | BU 2 |

Tip: You don't need to worry about the table name or column names at this stage.
When you configure RLS filters, you'll select the appropriate table and columns from
dropdowns.

## Step 2: Create Your Mapping Table File

Prepare your mapping table as a CSV or Excel file outside TBM Studio:

1. Open your spreadsheet application (Excel, Google Sheets, etc.).
2. Create columns for User ID and the item(s) users can access.
3. Enter one row for each user-to-item mapping. If a user has access to multiple items,
   include multiple rows for that user.
4. Save the file as CSV or Excel format.

**Example: Standard Business Unit Access Table**

|  |  |
| --- | --- |
| **User ID** | **BU** |
| bob@acme.com | BU 2 |
| rachel@acme.com | BU 1 |
| rachel@acme.com | BU 3 |
| tom@acme.com | BU 1 |
| tom@acme.com | BU 2 |
| tom@acme.com | BU 3 |

*In this example, Bob sees only BU 2 data, Rachel sees BU 1 and BU 3, and Tom sees all
three business units.*

**Example: Full Access Table (for users who should see everything)**

|  |  |
| --- | --- |
| **User ID** | **Is Admin** |
| sally@acme.com | Yes |
| director@acme.com | Yes |

*This separate table is used with OR logic in RLS filters to grant full access without
listing every possible BU value.*

## Step 3: Upload the Mapping Table to the RLS Project

1. Open the **Settings** menu and click **Configure Row-Level Security**.
2. In the Row-Level Security project, click **New** > **Table**.
3. Enter a descriptive name for the table (e.g., "BU Access" or "Cost Center
   Permissions").
4. Select **Upload File** and choose your prepared CSV or Excel file.
5. Review the column detection. Ensure User ID and Item columns are correctly
   identified.
6. Click **Create** to upload the table.

## Step 4: Verify the Upload

1. Open the uploaded table from the Project Explorer.
2. Review the data to ensure all user IDs and items appear correctly.
3. Verify column data types are appropriate (typically Label/Text for both columns).
4. Check in the table to make it available for RLS configuration.

## Alternative: Load Mapping Tables via DataLink

For organizations with many users or frequent permission changes, you can automate mapping
table updates using DataLink (Classic):

1. Navigate to your DataLink (Classic) instance.
2. Select your desired agent and connector.
3. In the **Project** section, type "Users" to target the Row-Level Security
   project.
4. Complete the configuration as you would for any DataLink run.

## Step 5: Update Mapping Tables When Access Changes

User access permissions change over time. Here's how to maintain your mapping tables:

**Adding a new user:**

- Add new row(s) to the mapping table with the user's email and their permitted
  items.
- If using file upload, re-upload the complete updated file.

**Changing a user's access:**Modify the rows for that user (add new item rows, remove
old ones) and re-upload.

**Removing a user's access:**Remove all rows for that user from the mapping table.

## Expected Results

- Mapping table(s) appear in the Row-Level Security project's Project Explorer.
- Tables contain accurate user-to-item mappings.
- Tables are available for selection when configuring RLS steps on data tables.

## Common Pitfalls and Troubleshooting

**User ID mismatch:**User IDs must exactly match the user names in the Users table.
Check for typos, extra spaces, or case differences.

**Item value mismatch:**Item values must exactly match the values in your data tables.
If your data has "Business Unit 1" but the mapping table has "BU 1", RLS won't work
correctly.

**Missing full-access users:**If you add new items (e.g., a new business unit), users
granted access through the standard mapping table won't automatically see the new data
unless you update their entries. Consider using a separate "full access" table for users who
should always see all data.

**Parent topic:** [Data Security](../../../../studio/new-uc/howtoguides/work-with-data/data-security.html)
