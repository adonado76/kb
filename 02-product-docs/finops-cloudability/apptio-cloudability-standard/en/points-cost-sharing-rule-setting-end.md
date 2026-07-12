---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cost Sharing Rule Setting End Points"
breadcrumb:
  - "Cloudability API"
  - "Cost Sharing End Points"
  - "Cost Sharing Rule Setting End Points"
source_path: "SSVCLNQ/api-v3/cost_sharing_rule_setting.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cost Sharing Rule Setting End Points

Summary

Define a set of rules around how to allocate or distribute the shared costs.

The Rule Object

updatedAt (timestamp): when it was last updated

businessDimension (string): the business dimension whose values will drive cost-sharing

sourceIncludeBuckets : values from the Business Dimension to include

scopeDimension : scopes the cost-sharing to master payer or linked accounts

mapping : the mapping details

type : proportional, fixed, or even split mapping

targetExcludeBuckets : what business dimension values to exclude

metricName : the cost metric to use for this allocation

Example Rule Object

```
{
\t"updatedAt":"2019-03-13T18:31:36.129Z",
\t"businessDimension":"category4",
\t"sourceIncludeBuckets":[
\t\t"Cloudy Production",
\t\t"Cloudy Consolidated Master"
\t],
\t"scopeDimension":"account_identifier",
\t"mapping":{
\t\t"type":"ProportionalMapping",
\t\t"targetExcludeBuckets":[
\t\t\t"Cloudy IAM Account",
\t\t\t"Cloudy Staging"
    ],
\t\t"metricName":"unblended_cost"
  }
}
```

Example Cost Sharing Rule Requests

Example Request - Setting Proportional Allocation Rule

Allocate the shared costs to chosen targets proportionally based on the target's direct costs.

Note: metricName is required for the Proportional type (mode) only

```
curl -X "POST" "https://api.cloudability.com/v3/internal/cost-sharing/rules" \\
     -H 'Content-Type: application/json; charset=utf-8' \\
     -u ‘[auth_token]:’ \\
     -d $'{
  "scopeDimension": "account_identifier",
  "businessDimension": "category1",
  "sourceIncludeBuckets": [
    "CloudX Production",
    "CloudX Consolidated Master"
  ],
  "mapping": {
    "type": "ProportionalMapping",
    "targetExcludeBuckets": [
      "CloudX IAM Account",
      "Other Excluded Bucket"
    ],
    "metricName": "unblended_cost"
  }
}'
```

```
{
\t"updatedAt":"2019-03-13T18:31:36.129Z",
\t"businessDimension":"category4",
\t"sourceIncludeBuckets":[
\t\t"CloudX Production",
\t\t"CloudX Consolidated Master"
\t],
\t"scopeDimension":"account_identifier",
\t"mapping":{
\t\t"type":"ProportionalMapping",
\t\t"targetExcludeBuckets":[
\t\t\t"CloudX IAM Account",
\t\t\t"Cloudability Customer Trustee"
    ],
\t\t"metricName":"unblended_cost"
  }
}
```
