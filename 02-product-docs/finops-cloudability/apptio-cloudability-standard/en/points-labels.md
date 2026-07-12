---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Labels"
breadcrumb:
  - "Cloudability API"
  - "Containers End Points"
  - "Labels"
source_path: "SSVCLNQ/api-v3/labels.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Labels

Summary:

Get a list of Label Keys observed in a given timeframe for a filtered set of data.

End point:

/containers/labels

Query Arguments:

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| start/end | Start/End date for the window of usage results. | Required | Format YYYY-MM-DD |
| filters | Filter the reported data to the given dimension values. | N/A |  |
| pretty | Pretty-print the JSON response | None | true |

Example Request

```
curl "https://api.cloudability.com/v3/containers/labels?pretty=true&start=2018-11-01&end=2018-11-05&filters=namespace==my-namespace&filters=cluster==${cluster_id}" -u "${API_KEY}:"
```

```
{
  "result": {
    "labels": [
      {
        "key": "cldy:labels:app",
        "keyDisplay": "app"
      },
      {
        "key": "cldy:labels:cluster",
        "keyDisplay": "cluster"
      },
      {
        "key": "cldy:labels:environment",
        "keyDisplay": "environment"
      },
      {
        "key": "cldy:labels:job-name",
        "keyDisplay": "job-name"
      },
      {
        "key": "cldy:labels:name",
        "keyDisplay": "name"
      },
      {
        "key": "cldy:labels:role",
        "keyDisplay": "role"
      },
      {
        "key": "cldy:labels:run",
        "keyDisplay": "run"
      },
      {
        "key": "cldy:labels:team",
        "keyDisplay": "team"
      }
    ]
  }
}
```
