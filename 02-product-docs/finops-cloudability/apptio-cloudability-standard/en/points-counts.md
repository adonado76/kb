---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Counts"
breadcrumb:
  - "Cloudability API"
  - "Containers End Points"
  - "Counts"
source_path: "SSVCLNQ/api-v3/counts.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Counts

This endpoint will be deprecated on November 14th, 2025, with most of its functionality now available through the Report API. We recommend migrating to the new API to avoid any disruption.

Summary

Return counts of distinct values for dimension keys for a given timeframe.

End Point

/containers/counts

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| start/end | Start/End date for the window of usage results. | Required | Format YYYY-MM-DD |
| dimensions | The dimensions to get counts for. The result will have a count for each dimension key specified. Comma-separated value | Required | cluster daemonset deployment job namespace pod replicaset replication_controller service cldy:labels:* (i.e. labels) |
| group | Group the reported data by the given dimensions. Comma-separated value | None | cluster daemonset deployment job namespace pod replicaset replication_controller service cldy:labels:* (i.e. labels) |
| filters | Filter the reported data to the given dimension values. | N/A |  |
| pretty | Pretty-print the JSON response | None | true |

Example Request

```
curl "https://api.cloudability.com/v3/containers/counts?pretty=true&start=2018-11-01&end=2018-11-05&dimensions=namespace,service&group=cluster" -u "${API_KEY}:"
```

```
{
  "result": {
    "groups": [
      {
        "group": [
          {
            "key": "cluster",
            "value": "e5ad2c07-2bd4-4e8f-afdf-6dbbcddc8cea"
          }
        ],
        "counts": [
          {
            "key": "namespace",
            "value": 9
          },
          {
            "key": "service",
            "value": 18
          }
        ]
      },
      {
        "group": [
          {
            "key": "cluster",
            "value": "0be6790f-e810-4f2e-a056-aa3f64c14504"
          }
        ],
        "counts": [
          {
            "key": "namespace",
            "value": 7
          },
          {
            "key": "service",
            "value": 12
          }
        ]
      },
      {
        "group": [
          {
            "key": "cluster",
            "value": "0be6790f-e810-4f2e-a056-aa3f64c14504"
          }
        ],
        "counts": [
          {
            "key": "namespace",
            "value": 11
          },
          {
            "key": "service",
            "value": 23
          }
        ]
      },
      {
        "group": [
          {
            "key": "cluster",
            "value": "642622c9-9dce-4789-bbdb-f0e002f0763b"
          }
        ],
        "counts": [
          {
            "key": "namespace",
            "value": 9
          },
          {
            "key": "service",
            "value": 11
          }
        ]
      },
      {
        "group": [
          {
            "key": "cluster",
            "value": "dfd2581f-480f-11e8-b253-42010a80003a"
          }
        ],
        "counts": [
          {
            "key": "namespace",
            "value": 7
          },
          {
            "key": "service",
            "value": 3
          }
        ]
      },
      {
        "group": [
          {
            "key": "cluster",
            "value": "8970c8f4-e7cd-46c2-b9e2-efa8e922fdeb "
          }
        ],
        "counts": [
          {
            "key": "namespace",
            "value": 6
          },
          {
            "key": "service",
            "value": 12
          }
        ]
      }
    ]
  }
}
```
