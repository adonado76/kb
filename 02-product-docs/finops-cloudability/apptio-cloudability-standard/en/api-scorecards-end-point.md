---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Scorecards End Point"
breadcrumb:
  - "Cloudability API"
  - "Scorecards End Point"
source_path: "SSVCLNQ/api-v3/scorecards_end_point.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Scorecards End Point

Summary

The Scorecards API end point can be used to retrieve your scorecard outlined in Scorecards KB .

- This end point does not support filtering and sorting.

End Point Particulars

end point : /scorecards for listing your organization's scorecard.

The Scorecards Object

The scorecards object has two blocks. In the main block, we show aggregate statistics for any spending within the scope of the supplied view as well as the grouping dimension. In the records block, we show scores for each individual business unit, as determined by the grouping dimension.

- Rightsizing Score - Measures how well you've matched the size of a resource to the workload
- Elasticity Score - Measures how well you are turning resources on and off in response to changing demand
- Pricing Score - Measures how well you're taking advantage of different purchasing options (including Spot and Reserved Instances) to pay the best possible price for a given resource
- The Overall Score combines these three components to give you a single metric measuring your overall cloud efficiency.

Example Scorecards Object

```
 {
  "result": {
    "dimensionKey": "group_name3",
    "elasticityScore": 0.7623178861,
    "overallScore": 0.63841755,
    "percentile": 0.5756578947,
    "pricingScore": 0.9395323124,
    "records": [
      {
        "dimensionValue": "cogs",
        "elasticityScore": 0.7187018801,
        "overallScore": 0.587071348,
        "pricingScore": 0.9614329474,
        "rightsizingScore": 0.2928227895,
        "totalSpend": 17472.9354800001
      },
      {
        "dimensionValue": "(not set)",
        "elasticityScore": 0.8770809734,
        "overallScore": 0.7298704459,
        "pricingScore": 0.8078440667,
        "rightsizingScore": 0.5487444058,
        "totalSpend": 4564.827239
      }
    ],
    "rightsizingScore": 0.3633010232,
    "totalSpend": 22037.7627189998
  }
}
```

Example Request - Retrieve a Scorecard

Perform a GET request at the /scorecards end point, specifying a viewId and dimension.

```
curl "https://api.cloudability.com/v3/scorecards?dimension=category4&duration=ten-day&viewId=0" \\
     -u ‘[auth_token]:’
```
