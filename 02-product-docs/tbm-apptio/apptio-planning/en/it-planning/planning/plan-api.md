---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Planning REST APIs Overview"
breadcrumb:
  - "Planning"
  - "APIs"
source_path: "it-planning/planning/plan-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planning REST APIs Overview

The **Apptio Planning REST APIs** provide secure, programmatic access to plans,
planning data, metadata, and related artifacts within Apptio Planning. These APIs are designed to
support automation and system integrations for planning, forecasting, analysis, governance, and data
exchange use cases.

**Using the Planning APIs, consumers can:**

- Discover plans available in an Apptio Planning environment
- Export and import plan expense data using CSV files
- Retrieve analytical outputs such as variance analysis and plan status
- Manage and validate user permissions at plan or global levels
- Integrate Actuals import into Spend Management
- Access layout metadata used to structure planning data

All APIs follow REST principles, use standard HTTP methods, and exchange data through JSON
responses and CSV files. Export APIs return downloadable CSV files, while import APIs accept CSV
files and return detailed validation results to support large‑scale, repeatable integrations.

## Prerequisites

To use the Plan APIs, you must:

1. [Create API keys](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=apis-api-overview-api-keys-faq "(Opens in a new tab or window)") for the environment from Apptio
   Administration.
2. [Generate Apptio open-token](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=apis-enhanced-access-administration-api-authentication-via-api-keys "(Opens in a new tab or window)") using api keys.
3. [Retrieve the **Environment Id**](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=apis-how-access-r12-api-through-enhanced-access-administration-via-curl#HowtoaccessR12APIthroughEnhancedAccessAdministrationviacurl__GetaenvIDuseopentoken__title__1 "(Opens in a new tab or window)"), which is required in all
   API headers.

Note: The user account used to generate API keys must have **Budget Process Owner** or
**Admin** privileges to access all available APIs. If a service account is used to create API
keys, please contact Apptio Support to ensure the necessary permissions are granted to that
account.

**Authentication Headers**

- All API requests require the following headers:
  - apptio-opentoken
  - Authentication token generated using API keys
- apptio-current-environment
  - Environment ID identifying the target Apptio Planning environment

  Note: Requests missing these headers or using invalid credentials will fail with authorization
  or access errors.

**Regional Endpoints**

- API requests must be sent to the correct regional endpoint for your Apptio deployment (for
  example, app.apptio.com, app-eu.apptio.com, or app-au.apptio.com).
- Ensure the base URL matches your region before issuing requests.

- **[Plan APIs](../../it-planning/planning/plan-data-api.html)**  
  The **Plan APIs** allow you to discover available plans and manage plan‑level expense data through import and export operations. These APIs form the foundation of most planning data integrations with Apptio Planning.
- **[Variance Analysis APIs](../../it-planning/planning/variance-analysis-api.html)**  
  The **Variance Analysis APIs** enable programmatic export of variance analysis data for a specific plan.
- **[Plan Status APIs](../../it-planning/planning/pln-status-api.html)**  
  The **Plan Status APIs** allow you to export plan approval and status information. These APIs are commonly used for governance, audit, and reporting purposes to understand the lifecycle and approval state of plans.
- **[Spend Management APIs](../../it-planning/planning/spnd-mgmt-api.html)**  
  The **Spend Management APIs** support the export and import of actuals data used in planning and financial analysis.
- **[User Permissions APIs](../../it-planning/planning/user-perm-api.html)**  
  The **User Permissions APIs** enable export and import of plan‑level and global permission data. These APIs support automated access management and validation of user permissions within Apptio Planning.
- **[Change History APIs](../../it-planning/planning/chng-hist-api.html)**  
  The **Change History APIs** allow you to export event log data that captures changes made within Apptio Planning.Change History data is exported as a CSV file and can be used to audit modifications for a specific plan, including **what changes were made**, **who made them**, and **when the changes occurred**.
- **[Table Layouts APIs](../../it-planning/planning/tab-lay-api.html)**  
  The **Table Layouts API** provides access to layout metadata used for displaying and organizing expense data in Apptio Planning. Layouts define how plan data is structured and presented across different expense types.
