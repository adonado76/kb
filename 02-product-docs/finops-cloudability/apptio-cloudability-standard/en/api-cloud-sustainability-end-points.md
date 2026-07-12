---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cloud Sustainability End Points"
breadcrumb:
  - "Cloudability API"
  - "Cloud Sustainability End Points"
source_path: "SSVCLNQ/api-v3/cloud-sustainability-api.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cloud Sustainability End Points

The Cloud sustainability API endpoint can be used to retrieve sustainability metrics.

End Point Detail

Sustainability metrics follow all the API functionality supported by the Cost Reporting Endpoint . For sustainability metrics information, we are adding two new metrics: carbon_emissions and kwh_consumption

Example Sustainability Report Object

Retrieve a list of sustainability metrics by performing a GET request at the reporting endpoint.

Example Request

```
curl 'https://api.cloudability.com/v3/reporting/cost/run?start_date=2024-08-01&end_date=2024-08-28&dimensions=region&metrics=total_amortized_cost,carbon_emissions,kwh_consumption,embodied_emissions,operational_emissions&filters=region[]=us-east-1,us-west-2’ -u ‘[auth_token]
```

Example Response

```
 {
  "results": [],
  "meta": {
    "dates": {
      "start": "2024-08-01T00:00:00Z",
      "end": "2024-08-28T00:00:00Z"
    },
    "filters": [
      {
        "comparator": "[]=",
        "value": "us-east-1,us-west-2’",
        "measure": {
          "name": "region",
          "label": "Region",
          "description": "The region in which a resource exists or a usage charge occurred, for example: us-east-1 for AWS, US East for Azure, us-east1 for GCP and us-ashburn-1 for OCI.",
          "data_type": "string",
          "type": "dimension",
          "group": {
            "ID": 2,
            "Key": "billing",
            "Name": "Billing"
          },
          "sub_group": {
            "ID": 7,
            "Key": "vendor",
            "Name": "Vendor"
          }
        }
      }
    ],
    "metrics": [
      {
        "name": "total_amortized_cost",
        "label": "Cost (Amortized)",
        "description": "This is an “accrual” cost metric, representing the consumed cost during any period. This metric is handy for ensuring commitments are allocated to the time and place they are consumed.",
        "data_type": "currency",
        "type": "metric",
        "group": {
          "ID": 2,
          "Key": "billing",
          "Name": "Billing"
        },
        "sub_group": {
          "ID": 3,
          "Key": "costs",
          "Name": "Costs"
        }
      },
      {
        "name": "carbon_emissions",
        "label": "Estimated Carbon Emissions (MTCO2e)",
        "description": "Estimated Carbon emissions by a resource in metric tons of carbon dioxide equivalent - MTCO2e",
        "data_type": "float",
        "type": "metric",
        "group": {
          "ID": 2,
          "Key": "billing",
          "Name": "Billing"
        },
        "sub_group": {
          "ID": 14,
          "Key": "sustainability",
          "Name": "Sustainability"
        }
      },
      {
        "name": "kwh_consumption",
        "label": "Power Consumed (kWh)",
        "description": "Power consumed by a resource in Kilo Watt Hours - kWh",
        "data_type": "float",
        "type": "metric",
        "group": {
          "ID": 2,
          "Key": "billing",
          "Name": "Billing"
        },
        "sub_group": {
          "ID": 14,
          "Key": "sustainability",
          "Name": "Sustainability"
        }
      }
    ],
    "dimensions": [
      {
        "name": "region",
        "label": "Region",
        "description": "The region in which a resource exists or a usage charge occurred, for example: us-east-1 for AWS, US East for Azure, us-east1 for GCP and us-ashburn-1 for OCI.",
        "data_type": "string",
        "type": "dimension",
        "group": {
          "ID": 2,
          "Key": "billing",
          "Name": "Billing"
        },
        "sub_group": {
          "ID": 7,
          "Key": "vendor",
          "Name": "Vendor"
        }
      }
    ],
    "aggregates": [
      {
        "name": "total_amortized_cost",
        "label": "Cost (Amortized)",
        "description": "This is an “accrual” cost metric, representing the consumed cost during any period. This metric is handy for ensuring commitments are allocated to the time and place they are consumed.",
        "data_type": "currency",
        "type": "metric",
        "value": "0"
      },
      {
        "name": "carbon_emissions",
        "label": "Estimated Carbon Emissions (MTCO2e)",
        "description": "Estimated Carbon emissions by a resource in metric tons of carbon dioxide equivalent - MTCO2e",
        "data_type": "float",
        "type": "metric",
        "value": "0"
      },
      {
        "name": "kwh_consumption",
        "label": "Power Consumed (kWh)",
        "description": "Power consumed by a resource in Kilo Watt Hours - kWh",
        "data_type": "float",
        "type": "metric",
        "value": "0"
      }
    ]
  },
  "offset": 0,
  "pagination": {},
  "limit": 0,
  "total_results": 0
}
```
