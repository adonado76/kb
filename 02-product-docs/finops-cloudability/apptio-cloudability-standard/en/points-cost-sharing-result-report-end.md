---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cost Sharing Result Report End Points"
breadcrumb:
  - "Cloudability API"
  - "Cost Sharing End Points"
  - "Cost Sharing Result Report End Points"
source_path: "SSVCLNQ/api-v3/cost_sharing_result_report.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cost Sharing Result Report End Points

Summary

Retrieve the Cost Sharing's result report.

Attributes of a result report are:

startDate - the start date of the cost data

endDate - the end date of the cost data

metric - the cost metric to use for this allocation

Example Request - Retrieving Result Report

Note: metric is required for any report using a non-Proportional type cost-sharing rule.

```
## Request (17)
curl "https://api.cloudability.com/v3/internal/reporting/cost-sharing?endDate=2019-03-12&startDate=2019-03-02&metric=unblended_cost" \\
     -u ‘[auth_token]:’
```

```
{
  "columnHeaders": {
    "dimensions": [
      "category1"
    ],
    "metrics": [
      {
        "name": "total_cost",
        "dataType": "currency"
      },
      {
        "name": "non_shared_amount",
        "dataType": "currency"
      },
      {
        "name": "shared_amount",
        "dataType": "currency"
      },
      {
        "name": "allocated_share_amount",
        "dataType": "currency"
      },
      {
        "name": "allocated_share_percent",
        "dataType": ""
      },
      {
        "name": "post_shared_amount",
        "dataType": "currency"
      }
    ]
  },
  "aggregates": [
    {
      "values": [
        "2107194.4920047736"
      ]
    }
  ],
  "filters": [],
  "count": 2,
  "pagination": {},
  "dates": {
    "start": "2019-03-02",
    "end": "2019-03-12"
  },
  "rows": [
    {
      "dimensions": [
        "little services"
      ],
      "metrics": [
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "763436.0316036056"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "0"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "763436.0316036056"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "0"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "0"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "0"
        }
      ]
    },
    {
      "dimensions": [
        "big services"
      ],
      "metrics": [
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "135622.52503421396"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "135622.52503421396"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "0"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "84070.49655704634"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "0.10054724124811285"
        },
        {
          "count": "0",
          "max": "0",
          "min": "0",
          "sum": "219693.02159126033"
        }
      ]
    }
  ]
}
```
