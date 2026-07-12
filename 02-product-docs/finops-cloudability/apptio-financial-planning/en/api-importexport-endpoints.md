---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "Import/Export Endpoints"
breadcrumb:
  - "Cloudability Financial Planning API"
  - "Import/Export Endpoints"
source_path: "SSVWBC/cloud-financial-planning/admin/import-export-end-points.html"
images: []
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# Import/Export Endpoints

*APIs used to export or import plan Forecast and Budget data.*

## Export

Export Forecast or Budget data as CSV. The exported resource is determined by the target field in the request body.

Endpoint

```
POST /v3/planning/exports
```

Request Body Example

```
curl -X POST 'https://api.cloudability.com/v3/planning/exports' \
  -H 'Content-Type: application/json' \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]' \
  --data @- << EOF
{
  "target": "FORECAST",
  "viewId": 0,
  "contextList": [
    {
      "contextType": "plan",
      "id": "31334964-ed17-4680-b2a6-a1a46512cb19"
    }
  ],
  "csvFormatSettings": {
    "characterEncoding": "UTF_8",
    "columnDelimiter": "COMMA"
  }
}
EOF

```

Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| target | enum | Resource to export: FORECAST , BUDGET_TARGET |
| viewId | integer | Cloudability View ID of the plan |
| contextList[].contextType | enum | Context type. For this API, use plan |
| contextList[].id | string (UUID) | Plan ID |
| csvFormatSettings | object | CSV output format settings |
| csvFormatSettings.characterEncoding | enum | Character encoding, for example: UTF_8 |
| csvFormatSettings.columnDelimiter | enum | Column delimiter, for example COMMA |

Responses

- 200 - OK . Export completed successfully. Response body contains CSV content.
- 400 - Bad Request . Invalid request payload.

## Import Budget or Forecast

Imports CSV data into a plan asynchronously. The imported resource is determined by the target form parameter.

Endpoint

```
POST /v3/planning/imports
```

Request Example

```
curl -X POST 'https://api.cloudability.com/v3/planning/imports' \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]' \
  -F 'file=@/path/to/file/file.csv' \
  -F 'encoding=UTF_8' \
  -F 'delimiter=COMMA' \
  -F 'planId=e904b327-6009-4f02-95c3-8483b45a6cfb' \
  -F 'type=MERGE' \
  -F 'viewId=0' \
  -F 'target=BUDGET_TARGET'

```

Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| file | file (CSV) | CSV to import |
| encoding | enum | File encoding, for example UTF_8 |
| delimiter | enum | CSV delimiter, for example COMMA |
| type | enum | Import mode. Currently only REPLACE is supported |
| planId | string (UUID) | Plan ID to import into |
| viewId | integer | Cloudability View ID of the plan |
| target | enum | Import target: BUDGET_TARGET or FORECAST |

Response Body

```
{
  "id": "string (uuid)",
  "planId": "string (uuid)",
  "viewId": 0,
  "target": "BUDGET_TARGET | FORECAST",
  "status": "Pending | Running | Success | Error"
}
```

Response Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| id | string (UUID) | Import job ID |
| planId | string (UUID) | Plan associated with the import |
| viewId | integer | Cloudability View ID of the plan |
| target | enum | Import target: BUDGET_TARGET or FORECAST |
| status | enum | Current job status: Pending , Running , Success , Error |

Response Codes

- 200 - Accepted . Import job accepted. Response body contains import job details.
- 400 - Bad Request . Invalid request payload.

## Get Import Job by ID

Returns the status and details of a specific import job.

Endpoint

```
GET /v3/planning/imports/{jobId}?planId={planId}&viewId={viewId}
```

Request Example

```
curl 'https://api.cloudability.com/v3/planning/imports/7b23a723-72f1-43c7-937e-5ca457949871?planId=4b6d0216-8ba1-4c3d-a71f-52c48063ad09&viewId=0' \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]'

```

Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| jobId | String (UUID) | ID of the job |
| planId | string (UUID) | ID of the plan |
| viewId | integer | Cloudability View ID of the plan |

Response Codes

- 200 - OK . Import job returned successfully. Response body contains import job details. Same structure as the import job object returned by the import submission endpoint.
- 404 - Not Found . Import job or plan not found.

## Get Import Jobs

Returns import jobs for a plan, filtered by import target and optionally by status.

Endpoint

```
GET /v3/planning/imports?planId={planId}&viewId={viewId}&target={target} [&status={status}]
```

Request Example

```
curl 'https://api.cloudability.com/v3/planning/imports?planId=4b6d0216-8ba1-4c3d-a71f-52c48063ad09&viewId=0&target=budget_target&status=Success' \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]'

```

Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| planId | string (UUID) | Plan associated with the import |
| viewId | integer | Cloudability View ID of the plan |
| target | enum | Import target: BUDGET_TARGET or FORECAST |
| status | enum | Status filter (optional): Pending , Running , Success , Error |

Response Codes

- 200 - OK . Import jobs returned successfully. Response body contains array of import job objects. Same structure as the import job object returned by the import submission endpoint.
- 404 - Not Found . Plan not found.

- To ensure the CSV matches the required schema, export the corresponding Forecast or Budget using the UI to use it as template.
- The type import mode is currently ignored by the service; only Replace All behavior is supported.
