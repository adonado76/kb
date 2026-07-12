---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "Alerts Endpoints"
breadcrumb:
  - "Cloudability Financial Planning API"
  - "Alerts Endpoints"
source_path: "SSVWBC/cloud-financial-planning/admin/alerts-end-points.html"
images: []
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# Alerts Endpoints

*APIs used to manage CFP alerts for budget or forecast threshold monitoring.*

## Alerts Object

| Field | Type | Description |
| --- | --- | --- |
| alertId | string (UUID) | Identifier of the alert |
| alertCheckType | enum | One of: EXCEEDS_FORECAST, EXPECTED_TO_EXCEED_FORECAST, EXCEEDS_BUDGET, EXPECTED_TO_EXCEED_BUDGET |
| planId | string (UUID) | Plan associated with the alert |
| timePeriod | string | Evaluation period. One of: MTD, QTD, YTD |
| alertThresholdValue | number | Alert evaluation threshold (e.g., 10 = 10%) |
| filterConditions | array<FilterCondition> | Scope filters |
| filterConditions[].dimensionId | string (UUID) | Dimension to filter by |
| filterConditions[].values | array<string> | Allowed values for the dimension |
| subscribedUsers | array<string(UUID)> | CFP user IDs to notify |
| isShared | boolean | Shared with other users |
| isTriggered | boolean | Whether the alert is currently triggered |
| createdBy | string | Creator (e.g., email) |
| modifiedBy | string | Last modifier (e.g., email) |
| createdTime | integer (epoch ms) | When created |
| modifiedTime | integer (epoch ms) | When last modified |

Example Alert Object

```
{
  "timePeriod": "MTD",
  "alertCheckType": "EXPECTED_TO_EXCEED_FORECAST",
  "planId": "d4ced04e-3333-48e8-994e-a365fa68808a",
  "alertThresholdValue": 3,
  "filterConditions": [
    {
      "dimensionId": "f0c3e50f-4b43-4f1d-8b0c-1f7b9a84b1d2", // Account Name
      "values": ["prod-master", "billing-shared"]
    }
  ],
  "subscribedUsers": [],
  "isShared": false,
  "alertId": "2e467b2e-5534-4c88-818b-156367c5e87d",
  "createdBy": "admin@apptio.com",
  "modifiedBy": "admin@apptio.com",
  "createdTime": 1710182055645,
  "modifiedTime": 1710182055645
}

```

## Create an Alert

Create an alert.

Endpoint

```
POST /v3/planning/alerts
```

Request Example

```
curl -X POST 'https://api.cloudability.com/v3/planning/alerts' \
  -H "Content-Type: application/json" \
  -H 'Accept-Language: en-US' \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]' \
  -d @- << EOF
{
  "alertCheckType": "EXPECTED_TO_EXCEED_FORECAST",
  "alertThresholdValue": 1,
  "filterConditions": [
    {
      "dimensionId": " f0c3e50f-4b43-4f1d-8b0c-1f7b9a84b1d2",
      "values": ["prod-master"]
    }
  ],
  "isShared": true,
  "planId": "d4ced04e-3333-48e8-994e-a365fa68808a",
  "subscribedUsers": ["d1d681c1-5548-456c-82c3-9fec7164a154"],
  "timePeriod": "MTD",
  "viewId": 0
}
EOF

```

Parameters - Body

| Parameter | Type | Description |
| --- | --- | --- |
| alertCheckType | enum | One of: EXCEEDS_FORECAST , EXPECTED_TO_EXCEED_FORECAST , EXCEEDS_BUDGET , EXPECTED_TO_EXCEED_BUDGET |
| alertThresholdValue | number | Percentage threshold (e.g., 10 = 10%) |
| filterConditions | array | Each item: { "dimensionId": "<uuid>", "values": ["val1","val2"] } |
| isShared | boolean | Share with other users |
| planId | string (UUID) | Target plan |
| subscribedUsers | array<string(UUID)> | List of CFP userIds to notify. Must also include the caller’s CFP userId (use “ Get Current User ” to retrieve your own) |
| timePeriod | string | e.g., MTD |
| viewId | integer | Cloudability View ID of the target plan |

filterConditions Examples

Multiple conditions are AND ed together; multiple values within one condition are OR ed.

A. Team (single dimension)

```
"filterConditions": [
  {
    "dimensionId": "21b07899-3873-4961-8762-fc77ad18041a", // Team
    "values": ["Engineering", "SRE"]
  }
]

```

B. Account + Environment (intersection across dimensions)

```
"filterConditions": [
  {
    "dimensionId": "f0c3e50f-4b43-4f1d-8b0c-1f7b9a84b1d2", // Account Name
    "values": ["prod-master", "billing-shared"]
  },
  {
    "dimensionId": "9a2f1c8a-7c3f-4a15-9e9c-2d45e8c0a3b7", // Environment
    "values": ["prod"]
  }
]

```

C. Region + Service + Tag

```
"filterConditions": [
  {
    "dimensionId": "3d7d9f63-6e5a-4d61-9f9b-91f0a12d3b9e", // Region
    "values": ["us-east-1", "eu-west-1"]
  },
  {
    "dimensionId": "8d1f6b2a-5f8a-4c03-af83-2e7ac1d6b4fe", // Service
    "values": ["AmazonEC2", "AmazonEKS"]
  },
  {
    "dimensionId": "b85e4b10-1d4a-43f1-a8b2-0c2f6bd7f7a9", // Tag: Kubernetes_cluster
    "values": ["cluster-a", "cluster-b"]
  }
]

```

How isTriggered is evaluated

- EXCEEDS_FORECAST : true if actual-to-date spend exceeds forecast-to-date by more than alertThresholdValue % within timePeriod .
- EXPECTED_TO_EXCEED_FORECAST : true if projected end-of-period spend is expected to exceed the full-period forecast by more than alertThresholdValue %.
- EXCEEDS_BUDGET : true if actual-to-date spend exceeds budget-to-date by more than alertThresholdValue %.
- EXPECTED_TO_EXCEED_BUDGET : true if projected end-of-period spend is expected to exceed the full-period budget by more than alertThresholdValue% .

isTriggered is recomputed on the platform’s evaluation cadence and respects the filterConditions scope. If filters match no data, it will not trigger.

## Get an Alert

Retrieves details for a specific alert.

Endpoint

```
GET /v3/planning/alerts/{alertId}
```

Request Example

```
curl 'https://api.cloudability.com/v3/planning/plans/{planId}/alerts/{alertId}?viewId=0' \
  -H "Accept-Language: en-US" \
  -H "Apptio-Current-Environment: [apptio Frontdoor environment id]" \
  -H "Apptio-Opentoken: [apptio opentoken]"

```

Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| alertId | string (UUID) | ID of the alert |

## Get Alerts for a Specific User

Returns list of alerts owned by or shared with the specified user.

Endpoint

```
GET /v3/planning/alerts?userId={userId}
```

Request Example

```
url 'https://api.cloudability.com/v3/planning/alerts?userId=123456' \
  -H "Content-Type: application/json" \
  -H 'Accept-Language: en-US' \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]'

```

Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| userID | string (UUID) | ID of User to retrieve alerts for |

## Update an Alert

Update an existing alert.

Endpoint

```
PATCH /v3/planning/alerts/{alertId}
```

Request Example

```
curl -X PATCH 'https://api.cloudability.com/v3/planning/alerts/9ec054d0-e5fd-4b9b-a46a-8af7648e905b' \
  -H "Content-Type: application/json" \
  -H 'Accept-Language: en-US' \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]' \
  -d @- << EOF
{
  "alertCheckType": "EXPECTED_TO_EXCEED_FORECAST",
  "alertThresholdValue": 1,
  "filterConditions": [
    {
      "dimensionId": "21b07899-3873-4961-8762-fc77ad18041a",
      "values": ["Engineering”]
    }
  ],
  “isShared”: true,
  “planId”: “d4ced04e-3333-48e8-994e-a365fa68808a”,
  “subscribedUsers”: [“d1d681c1-5548-456c-82c3-9fec7164a154”],
  “timePeriod”: “MTD”,
  “viewId”: 0
}
EOF

```

Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| alertId | string (UUID) | ID of the alert |

Notes

- Same parameters as Create ; send only the fields you intend to change.
- Must include subscribedUsers array with the caller’s CFP userId (use “ Get Current User ” to retrieve your own)

## Delete an Alert

Deletes the specified alert.

Endpoint

```
DELETE /v3/planning/alerts/{alertId}
```

Request Example

```
curl -X DELETE 'https://api.cloudability.com/v3/planning/alerts/9ec054d0-e5fd-4b9b-a46a-8af7648e905b' \
  -H "Content-Type: application/json" \
  -H 'Accept-Language: en-US' \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]'

```

Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| alertId | string (UUID) | ID of the alert |
