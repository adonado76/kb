---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Plan Status APIs"
breadcrumb:
  - "Planning"
  - "APIs"
  - "Planning REST APIs Overview"
source_path: "it-planning/planning/pln-status-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Plan Status APIs

The **Plan Status APIs** allow you to export plan approval and status information.
These APIs are commonly used for governance, audit, and reporting purposes to understand the
lifecycle and approval state of plans.

Plan status data is exported as a CSV file and can be used to track progress, identify
bottlenecks, or support oversight processes across planning cycles.

## POST /planning/api/v1/plans/<planId>/status/export

**Description**

Exports plan approval status data. The export is returned as a CSV file based on the parameters
supplied.

**Request**

```
POST https://app.apptio.com/planning/api/v1/plans/<planId>/status/export
```

Note: Ensure the URL matches your region (e.g., app-eu.apptio.com, app-au.apptio.com). Use the plans
GET api to get Plan Id of plan to export.

**Parameters**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Allowed Values** | **Required** | **Description** |
| basePercentage | ONE ONE\_HUNDRED | FALSE | Format in which percentage has to be displayed. Default: ONE |
| characterEncoding | UTF\_8 SHIFT\_JIS | FALSE | Input file encoding Default: UTF\_8 |
| columnDelimiter | COMMA SEMICOLON  TAB | FALSE | CSV delimiter Default: COMMA |
| dateFormat | *Supported date formats:* *yyyy-MM-dd*  *yyyy/MM/dd*  *yyyy.MM.dd*  *yy-MM-dd*  *yy/MM/dd*  *yy.MM.dd*  *yy-M-d*  *yy/M/d*  *yy.M.d*  *MM-dd-yyyy*  *MM/dd/yyyy*  *MM.dd.yyyy*  *MM-dd-yy*  *MM/dd/yy*  *MM.dd.yy*  *M-d-yyyy*  *M/d/yyyy*  *M.d.yyyy*  *M-d-yy*  *M/d/yy*  *M.d.yy*  *dd-MM-yyyy*  *dd/MM/yyyy*  *dd.MM.yyyy*  *dd-MM-yy*  *dd/MM/yy*  *dd.MM.yy*  *d-M-yy*  *d/M/yy*  *d.M.yy*  *d-M-yyyy*  *d/M/yyyy*  *d.M.yyyy* | FALSE | Format of date fields in the import file. Default: yyyy-MM-dd |
| decimalPrecision | ZERO  ONE  TWO  THREE  FOUR  FIVE  SIX  SEVEN  EIGHT | FALSE | Number of decimals applied to numeric values Default: EIGHT |
| decimalSymbol | PERIOD COMMA | FALSE | Decimal separator Default: PERIOD |

**Response**

A downloadable CSV file containing the selected plan’s status details.

**Parent topic:** [Planning REST APIs Overview](../../it-planning/planning/plan-api.html "The Apptio Planning REST APIs provide secure, programmatic access to plans, planning data, metadata, and related artifacts within Apptio Planning. These APIs are designed to support automation and system integrations for planning, forecasting, analysis, governance, and data exchange use cases.")
