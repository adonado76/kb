---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Change History APIs"
breadcrumb:
  - "Planning"
  - "APIs"
  - "Planning REST APIs Overview"
source_path: "it-planning/planning/chng-hist-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Change History APIs

The **Change History APIs** allow you to export event log data that captures changes
made within Apptio Planning.Change History data is exported as a CSV file and can be used to audit
modifications for a specific plan, including **what changes were made**, **who made them**,
and **when the changes occurred**.

## POST /at/api/v1/planning/export

**Description**

Exports Change History event logs in to a .CSV file based on selected filters such as date range,
username, container, etc.

**Request**

```
POST https://app.apptio.com/at/api/v1/planning/export
```

Note: Ensure the URL matches your region (e.g., app-eu.apptio.com, app-au.apptio.com)

**Headers**

|  |  |  |
| --- | --- | --- |
| **Header** | **Value** | **Description** |
| apptio-opentoken | <open-token> | Authentication token generated in step 2 of prerequisites |
| apptio-current-environment | <environment-id> | Required environment UUID retrieved from step 3 of prerequisites |

**Parameters**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Allowed Values** | **Required** | **Description** |
| startDate | yyyy-MM-dd yyyy/MM/dd  yyyy.MM.dd  yyyy-MM-ddThh:mm:ssZ | TRUE | Start Date to export event logs. Note:  - Date-only values are converted to start of day (00:00:00 UTC). - Ambiguous formats like MM/dd/yyyy or dd/MM/yyyy are rejected to prevent data errors. |
| endDate | yyyy-MM-ddyyyy/MM/dd yyyy.MM.dd  yyyy-MM-ddThh:mm:ssZ | TRUE | Start Date to export event logs. Note:  - Date-only values are converted to start of day (00:00:00 UTC). - Ambiguous formats like MM/dd/yyyy or dd/MM/yyyy are rejected to prevent data errors. |
| eventTypes | ARRAY of STRINGS | FALSE | Event types to filter by |
| userNames | ARRAY of STRINGS | FALSE | Usernames to filter by |
| container |  | FALSE | Container value to filter by |
| item |  | FALSE | Item value to filter by |
| context |  | FALSE | Context value to filter by |
| areas | ARRAY of STRINGS | FALSE | Area types to filter by |
| itemTypes | ARRAY of STRINGS | FALSE | Item types to filter by |
| contextTypes | ARRAY of STRINGS | FALSE | Context types to filter by |

**Response**

A downloadable CSV file that includes event log data for the selected filters.

**Parent topic:** [Planning REST APIs Overview](../../it-planning/planning/plan-api.html "The Apptio Planning REST APIs provide secure, programmatic access to plans, planning data, metadata, and related artifacts within Apptio Planning. These APIs are designed to support automation and system integrations for planning, forecasting, analysis, governance, and data exchange use cases.")
