---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "How-To Guide: Export Data via API"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Data Export"
  - "How-To Guide: Export Data via API"
source_path: "SSWRJM/studio/new-uc/howtoguides/work-with-data/htg-api.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# How-To Guide: Export Data via API

Objective: Programmatically retrieve data from TBM Studio tables and reports using the Platform API

When to use: When you need flexible, on-demand access to TBM Studio data for custom integrations, ETL pipelines, or automation scripts

Prerequisites:

- TBM Studio version 12.0 or later
- API authentication credentials (API keys or user credentials)
- Appropriate permissions for downloading data (AccessProd, AccessStg, DrillDown, and relevant View permissions)
- Basic familiarity with HTTP requests and your preferred scripting language

Time estimate: 20-30 minutes for initial setup; varies for integration development

## Understanding API-Based Export

The TBM Studio Platform API provides direct, programmatic access to your data without requiring the DataLink product. Common reasons to use the API include:

- Embedding data retrieval in third-party ETL tools
- Building custom applications that consume TBM data
- Automating data extraction when DataLink agents cannot be installed
- Implementing conditional logic or complex data retrieval workflows

## Step 1: Set Up Authentication

Before making API calls, configure your authentication. TBM Studio supports API key authentication (recommended) and username/password authentication.

For API key authentication:

1. In Enhanced Access Administration, ensure your user account has API keys configured.
1. Note your public key and secret key values.
1. Ensure the key has been granted access to the appropriate environment.

Required permissions for downloading data:

Your account needs these minimum permissions:

- AccessProd, AccessStg, DrillDown, View Proactive, AllDataView
- ViewMetricReports, ViewObjectReports, ViewTransformReports
- ViewTransparencyReports, ViewUnitReports, ViewReportsSavedForEveryone

## Step 2: Obtain an Authentication Token

Make a POST request to obtain an access token:

Endpoint: https://frontdoor.apptio.com/service/apikeylogin

Headers:

Accept: application/json

Content-Type: application/json

Body:

```
{"keyAccess": "your-public-key", "keySecret":
        "your-secret-key"}
```

Response: The response includes an apptio-opentoken cookie that you'll use for subsequent requests.

## Step 3: Get Your Environment ID

If you don't already know your environment ID, retrieve it with this request:

Endpoint: https://frontdoor.apptio.com/api/environment/[yourdomain.com]/[yourfrontdoorenv]

Replace [yourdomain.com] with your domain and [yourfrontdoorenv] with your environment name (typically "main").

The response includes the environment id value you'll need for data requests.

## Step 4: Download Table Data

With authentication complete, you can retrieve data from tables.

Get the API URL from TBM Studio:

- Navigate to the table in TBM Studio (Data Studio or Published Table).
- Select the Home tab, click Export , then select Show API URL .
- Copy the URL for your preferred format (CSV, TSV, or JSON).

Headers for all download requests:

Content-Type: text/tab-separated-values (or application/json for JSON)

apptio-opentoken: [your-token]

apptio-current-environment: [your-environment-id]

app-type: Flagship

app-version: NA

Note: The app-type and app-version headers are required for TBM Studio version 12.9 and later.

Supported file formats: CSV, TSV, CSV.GZ, TSV.GZ, XLS, XLSX

Return Codes and Error Handling

| Code | Meaning |
| --- | --- |
| Code | Meaning |
| 200 | Success |
| 400 | Incorrect API string (check URL format) |
| 500 | Internal server error (check permissions or data availability) |

## Common Pitfalls

Missing required headers

In version 12.9+, forgetting app-type and app-version headers causes authentication failures.

Incorrect time period format

Time periods must follow Apptio conventions (e.g., "January:2024" or "current" for the current month).

Token expiration

Authentication tokens expire. Implement token refresh logic in long-running processes.

Permission errors

Download failures often indicate missing permissions. Verify your account has the required permission set listed in Step 1.

## What's Next

- For comprehensive API documentation including upload capabilities, see Section 5.5 (API Reference)
- For DataLink integration patterns, see the DataLink documentation
- To set up Published Tables for automated BI feeds, see here .
