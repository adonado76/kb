---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Set Up Editable Table Publishing"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Manual Data Entry"
source_path: "studio/new-uc/howtoguides/work-with-data/setup-et-publish.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Set Up Editable Table Publishing

**Objective:** Configure how user-entered data from editable tables flows into transform
tables and ultimately your cost model, including manual, scheduled, and automated
publishing.

**When to Use**

- After creating editable tables that need to feed transform tables
- When establishing automated data update rhythms
- For collaborative forecasting or planning scenarios
- To enable business users to update model inputs without IT intervention

**Why this matters**: Editable tables exist outside the standard transform pipeline.
Publishing moves user-entered data into transform tables where it can be used in calculations
and allocations. Without proper publishing configuration, user updates remain isolated and
don't affect the model.

## Prerequisites

- An editable table (blank or enriched) already created with defined columns
- Understanding of when data should update (ad-hoc, daily, weekly, monthly)
- Knowledge of which time periods need data
- Admin or builder permissions for scheduling

## Time estimate

15-25 minutes

## A. Create a Transform Table from Your Editable Table

1. **Create the transform table**
   - Navigate to **Data Studio**
   - On the **Home** tab, select **New > Table**
   - Enter a name for the transform table (e.g., "Vendor Categories Transform")
   - Click **OK**
2. **Select Editable Table as source**
   - In the **Create Table** popup, select the **Editable Table** tile
   - In the **Editable Table** dropdown, select your editable table name
3. **Choose initial publish method**
   - **Upload Method:** Select **Replace** (new publishes completely replace
     existing data - most common)
   - Select a **Recurring Publish Schedule** from the dropdown, or use "Default - No
     Recurring Update"
   - Click **OK**
4. **Save and check in**
   - Click **Save** on the **Home** tab
   - Click **Check In**

## B. Manually Publish from TBM Studio

Use this method when you want to control exactly when data updates.

1. **Navigate to your transform table**
   - In **Project Explorer**, locate the transform table sourced from your editable
     table
   - Check out the table if needed
2. **Access the Editable Table step**
   - Click **Steps > Editable Table** in the pipeline
   - You'll see time period placeholders for each period defined in your project
3. **Publish for a specific period**
   - Right-click on the period you want to update (e.g., "Jan 2025")
   - Select **Update This Period**
   - The system publishes current editable table data to that period
4. **Verify and check in**
   - Click the **Table** step and verify data appears correctly
   - Click **Check In**

## C. Manually Publish from Reports

Users with appropriate permissions can publish editable table changes directly from
reports.

**Prerequisites:** User needs **Dev access** and **Stage access** (TBM Studio or
Admin access not required).

**User workflow:**

1. Open a report containing the editable table
2. Make desired changes to the data
3. Click **Save** to save changes to the editable table
4. Click **Publish** at the bottom of the report
5. Confirm the publish action in the warning popup
6. Enter a description in the **Check In** modal
7. Click **Check In**

Important: When publishing from a report, ALL editable table changes publish, not
just rows visible in the current report view. If multiple users are editing different
sections, one user's publish updates all changes.

## D. Set Up Automatic Publishing Schedules

Automatic publishing enables regular, unattended data updates.

1. **Enable recurring publish feature** (if not already enabled)
   - Navigate to **Project** tab > **Enable Features** (12.11.7) or **Project
     Settings** (12.11.8+)
   - Select **Enable Recurring Publish for Transform Tables**
   - Click **OK**
2. **Access recurring publish configuration**
   - Navigate to **Build** tab > **Recurring Publish**
   - You'll see two tabs: **Transform Table** and **Recurring Schedules**
3. **Create a new schedule**
   - Select the **Recurring Schedules** tab
   - Click **Add Schedule**
4. **Configure schedule settings**
   - **Schedule Name:** Enter a descriptive name (e.g., "Labor Mapping - Daily")
   - **Recurrence:** Select frequency (Hourly, Daily, Weekly, or Monthly)
   - **Publish To Period:** Select which time period receives the data (Current Month,
     Previous Month, Specific Period, etc.)
   - **Enable:** Check to activate the schedule
   - **Auto Promote to Production** (12.11.10+): Check to automatically promote
     published data to production
5. **Save and assign the schedule**
   - Click **Save**
   - Switch to the **Transform Table** tab
   - Locate your transform table and assign the new schedule

## Expected Results

After configuring publishing:

- **Manual publishing:** Editable table data flows into transform tables when you
  explicitly trigger publishing
- **Report-based publishing:** Business users can update model inputs without Studio
  access
- **Scheduled publishing:** Data updates automatically at defined intervals
- **Auto-promotion** (if enabled): Changes flow to production without manual
  intervention

## Common Pitfalls

|  |  |
| --- | --- |
| **Issue** | **Solution** |
| **Published data doesn't appear in transform table** | Verify the time period you're viewing matches the period you published to. Check in both the editable table and the transform table. Ensure no errors exist in the editable table data. |
| **Schedule doesn't run as expected** | Verify Enable checkbox is selected on the schedule. Check Last Publish Date & Time - if it shows "Initial," the schedule hasn't run yet. Verify start time and timezone are correct. |
| **Multiple users editing causes data overwrites** | This is expected behavior - last publish wins. Implement governance: assign different users to different sections. Use row-level security to partition editing responsibilities. |
| **Auto-promotion pushes bad data to production** | Disable auto-promotion for tables requiring manual validation. Implement data validation rules to catch errors before publishing. |

## What's Next

After setting up publishing:

- [Create reports for data entry](../create-reports/report-basic.html)
- [Apply row-level security](htg-arls.html)
- [Integrate with cost model](../build-cost-model/model-basics.html)
- Set up promotion governance (Section 6.1)

**Parent topic:** [Manual Data Entry](../../../../studio/new-uc/howtoguides/work-with-data/manual-data-entry.html)
