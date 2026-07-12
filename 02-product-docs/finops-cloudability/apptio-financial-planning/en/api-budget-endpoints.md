---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "Budget Endpoints"
breadcrumb:
  - "Cloudability Financial Planning API"
  - "Budget Endpoints"
source_path: "SSVWBC/cloud-financial-planning/admin/budget-end-points.html"
images: []
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# Budget Endpoints

*APIs used to retrieve and update budget targets associated with cost ownership values in a plan.*

## Budget Object

| Field | Type | Description |
| --- | --- | --- |
| id | string (UUID) | Id of the budget |
| plan_id | string (UUID) | Id of the plan the budget belongs to |
| cost_owner_id | string (UUID) | Id of the cost owner the budget belongs to |
| created_time | integer | Time the budget was initially created |
| modified_time | integer | Time the budget was last modified |
| is_editable | boolean | Whether this budget can be edited by the caller |
| cost_owner | object | Convenience object with the cost owner’s name and id |
| budgets_as_flat_amounts | object | Flat currency amounts by period/quarter/year (see keys below) |
| budgets_as_percentages | object (optional) | Percentages relative to the plan (same key scheme as flat amounts) |

Example Budget Object

```
json
{
  "id": "65a4839b-35ef-438d-8958-b68d2423fcc1",
  "is_editable": true,
  "cost_owner": {
    "name": "J. Smith",
    "id": "1cf4ae4c-4c33-4427-9b97-030b42ab4eed"
  },
  "budgets_as_flat_amounts": {
    "p0": 21666.666666666667,
    "p1": 21666.666666666667,
    "p2": 21666.666666666667,
    "p3": 21666.666666666667,
    "p4": 21666.666666666667,
    "p5": 21666.666666666667,
    "p6": 21666.666666666667,
    "p7": 21666.666666666667,
    "p8": 21666.666666666667,
    "p9": 21666.666666666667,
    "p10": 21666.666666666667,
    "p11": 21666.666666666667,
    "q0": 65000.000000000001,
    "q1": 65000.000000000001,
    "q2": 65000.000000000001,
    "q3": 65000.000000000001,
    "fy0": 260000.000000000004
  }
}

```

## Get Budgets

Fetches budgets for the specified plan; optionally filtered to specified cost ownership value(s). The cost ownership dimension in a Plan establishes the budget line items – one budget line per dimension value.

Endpoint

```
POST /v3/planning/budget-targets/fetch?planId={planId}&viewId={viewId}
```

Request Example

```
curl -X POST 'https://api.cloudability.com/v3/planning/budget-targets/fetch?planId=0b17a55a-c839-446f-986b-274702f27b2e&viewId=0' \
  -H "Content-Type: application/json" \
  -H 'Accept-Language: en-US' \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]' \
  -d @- << EOF
{
  "costOwnerIds": []
}
```

Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| planId | string (UUID) | ID of plan to fetch budgets from |
| viewID | string (UUID) | View ID of the plan |
| costOwnerIds | array<string, UUID>) | Optional cost ownership filter; each ID refers to a specific cost ownership dimension value (essentially, a budget line item) empty array returns all budget line items |

## Get a Budget

Retrieves a single budget target by its ID (within a plan).

Endpoint

```
GET /v3/planning/budget-targets/{budgetTargetId}?planId={planId}&viewId={viewId}
```

Request Example

```
curl 'https://api.cloudability.com/v3/planning/budget-targets/151a147c-5f85-4a3a-9a0c-f5158eb5b350?planId=9dba6ca0-3ae1-49a7-b4fb-adbb78122f06&viewId=0' \
  -H "Content-Type: application/json" \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]'

```

Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| planId | string (UUID) | ID of plan to fetch budgets from |
| viewID | string (UUID) | View ID of the plan |
| budgetTargetID | string (UUID) | Budget target ID |

## Edit a Budget

Updates a single fiscal period, quarter, or year for the budget — either as a flat amount or as a percentage of the plan

Endpoint

```
PATCH /v3/planning/budget-targets/{budgetTargetId}?planId={planId}&viewId={viewId}
```

Request Example

```
curl -X PATCH 'https://api.cloudability.com/v3/planning/budget-targets/151a147c-5f85-4a3a-9a0c-f5158eb5b350?planId=9dba6ca0-3ae1-49a7-b4fb-adbb78122f06&viewId=0' \
  -H "Content-Type: application/json" \
  -H 'Accept-Language: en-US' \
  -H 'Apptio-Current-Environment: [apptio Frontdoor environment id]' \
  -H 'Apptio-Opentoken: [apptio opentoken]' \
  -d @- << EOF
{
  "amount": 100,
  "fiscalPeriod": "budgets_as_flat_amounts.fy0"
}
EOF

```

Parameters - Path / Query

| Parameter | Type | Description |
| --- | --- | --- |
| planId | string (UUID) | ID of plan |
| viewID | string (UUID) | View ID of the plan |
| budgetTargetID | string (UUID) | Budget target ID |

Parameters - Body

| Parameter | Type | Description |
| --- | --- | --- |
| amount | number | The value to set. If fiscalPeriod is budgets_as_flat_amounts.* , this is a currency amount . If it is budgets_as_percentages.* , this is a fraction (e.g., 0.10 = 10%). |
| fiscalPeriod | string | A dotted path identifying what to update. Use one of: • budgets_as_flat_amounts.pN (period), qN (quarter), or fyN (year) • budgets_as_percentages.pN / qN / fyN |

Examples of valid fiscalPeriod values

- Periods: budgets_as_flat_amounts.p0 , budgets_as_flat_amounts.p11
- Quarters: budgets_as_flat_amounts.q0 , budgets_as_flat_amounts.q3
- Years: budgets_as_flat_amounts.fy0 , budgets_as_flat_amounts.fy5
- Percent-based updates: same paths but under budgets_as_percentages.*

When patching a budget, you point fiscalPeriod at a specific node:

- Periods: budgets_as_flat_amounts.pN or budgets_as_percentages.pN
- Quarters: *.qN
- Years: *.fyN
