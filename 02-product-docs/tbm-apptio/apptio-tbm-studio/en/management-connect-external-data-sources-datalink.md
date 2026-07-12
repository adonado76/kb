---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Connect to External Data Sources (DataLink)"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Data Import & Management"
  - "Connect to External Data Sources (DataLink)"
source_path: "SSWRJM/studio/new-uc/howtoguides/work-with-data/connect-external-dl.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connect to External Data Sources (DataLink)

Objective: Set up automated data integration between TBM Studio and external systems using DataLink connectors to eliminate manual file uploads.

When to use this procedure: Use DataLink when you need to:

- Automate regular data loads (daily, weekly, monthly)
- Connect to ServiceNow for application TCO data exchange
- Pull data from enterprise systems without manual intervention
- Maintain consistent data feeds without manual file preparation

Prerequisites:

- Administrator access to TBM Studio and DataLink
- Credentials for the external data source (ServiceNow, database, etc.)
- For ServiceNow: Apps & Services TCO app installed (Quebec, Paris, or Orlando release)
- For API uploads: API authentication configured (see Section 3.5.1)

Time estimate: 20-30 minutes for initial configuration; 5 minutes for schedule changes

## Steps

## Part 1: Prepare TBM Studio (ServiceNow Integration)

1. Set up TCO reports in TBM Studio: Create the reports that will send data to ServiceNow, including Application TCO report (with Cost Pool composition) and Application TCO (with IT Resource Tower composition).
1. Configure mandatory columns in your reports: Cost Model: Set to “Business Application Costing” Fiscal period: Use formula = "FY"& CurrentDate("YY") &": "&"Q"& gettimeoffset("Quarter","Start","Year") +1 Business Application: Application Name (must match ServiceNow cmdb_ci_business_app table) Amount: Use formula = QuarterToDate(Cost)
1. Get the report API URIs: Navigate to each report, right-click, select Show API URI , and copy the JSON format URL.

## Part 2: Configure DataLink Connection

1. Create a new connection: Open DataLink, click New Connection , enter a Connection Name, and click Next .
1. Select the connector: Choose ServiceNow Apps & Services TCO Egress connector and click Next .
1. Select an agent: Choose either Cloud-based agent (hosted by Apptio, faster setup) or On-premise agent (better performance for local data).
1. Configure authentication:

Select authentication type: Basic (username/password) or OAuth 2.0 (token-based, cloud agents only)

For Basic Authentication:

- Enter ServiceNow base URL (e.g., https://{instance}.service-now.com)
- Enter username and password

For OAuth 2.0 Authentication:

- Register DataLink as a client application in ServiceNow first
- Enter Authorization URL, Token URL, Client ID, and Client Secret
- Specify Scope (READ and WRITE or READ only)
- Click Get Access Token Enter report details: Select the BIIT host, select the reports, paste the Report URLs (JSON format), and select the time period. Schedule the connection: Choose Schedule by time (specific days/times) or Schedule by event (run after another connection completes). Test the connection: Run the connection manually to verify setup, check logs for errors, and verify data appears in ServiceNow.

## Expected Results

- DataLink connection successfully authenticates with the external system
- Data automatically flows between systems on schedule
- Data is available in TBM Studio tables for use in models and reports
- For ServiceNow: TCO data appears in ServiceNow dashboards

## Common Pitfalls and Troubleshooting

Problem: Authentication fails

Solution: Verify credentials, re-obtain OAuth token if expired, ensure service account has necessary permissions in both systems.

Problem: Connection runs but no data appears

Solution: Verify report API URI is in JSON format and correctly copied, check selected time period has data, review DataLink logs.

Problem: Scheduled connection doesn’t run

Solution: Verify schedule settings, check agent status, for event-based schedules ensure triggering connection has completed.

## What’s Next

- Monitor data freshness: Set up alerts for missing or delayed data (Section 6.4)
- Transform integrated data : Apply transformations to standardize data (Section 3.1.2)
- Schedule coordinated builds: Align model calculations with integration schedules (Section 6.1)
