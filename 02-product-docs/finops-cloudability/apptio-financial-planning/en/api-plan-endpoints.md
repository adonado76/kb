---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "Plan Endpoints"
breadcrumb:
  - "Cloudability Financial Planning API"
  - "Plan Endpoints"
source_path: "SSVWBC/cloud-financial-planning/admin/plan-end-points.html"
images: []
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# Plan Endpoints

*APIs used to create and manage CFP plans.*

## Plan Object

| Field | Type | Description |
| --- | --- | --- |
| id | string (UUID) | The start date for the cost report. Format: YYYY-MM-DD |
| referencedPlanId | string (UUID), nullable | ID of the plan this plan was cloned or referenced from |
| name | string | Name of the plan |
| periodCount | integer | Number of fiscal periods in the plan |
| createdTime | integer (epoch ms) | Timestamp when the plan was created |
| createdById | string (UUID) | User ID of the creator |
| modifiedTime | integer (epoch ms) | Timestamp when the plan was last modified |
| modifiedById | string (UUID) | User ID of the last modifier |
| startYear | integer | Fiscal start year of the plan |
| planStatusId | string (UUID) | Current plan status ID |
| costOwnerDimensionId | string (UUID) | ID of the cost-owning dimension |
| viewId | integer | Cloudability View ID associated with plan |
| baselineConfigurationId | string (UUID) | ID of the configuration used for baseline |
| forecastStatus | string, nullable | Status of the most recent forecast |
| costOwningDimension | array | Details of the cost-owning dimension (ID, name, display name) |
| planOwner | array | Plan owner details (user ID, full name, email) |

Example Plan Object

```
{
  "id": "dbdeec51-609e-431a-9cd3-5a1766d98678",
  "referencedPlanId": null,
  "name": "A Plan",
  "periodCount": 12,
  "createdTime": 1709339966638,
  "createdById": "2f15e3e2-f547-4dbd-8125-ff64e39f82f1",
  "modifiedTime": 1709339966638,
  "modifiedById": "4b12f1c0-6831-4893-b332-8f7cd90bb7f5",
  "startYear": 2024,
  "planStatusId": "f31eacea-7f04-4639-8dbc-bb11513674bd",
  "costOwnerDimensionId": "19f91d86-c5f9-462a-b3f8-61b7b094b051",
  "viewId": 0,
  "baselineConfigurationId": "999c57f3-207a-4bcc-810b-4593f9487980",
  "forecastStatus": null,
  "costOwningDimension": [
    {
      "id": "c158e7ff-9a99-499b-b6e0-6ab3743f2945",
      "name": "group_name1",
      "displayName": "Group Name 1"
    }
  ],
  "planOwner": []
}
```

## Get Plan Options

Returns supported values used during plan creation (plan duration, spend types, cost metrics).

```
GET /v3/planning/plans/options
```

Request Example

```
curl 'https://api.cloudability.com/v3/planning/plans/options' \
	-H 'Accept-Language: en-US' \
	-H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
	-H 'Apptio-Opentoken: [apptio opentoken]'
```

Response Fields

| Parameter | Type | Description |
| --- | --- | --- |
| maxPlanYears | integer | Maximum supported plan duration in years |
| excludedSpendOptions | array<object> | Supported spend types for exclusion |
| costMetricOptions | array<object> | Supported cost metrics |

Response Body Example

```
{
  "maxPlanYears": 3,
  "excludedSpendOptions": [
    {
      "id": "28be42fb-1dca-4e66-86c7-dace452199ef",
      "name": "Credits"
    },
    {
      "id": "768ebf89-a1c4-48f7-898c-364366755544",
      "name": "One-time Charges"
    }
  ],
  "costMetricOptions": [
    {
      "id": "bf57f572-0d23-4333-8a70-1d9197138d7b",
      "name": "Cost (Adjusted)"
    },
    {
      "id": "5de36ae2-a3ff-4626-91d9-814f1afa1ab7",
      "name": "Cost (Adjusted Amortized)"
    },
    {
      "id": "bf618379-cbe5-46a2-b1c4-4fb0274e35a2",
      "name": "Cost (Amortized)"
    },
    {
      "id": "3e382938-ded1-4a62-9c22-0152f457b835",
      "name": "Cost (List)"
    },
    {
      "id": "c5f9d1a9-9971-4915-86cd-0ba933bcd49d",
      "name": "Cost (Total Blended)"
    },
    {
      "id": "cc9d0c39-dbdf-45bb-9299-0dd29d6b53f5",
      "name": "Cost (Total)"
    },
  ]
}

```

## Create a Plan

Creates a new plan with specified dimensions and initial baseline forecast.

Endpoint

```
GET /v3/planning/plans/options
```

Request Example

```
curl -X POST 'https://api.cloudability.com/v3/planning/plans?viewId=0' \
  -H "Content-Type: application/json" \
  -H "Accept-Language: en-US" \
  -H "Apptio-Current-Environment: [apptio Frontdoor environment id]" \
  -H "Apptio-Opentoken: [apptio opentoken]" \
  -d @- << EOF
{
  "costOwnerDimensionName":"group_name3",
  "dimensions":[
    { "name":"group_name3", "type":"Cloudability" },
    { "name":"custom_test_dimension_3", "type":"Plan" }
  ],
  "viewId":0,
  "calculateBaselineRequest":{
    "monthsBack":12,
    "useLastYearActuals":false,
    "costMetricId":"fe7f6218-cc24-45db-abf1-582fedceaf96",
    "excludedSpendIds":[],
    "userId":123456
  },
  "name":"Plan",
  "planDuration":1,
  "startYear":2024,
  "userId":123456
}
EOF

```

Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| viewId | integer | Cloudability View ID to associate with plan |
| costOwnerDimensionName | string | Name of the cost-owning dimension (see Get Dimensions for possible values) |
| dimensions | array | List of dimensions (Cloudability or Plan) |
| calculateBaselineRequest | object | Settings for generating the initial baseline forecast (see below) |
| name | string | Name of the plan |
| planDuration | integer | Plan duration in years (see Get Plan Options → MaxPlanDuration) |
| startYear | integer | Fiscal start year |
| userId | integer | Cloudability user ID of requestor |

calculateBaselineRequest Object

| Field | Type | Description |
| --- | --- | --- |
| monthsBack | integer | Number of historical months of actuals to use when creating the baseline forecast |
| useLastYearActuals | boolean | If true, use the prior fiscal year’s actuals as the baseline source |
| costMetricId | string (UUID) | Cost metric to use when computing the baseline (see Get Plan Options → costMetricId) |
| excludedSpendIds | array | List of spend-type IDs to exclude from the baseline (see Get Plan Options → excludedSpendIds) |
| userId | integer | Cloudability user ID initiating the baseline calculation |

- Use Get Plan Options for valid values of planDuration , excludedSpendIds , and costMetricId .
- Use Get Dimensions for details on costOwnerDimensionName and other plan dimensions.
- The userId fields at both the top level and inside calculateBaselineRequest expect a Cloudability user ID (integer).

## Get a Plan

Retrieves details for a specific plan.

Endpoint

```
GET /v3/planning/plans/{planId}?viewId={viewId}
```

Request Example

```
curl 'https://api.cloudability.com/v3/planning/plans/{planId}?viewId=0' \
  -H "Accept-Language: en-US" \
  -H "Apptio-Current-Environment: [apptio Frontdoor environment id]" \
  -H "Apptio-Opentoken: [apptio opentoken]"

```

Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| planId | string (UUID) | ID of the plan to fetch |
| viewId | integer | Cloudability View ID of plan |

Response Example

```
{
  "id": "0a31996d-8106-4fcf-90e8-a480e8655ac2",
  "name": "FY2023 Plan v7",
  "periodCount": 12,
  "startYear": 2023,
  "planStatusId": "25121509-0beb-46ff-974d-cd2cc4f6dc20",
  "costOwnerDimensionId": "ff834521-56a7-478d-b5b3-0aa469cfbee3",
  "referencedPlanId": null,
  "createdTime": 1681839707244,
  "createdById": "b6b808f2-784c-4efb-a82f-2c976a7050d6",
  "modifiedTime": 1681858772118,
  "modifiedById": "b6b808f2-784c-4efb-a82f-2c976a7050d6",
  "viewId": 0,
  "baselineConfigurationId": "8193ca04-3a73-4314-9472-801da3eeaeec",
  "forecastStatus": "Success",
  "costOwningDimension": [
    {
      "id": "ff834521-56a7-478d-b5b3-0aa469cfbee3",
      "name": "tag5",
      "displayName": "Team (value)"
    }
  ],
  "planOwner": [
    {
      "id": "b6b808f2-784c-4efb-a82f-2c976a7050d6",
      "email": "john.smith@ibm.com",
      "fullName": "John Smith",
      "login": "john.smith@ibm.com"
    }

```

## Get Plans

Returns a list of plans associated with a specific View.

Endpoint

```
GET /v3/planning/plans?viewId={viewId}
```

Request Example

```
curl 'https://api.cloudability.com/v3/planning/plans?viewId=0' \
  -H "Accept-Language: en-US" \
  -H "Apptio-Current-Environment: [apptio Frontdoor environment id]" \
  -H "Apptio-Opentoken: [apptio opentoken]"

```

| Parameter | Type | Description |
| --- | --- | --- |
| viewId | integer | Returns all plans associated with this View |

Response Example

```
[
  {
    "id": "059705e7-dd14-4ec1-9ac3-d40f42d5cbf8",
    "name": "db FY2025 Plan 3yr",
    "periodCount": 36,
    "startYear": 2025,
    "planStatusId": "25121509-0beb-46ff-974d-cd2cc4f6dc20",
    "costOwnerDimensionId": "ba3e6ae8-e21f-4924-add7-07882fc7d98b",
    "referencedPlanId": null,
    "createdTime": 1754519904222,
    "createdById": "2cfae61c-bf77-4287-8898-77f2ee430424",
    "modifiedTime": 1754519904222,
    "modifiedById": "2cfae61c-bf77-4287-8898-77f2ee430424",
    "viewId": 0,
    "baselineConfigurationId": null,
    "forecastStatus": null,
    "costOwningDimension": [],
    "planOwner": [],
    "properties": null,
    "forecastPresetId": "24eec143-54e2-4351-a0df-e1c53c03527a"
  },
  {
    "id": "0a31996d-8106-4fcf-90e8-a480e8655ac2",
    "name": "FY2023 Plan v7",
    "periodCount": 12,
    "startYear": 2023,
    "planStatusId": "25121509-0beb-46ff-974d-cd2cc4f6dc20",
    "costOwnerDimensionId": "ff834521-56a7-478d-b5b3-0aa469cfbee3",
    "referencedPlanId": null,
    "createdTime": 1681839707244,
    "createdById": "b6b808f2-784c-4efb-a82f-2c976a7050d6",
    "modifiedTime": 1681858772118,
    "modifiedById": "b6b808f2-784c-4efb-a82f-2c976a7050d6",
    "viewId": 0,
    "baselineConfigurationId": null,
    "forecastStatus": null,
    "costOwningDimension": [],
    "planOwner": [],
    "properties": null,
    "forecastPresetId": "4c3d12b3-9c7b-445b-9057-07ee2b8f921b"
  }
]

```

## Delete a Plan

Deletes an existing plan.

Endpoint

```
DELETE /v3/planning/plans/{planId}?viewId={viewId}
```

Request Example

```
curl -X DELETE 'https://api.cloudability.com/v3/planning/plans/{planId}?viewId=0' \
  -H "Accept-Language: en-US" \
  -H "Apptio-Current-Environment: [apptio Frontdoor environment id]" \
  -H "Apptio-Opentoken: [apptio opentoken]"

```

| Parameter | Type | Description |
| --- | --- | --- |
| planId | string (UUID) | ID of the plan to delete |
| viewId | integer | Cloudability View ID of plan |
