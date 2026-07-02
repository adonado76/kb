---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How-To Guide: Configure Published Tables"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Data Export"
source_path: "studio/new-uc/howtoguides/work-with-data/htg-config-pt.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How-To Guide: Configure Published Tables

**Objective:** Create and configure a Published Table that external systems can query for
cost model data

**When to use:** When you need to provide a stable, automatically refreshed dataset to
external BI tools, data warehouses, or other Costing & Planning projects

**Prerequisites:**

- TBM Studio version 12.11.3 or later
- Administrator permissions to create and modify Published Tables
- A completed cost model with calculated data
- (Optional) An existing report table to convert

**Time estimate:** 15-20 minutes

## Understanding Published Tables

Published Tables are dedicated export entities in TBM Studio, distinct from reports and
transform tables. They solve a common problem: before Published Tables, users had to create
locked reports to export data, which added load to the staging calculation process and
complicated permissions management.

Published Tables offer several advantages:

- Eliminate the need to manage report permissions for data export
- Support export as soon as the development calculation finishes
- Provide a stable schema that external systems can rely on
- Remove dependency on the reporting surface for data egress

Important: Published Tables reflect deployed model values only—they do not expose
draft values from development branches. Data updates whenever a staging or production
calculation completes successfully.

## Method 1: Create a New Published Table

Follow these steps to create a Published Table from scratch:

1. Navigate to the **Home** tab and select **New**.
2. Select **Published Table** from the menu.
3. In the dialog that appears:
   - Enter a descriptive **Name** for the table (e.g., "Monthly Cost Summary -
     PowerBI")
   - Select a **Category** to organize the table in Project Explorer
   - Click **OK**
4. Locate the newly created table in Project Explorer under the specified category.
5. Configure the Published Table by defining its data content:
   - Select the source model object or transform table
   - Choose which columns to include
   - Apply any formatting or casting rules as needed

Note: The configuration process mirrors how you would configure a report table. For detailed
instructions on table configuration options, see the Tables in Reports section of the Report
Studio documentation (Section 5.3).

- Check in your changes to make the Published Table part of your project.

## Method 2: Create from an Existing Report Table

If you already have a report table configured with the data you want to export, you can
convert it directly to a Published Table:

1. Navigate to the report containing the table you want to export.
2. Right-click on the report table.
3. Select **Create Published Table** from the context menu.
4. In the dialog:
   - Enter a **Name** for the new Published Table
   - Select a **Category**
   - Click **OK**
5. The new Published Table appears in Project Explorer and inherits the configuration from
   the original report table.

Tip: This method is ideal when you've already perfected a report table's column
selection and formatting—it saves you from recreating that configuration.

## Configure Pre-Calculation Settings

By default, Published Tables are pre-calculated during the build process, ensuring data is
ready immediately when requested. You can adjust this behavior:

1. In Project Explorer, check out the Published Table.
2. Select the **Published Table** tab to view its properties.
3. Locate the **Active** setting:
   - **Checked (default):** The system pre-calculates the table during builds. Data is
     ready immediately when the API URL is called.
   - **Unchecked:** The system does not pre-calculate. The API still works, but the
     first request triggers calculation, which may delay the response.
4. Check in your changes.

**When to disable pre-calculation:** Consider disabling pre-calculation for Published
Tables that are rarely accessed or used only for troubleshooting. This reduces build time
for your primary exports.

## Retrieve the API URL for a Published Table

Once configured, retrieve the URL that external systems will use to access the data:

1. In Project Explorer, right-click on the **Published Table**.
2. Select **Show API URL** from the context menu.
3. Copy the URL from the dialog.
4. Use this URL in:
   - DataLink connections for scheduled data extraction
   - Custom scripts for programmatic access
   - BI tool data source configurations

Tip: The API URL remains stable as long as the Published Table name doesn't
change. If you rename the Published Table, update all consuming systems with the new
URL.

## Expected Results

After completing these steps:

- Your Published Table appears in Project Explorer under its assigned category
- Data refreshes automatically after each successful staging or production
  calculation
- External systems can retrieve data using the API URL in CSV or JSON format
- Schema remains stable unless you explicitly modify the Published Table
  configuration

## Common Pitfalls

**Data not appearing in Published Table** - Published Tables only reflect deployed model
values. If you're working in a development branch, data won't appear until you promote
changes and run a calculation.

**Slow first request** - If pre-calculation is disabled, the first API request triggers
calculation. For large datasets, this can take significant time. Enable pre-calculation for
frequently accessed Published Tables.

**Schema changes breaking downstream systems** - When you modify column selections in a
Published Table, downstream systems may break. Communicate schema changes to all data
consumers before making modifications.

**Errors blocking refresh** - If upstream transform tables have errors or data mismatches,
the Published Table refresh will fail. Check the calculation logs and resolve upstream
issues first.

**Parent topic:** [Data Export](../../../../studio/new-uc/howtoguides/work-with-data/data-export.html)
