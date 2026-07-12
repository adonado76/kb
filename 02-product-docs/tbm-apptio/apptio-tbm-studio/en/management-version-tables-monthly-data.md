---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Version Tables for Monthly Data"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Data Import & Management"
  - "Version Tables for Monthly Data"
source_path: "SSWRJM/studio/new-uc/howtoguides/work-with-data/version-tables-monthly-data.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Version Tables for Monthly Data

Objective: Configure tables to maintain separate datasets for each time period, enabling historical tracking and period-over-period analysis.

When to use this procedure: Use monthly versioning when:

- Data values change each month (e.g., general ledger, actual costs, server utilization)
- You need to preserve historical values for trend analysis
- Your business processes require month-end close and period locking
- Different data structures or values apply to different time periods

Do not use monthly versioning when:

- Data is static or changes infrequently
- You only need the most current data
- Data is reference/lookup information (e.g., cost pool mappings)

Prerequisites:

- Time has been enabled for the project
- Understanding of your organization’s fiscal calendar
- Familiarity with creating and uploading tables
- Permissions to edit tables (AccessDev role)

Time estimate: 15 minutes for initial configuration; 5 minutes per period for ongoing uploads

## Steps

Part 1: Configure Monthly Versioning for a New Table

1. Create a new table: In the Project Explorer , click New → Table , enter a Name (e.g., “Monthly GL Actuals”), enter a Category, and click OK .
1. Select monthly versioning: At the top of the screen, locate the Data Refresh Cycle dropdown and select Monthly versions; Update every month .

Understanding Monthly Versioning Options:

- Monthly versions; Update every month: New data added monthly; previous months preserved
- Yearly versions; Update every month: 12 months uploaded monthly (rolling year)
- Yearly versions; Update at start of year: Annual upload; static until next year
- Yearly versions with carryover: Annual upload with automatic carryover of previous year’s values Upload the first month ’ s data: Ensure the date picker shows the period you want, click File Upload , upload your data file, configure import settings, click Save and Check In . Configure data expiration notifications (optional): Click to configure notifications to set up email alerts when data hasn’t been refreshed according to schedule.

Part 2: Upload Data for Subsequent Periods

1. Check out the table: Navigate to the table, right-click, select Check Out .
1. Switch to the target period: Use the date picker to select the period for new data. A placeholder appears in the Upload step.
1. Upload the period ’ s data: Click the placeholder, browse to the file or drag it in. The system creates a new version for this period.
1. Verify and save: Click the Table step to preview, verify values, click Save and Check In .

## Expected Results

- Table contains separate datasets for each time period
- Switching periods in the date picker displays the corresponding dataset
- Historical data is preserved and accessible
- Period-over-period comparisons are possible in reports
- Data freshness alerts notify you when monthly uploads are missing

## Common Pitfalls and Troubleshooting

Problem: “Missing data” errors in model or reports

- Cause: Data not uploaded for all periods between project start and current date
- Solution: Upload data files for all required periods. Consider adjusting project start date, using carryover versioning, or creating placeholder datasets.

Problem: Uploaded to wrong period

Solution: Always check the date picker before uploading. Delete the incorrect upload by selecting that period, checking out, and removing the file from the Upload step.

Problem: Schema changes didn’t apply to older periods

- Cause: Schema changes only apply from the selected period forward
- Solution: This is expected behavior. To update older periods, switch to each period using the date picker, make changes, and save.

## What’s Next

- Set up date partitioning : For GL files with monthly columns, add date partition transform steps
- Configure closed periods: Lock finalized periods to prevent accidental changes (Section 6.1)
- Schedule automated builds: Align model calculations with month-end close processes (Section 6.1)
- Create trending reports : Leverage monthly data for period-over-period analysis
