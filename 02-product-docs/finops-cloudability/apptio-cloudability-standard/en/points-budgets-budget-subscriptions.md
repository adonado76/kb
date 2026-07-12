---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Budgets and Budget Subscriptions"
breadcrumb:
  - "Cloudability API"
  - "Budgets & Forecasting End Points"
  - "Budgets and Budget Subscriptions"
source_path: "SSVCLNQ/api-v3/budgets_and_budget_subscriptions.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Budgets and Budget Subscriptions

The Budget Object

id (string) - UUID for the budget

viewId (string) - The viewId the budget is applied against

name (string) - The name of the budget

basis (string) - Cost basis. One of "cash," "amortized," "adjusted", "adjustedAmortized" and "list"

ownerId (string) - The unique id of the person who created the budget

months (array) - list of month objects for those having defined budgets.

month (string) - month of spend YYYY-MM

threshold (integer) - budget limit for that month

Example Budget Object

```
{
  "result": {
      "id": "8a028d91-1234-abcd-54fc-0a131052b72f",
      "viewId": "0",
      "name": "Q4 Amortized",
      "basis": "amortized",
      "ownerId": "11235",
      "months": [
        {
          "month": "2017-10",
          "threshold": 19500
        },
        {
          "month": "2017-11",
          "threshold": 20500
        },
        {
          "month": "2017-12",
          "threshold": 21500
        }
      ]
    }
}
```

Example Budget Requests

Create a Budget

```
curl -X POST "https://api.cloudability.com/v3/budgets" \\
     -H 'Content-Type: application/json' \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
{
  "name": "TesterTon",
  "basis": "cash",
  "viewId": "0",
  "months": [
    {
      "month": "2018-01",
      "threshold": 19500
    },
    {
      "month": "2018-02",
      "threshold": 20500
    },
    {
      "month": "2018-03",
      "threshold": 21500
    }
  ]
}
EOF
```

A successful operation will result in the object being created and returned to the client.

Retrieve a Budget

```
curl "https://api.cloudability.com/v3/budgets/0643ce32-ca2b-4776-6492-2397a0e96c7f" \\
     -u ‘[auth_token]:’
```

Update a Budget

```
 curl -X PUT https://api.cloudability.com/v3/budgets/0643ce32-ca2b-4776-6492-2397a0e96c7f \\
     -H 'Content-Type: application/json' \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
{
  "name": "TesterTon",
  "basis": "amortized",
  "viewId": "0",
  "months": [
    {
      "month": "2018-01",
      "threshold": 29500
    }
  ]
}
EOF

```

Delete a Budget

curl -X DELETE https://api.cloudability.com/v3/budgets/0643ce32-ca2b-4776-6492-2397a0e96c7f \\ -u ‘[auth_token]:’

List All Budgets

```
curl https://api.cloudability.com/v3/budgets \\
     -u ‘[auth_token]:’
```

The Budget Subscription Object

As well as creating budgets for your cloud spend you can create subscriptions to receive an email notification if you exceed and/or are projected to exceed your budget.

id (string) - id for the subscription

budgetId (string) - budgetId that the subscription applies to

notifyExceeded (boolean) - notify when actual spend exceeds budget, true of false

notifyExpected (boolean) - notify when expected spend exceeds budget, true of false

Example Budget Subscription Object

```
{
  "result": {
      "id": "3f38dd43-f953-43d8-91bc-0184818f7598",
      "budgetId": "d090e29e-2a26-4ca5-7f9a-67be3134081e",
      "notifyExceeded": false,
      "notifyExpected": true
  }
}
```

Example Budget Subscription Requests

Create a Budget Subscription

```
 curl -X POST "https://api.cloudability.com/v3/budget-subscriptions" \\
     -H 'Content-Type: application/json' \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
{
  "budgetId": "d090e29e-2a26-4ca5-7f9a-67be3134081e",
  "notifyExpected": true,
  "notifyExceeded": true
}\t
EOF
```

Retrieve a Budget Subscription

```
curl https://api.cloudability.com/v3/budget-subscriptions/3f38dd43-f953-43d8-91bc-0184818f7598 \\
     -u ‘[auth_token]:’
```

Update a Budget Subscription

```
curl -X PUT https://api.cloudability.com/v3/budget-subscriptions/3f38dd43-f953-43d8-91bc-0184818f7598 \\
     -H 'Content-Type: application/json' \\
     -u ‘[auth_token]:’ \\
     -d @- << EOF
{
  "budgetId": "d090e29e-2a26-4ca5-7f9a-67be3134081e",
  "notifyExpected": true,
  "notifyExceeded": false
}\t
EOF
```

Delete a Budget Subscription

```
curl -X DELETE https://api.cloudability.com/v3/budget-subscriptions/3f38dd43-f953-43d8-91bc-0184818f7598 \\
     -u ‘[auth_token]:’
```

List All Budget Subscriptions

```
curl https://api.cloudability.com/v3/budget-subscriptions \\
     -u ‘[auth_token]:’
```
