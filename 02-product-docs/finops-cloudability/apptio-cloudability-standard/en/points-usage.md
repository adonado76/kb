---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Usage"
breadcrumb:
  - "Cloudability API"
  - "Containers End Points"
  - "Usage"
source_path: "SSVCLNQ/api-v3/usage.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Usage

This endpoint will be deprecated on November 14th, 2025, with most of its functionality now available through the Report API. We recommend migrating to the new API to avoid any disruption.

Summary

Provides usage by day for a filtered set of data. Specify the time range, then metrics to aggregate, and the filters, and the results will show the resource allocation percentages and average values, by day over the time range.

End Point

/containers/usage

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| start/end | Start/End date for the window of usage results. | Required | Format YYYY-MM-DD |
| metrics | Metrics to calculate allocations for. Comma-separated value. | cpu/reserved memory/reserved_rss network/tx network/rx filesystem/usage | cpu/reserved cpu/usage memory/reserved memory/reserved_rss memory/usage network/tx network/rx filesystem/usage |
| filters | Filter the reported data to the given dimension values. NOTE if filtering on cluster , the cost basis is also filtered, affecting the allocation percentages | N/A |  |
| pretty | Pretty-print the JSON response | None | true |

Example Request

```
curl "https://api.cloudability.com/v3/containers/usage?pretty=true&start=2018-11-01&end=2018-11-05&metrics=cpu/reserved,filesystem/usage" \\
-u "${API_KEY}:"
```

```
{
  "result": {
    "allocations": [
      {
        "metrics": [
          {
            "key": "cpu/reserved",
            "allocation": [
              0.7987696152936873,
              0.8033224699512777,
              0.7962087739444434,
              0.7849621407764081,
              0.7979094432363594,
              0.7968074452235664
            ],
            "resource": {
              "mean": [
                24871023,
                23591075,
                24485813,
                24441104,
                24844240,
                24809927
              ],
              "unit": "microcpu"
            },
            "available": {
              "mean": [
                31136666,
                29366881,
                30753006,
                31136666,
                31136666,
                31136666
              ],
              "unit": "microcpu"
            }
          },
          {
            "key": "filesystem/usage",
            "allocation": [
              0.018209299442523686,
              0.018631274665818067,
              0.018326117929819974,
              0.018119344944692844,
              0.01838696498388433,
              0.0185451797742567
            ],
            "resource": {
              "mean": [
                4792551765,
                4500930636,
                4743095999,
                4763378979,
                4842758913,
                4858709445
              ],
              "unit": "bytes"
            },
            "available": {
              "mean": [
                263192539639,
                241579318488,
                258816188859,
                262889138326,
                263380004131,
                261993116531
              ],
              "unit": "bytes"
            }
          }
        ]
      }
    ]
  }
}
```
