---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Monitor engagement with Apptio Usage reports"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Report Basics"
  - "Monitor engagement with Apptio Usage reports"
source_path: "SSWRJM/studio/admin/monitor-engagement-apptio.html"
images:
  - "03-media/apptio-tbm-studio/setting-icon.png"
  - "03-media/apptio-tbm-studio/studio_import%20project_usage_sui.png"
  - "03-media/apptio-tbm-studio/usage_summary_sui.png"
  - "03-media/apptio-tbm-studio/user_logins_sui.png"
  - "03-media/apptio-tbm-studio/studio_apptiousagedashboard_6_sui.png"
  - "03-media/apptio-tbm-studio/studio_usage%20dashboard_current%20month_sui.png"
  - "03-media/apptio-tbm-studio/use_case_mapping_columns_sui.png"
  - "03-media/apptio-tbm-studio/use_case_mapping2_sui.png"
  - "03-media/apptio-tbm-studio/use_case_mapping4_sui.png"
  - "03-media/apptio-tbm-studio/use_case_mapping5_sui.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Monitor engagement with Apptio Usage reports

- Overall Apptio report engagement metrics across your organization
- Active and inactive users
- Popular and unpopular reports
- Report performance and loading times

Apptio recommends that a regular review of your Apptio Usage analytics become a part of your adoption strategy.

## Enable the Apptio Usage dashboard

1. In TBM Studio , from the Settings ( ) menu, click Import .
1. Click Usage , then click OK . Wait for the project to calculate. Calculations might take more than an hour, depending on the complexity of your project.
1. After calculations are complete, on the Settings menu, click Access Administration . Alternatively, you can log in to Enhanced Access Administration , and navigate to Access Administration .
1. In the Applications tab, next to Usage , click Show to make it visible. If you want to further modify role access, click Edit Visibility .

You can now access Usage on the Project menu that lists all Apptio applications.

## Set up the Usage refresh cadence

1. In TBM Studio , click Build > Promotion Options .
1. Click Recurring Updates .
1. Configure the recurrence frequency you want, then click Save .
1. Click Recurring Promotions .
1. Configure the recurrence to occur just after the updates, then click Save

## Apptio Usage dashboard reports

The following reports are available in the Apptio Usage dashboard.

## Usage Summary report

The Usage Summary report provides a quick overview of user engagement, which is especially useful for TBMAs to understand the value users are getting from Apptio and the areas of adoption that might need more attention. The Usage Summary report provides user information in the left panes and usage information in the right panes. Each pane displays key performance indicators (KPIs) that provide engagement insights.

- (1) User Filters - Select a user type or user name to filter the data displayed in the left panes that display user data.
- (2) User Count - This KPI shows the number of unique users who have logged in during the selected month and the average number of logins per user.
- (3) Logins - This KPI shows the number of logins for the selected month compared to the previous month.
- (4) Logins and Users - Use this chart to view the number of users and logins month-to-date, trends in user activity, and changes in adoption.
- (5) Login Summary by User - Use this table to view total logins per user for the month, quarter, and year-to-date. Click any item in the Full Name column to drill into specific user data.
- (6) Usage filters - Select an environment, user type, or user name to filter the data displayed in the right panes that display usage data. The default setting of the Environment filter is Production .
- (7) Views - This KPI shows the number of reports viewed during the selected month compared to the previous month.
- (8) Users - This KPI shows the number of unique users who have viewed reports in the selected month.
- (9) Report Usage - Use this chart to see the total reports and number of unique viewers month-to-date. This element can highlight trends in overall usage and help you understand the value of specific reports.
- (10) View Summary by Report - This table lists specific reports and their view counts per month, quarter, and year-to-date . Click any item in the Report Name column to drill into specific data, such as load time and use-case.

## User Logins report

The User Logins report displays more granular detail about users, such as specific login times, session duration, and activity during login.

- (1) User Count - This KPI shows the number of unique users who have logged in during the selected month and the average number of logins per user. This KPI also includes the month-over-month difference as a percentage.
- (2) Logins - This KPI shows the month-to-date number of logins compared to the login count from the previous month. This KPI also includes the month-over-month difference as a percentage.
- (3) Most Active User - The KPI shows the most active user in your Apptio product for the selected month. You can use this element to quickly identify top adopters and examine how they are using the system.
- (4) User Type Filter - Select a user type to filter the user login data.
- (5) Users and Logins Across Time - Use this chart to view the number of unique, logged in users compared to the total number of logins month-to-date. Both values should ideally increase over time, suggesting adequate adoption among your user base. If both values are decreasing, this chart might show you which periods to investigate further.
- (6) User Inactivity - Use this chart to view a list of the least active users, the time of their last access, and whether the last login was within the last 30 days. Combine information in this chart with the Users and Logins Across Time chart to identify users who might not have adequately adopted your Apptio solutions.
- (7) User Details – Login History - Use this table to view individual user login histories, including date, time, and browser information. Click View History in any row to view the activity for a specific user while they were logged in. This can be a valuable tool for troubleshooting unexpected issues that your users experience.

## Report Views report

The Report Views report provides detailed metrics about the viewing of projects and reports.

- (1) Views - This KPI shows the total number of report views during the selected month, and the month-over-month difference as a percentage.
- (2) Most Viewed Report and Most Active Viewer : Most Viewed Report - This KPI shows the report with the most views during the selected month. Most Active Viewer - This KPI shows the user with the most report views across all reports during the selected month.
- (3) Filters - Select an environment, report, project, or user name to filter the data displayed in the report.
- (4) Usage Across Time By Project - Use this pane to view usage per project over time. Select an option above the charts to display user data, report data, login data, or viewing data. The pie chart shows the metric you selected across all of your projects. The bar chart shows the same metric month-to-date.
- (5) Reports by Views - Use this chart to see the reports getting the most views and the number of unique users viewing those reports. You can click Views or Unique User Count to filter the graph by that metric alone. Click it again to return to the original view.
- (6) Reports by Users - Use this table to see user sessions sorted by report name. You can expand report names to see all of the users who accessed the report, then drill into information about that user's sessions.

## Report Performance report

The Report Performance report highlights the load times experienced by your users. This data gives you insight into performance issues and how to address them.

- (1) Filters - Select an environment, report, project, or user name to filter the data displayed in the report.
- (2) Report Load Time Percentiles – Top 5 - Use this chart to view the five slowest loading reports. For example, the 20th percentile (or "P20") of report loading times represents the slowest 20% of the loading times.
- (3) Report Latency – Top 5 - Use this chart to help identify the cause of poor performance. Then use the Load Time and Latency tables to investigate the source of the issue. The following performance metrics provide data related to the five slowest loading reports: Latency - The amount of time it takes for network traffic to travel between a user’s computer and Apptio’s data center. Request Time - The amount of time it takes for the request to be received by Apptio’s data center. Load Time - The amount of time it takes for Apptio’s data center to compute the required report data after receiving a request.
- (4) Load Time and Latency - Use these tables to investigate issues related to performance. Each table is organized by different elements but usually include the following: 90th percentile time Fastest and slowest times Percentage of total wait time - This is the percentage of total load time for the given performance metric. The central, dark line is the focus of this chart. The further the line is to the right, the more time is spent loading. Click View Details to drill into details. Specific tables include the following: Load Time - Entries are sorted by Report / User ID / InitalLoad or SlicersApplied.One factor that can increase Request Calculation time is the use of certain support queries in Apptio that cannot be precalculated. Latency - Entries are sorted by User ID / IP Address / Date / Application.Two factors that could increase latency time are Internet connectivity issues or an anti-virus firewall.
- (5) Project Period Access - Use this table to see when your users are using your reports per month and period. This data can help you understand which time periods are most often used by your users so you can pause the calculations on less frequently used time periods.

## Use case mapping reports

- Track logins based on use case
- Track logins based on the persona of end users
- Determine which use cases are high impacting for your organization
- Map both out-of-the-box and custom reports into tracking
- 

Use the following instructions to set up the use cases and personas so you can see them in the new Apptio Usage reports. Your use cases do not need to conform to the use cases in the Apptio Value Explorer (AVE).

## Report to Use Case Mapping table

1. Extract the Report to Use Case Mapping table from TBM Studio and populate the following columns for each report: Report Name - The name of the out-of-the-box or custom report Use Case - The use case that you want to deploy to align to the Report Name
1. Load the populated table back into the Report to Use Case Mapping table.

The Report Usage by Use Case report is now populated with use case data.

## User to Persona Mapping table

1. Extract the table from TBM Studio and populate a user ID, role, and persona for each user. User ID - The user's email address (their Enhanced Access Administration login) Role - The role of the user in Enhanced Access Administration (Admin, Business User, etc.) Persona - The persona of the end user (TBMA, IT Finance, Application Owner, IT Infra Owner, Service Owner, etc.)
1. Load the populated table back into the User to Persona Mapping table.

The Report Usage by Use Case report now allows you to filter by personas so you can view which persona are accessing each report.
