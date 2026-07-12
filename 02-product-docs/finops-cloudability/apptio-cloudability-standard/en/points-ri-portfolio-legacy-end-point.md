---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "RI Portfolio Legacy End Point"
breadcrumb:
  - "Cloudability API"
  - "RI Portfolio End Points"
  - "RI Portfolio Legacy End Point"
source_path: "SSVCLNQ/api-v3/ri_portfolio_legacy_endpoint.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# RI Portfolio Legacy End Point

Summary

The RI Portfolio end point can be used to retrieve a list of all your current and historical Reserved Instances (RIs). This Cloudability feature is especially handy as it aggregates RIs across all of your linked and master payer accounts for EC2, RDS, Redshift and Elasticache.

Learn more about the RI portfolio features.

Examples in this document will focus on EC2, but you will find patterns consistent across other AWS products.

- This end point supports filtering and sorting.

End Point Particulars

These end points are read-only for retrieving a list of Reservation Objects

end point : /reservations/aws/portfolio/ec2

end point : /reservations/aws/portfolio/rds

end point : /reservations/aws/portfolio/redshift

end point : /reservations/aws/portfolio/elasticache

These end points return a meta attribute within the JSON payload that looks like the following. In the example below 399 represents the number of RI purchases , whereas 24615 is the total number of instances across those purchases.

```
 "meta": {
    "aggregate": {
      "quantity": 24615
    },
    "pagination": {
      "totalCount": 399
    }
  }
```

The Reservation Object

vendorAccountId (string) - 12 digit string corresponding to your AWS account ID

reservationId (string) - The vendor supplied unique id for your reservation

instanceType (string) - The exact instance type you reserved

availabilityZone (string) - The availability zone you reserved into. If region scoped this will return as an empty string.

region (string) - The Region you reserved into. If AZ scoped this will return as an empty string.

start (integer) - The timestamp for when the RI began it's active period, represented in Unix time with millisecond precision.

end (integer) - The timestamp for when the RI began ended it's active period, represented in Unix time with millisecond precision.

duration (integer) - The active time for the RI, measured in seconds

term (integer) - Term for the RI, one or two year

productDescription (string) - The Reserved Instance product platform description as defined by AWS. For example Linux/UNIX (Amazon VPC) for EC2, aurora-mysql for RDS

tenancy (string) - Whether the RI is for shared (default) or single-tenant (dedicated) hardware

quantity (integer) - The number of instances comprising the reservation

state (string) - The state of the RI, the main ones being active right now or retired since the term finished.

offeringType (string) - Generally these will be one of 'No Upfront', 'Partial Upfront' or 'All Upfront' but for older retired RIs could be Utilization based types.

offeringClass (string) - Standard or Convertible

scope (string) - Availability Zone or Region

pricing (hash) - object containing details of verification state:

currencyCode (string) - At this time, the only supported currency is USD

upfront (integer) - The Upfront cost for the RI

recurring (hash) - info regarding the recurring aspect of the purchased RI.

frequency (string) - The granularity for the recurring price fee. Current supported value is 'hourly'

amount (number) - The hourly recurring rate for the RI.

tags (array) - a list of the tags applied to the RI

Example Reservation Object

```
{
  "result": [
    {
      "vendorAccountId": "118273444843",
      "reservationId": "aa04e121-436e-4cd4-8e50-0f8ebd95c52b",
      "instanceType": "r3.2xlarge",
      "availabilityZone": "",
      "region": "us-east-1",
      "start": 1516386261000,
      "end": 1521570259000,
      "duration": 5184000,
      "term": 1,
      "productDescription": "Linux/UNIX (Amazon VPC)",
      "tenancy": "default",
      "quantity": 1,
      "state": "active",
      "offeringType": "No Upfront",
      "offeringClass": "standard",
      "scope": "Region",
      "pricing": {
        "currencyCode": "USD",
        "upfront": 0,
        "recurring": {
          "frequency": "Hourly",
          "amount": 0.418
        }
      },
      "tags": []
    }
  ]
}
```

Example Requests

List Subscriptions

The following will list all subscriptions, historic and current, for EC2

```
curl "https://api.cloudability.com/v3/reservations/aws/portfolio/ec2" \\
     -u ‘[auth_token]:’
```

List Currently Active Subscriptions

```
curl "https://api.cloudability.com/v3/reservations/aws/portfolio/ec2?filter=state==active" \\
-u ‘[auth_token]:’
```

List & Order By Soonest Expiry Date

```
curl "https://api.cloudability.com/v3/reservations/aws/portfolio/ec2?filter=state==active&sortOrder=%2Bend" \\-u ‘[auth_token]:’
```
