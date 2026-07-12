---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Clusters"
breadcrumb:
  - "Cloudability API"
  - "Containers End Points"
  - "Clusters"
source_path: "SSVCLNQ/api-v3/clusters.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Clusters

Starting November 14th, this endpoint will require the parameter concise=true

Summary

Get a list of provisioned clusters for your organization, the date each cluster was provisioned, and a timestamp for the first and last date Cloudability received data for each cluster.

End point

```
 /containers/v2/clusters 
```

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| start/end | Start/End date for the window of cluster results. Affects what nodes are returned (only nodes that were seen in this window will be in the results). | Required | Format YYYY-MM-DD |
| pretty | Pretty-print the JSON response | None | true |
| viewId | The ID number of the view with which to process the request. A value of 0 indicates no view. | Required |  |

Example Requests

```
curl "https://api.cloudability.com/v3/containers/v2/clusters?pretty=true&start=2018-11-01&end=2018-11-05&viewId=0" -u "${API_KEY}:"
```

```
{
  "result": {
    "clusters": [
      {
        "id": "f603489e-5bc0-4749-a61b-c5be59208355",
        "name": "cluster-aws",
        "firstSeen": "2018-07-26T00:00:00Z",
        "lastSeen": "2018-11-02T00:00:00Z",
        "provisionedAt": "2018-07-26T00:00:00Z",
        "nodes": [
          {
            "vendor": "Amazon",
            "resourceIdentifier": "i-05c3b8dcc15a2ecdb"
          },
          {
            "vendor": "Amazon",
            "resourceIdentifier": "i-0f58a6f23f21fddb9"
          },
          {
            "vendor": "Amazon",
            "resourceIdentifier": "i-056744c5a41b70336"
          },
          {
            "vendor": "Amazon",
            "resourceIdentifier": "i-0b6c49803ffcc4e21"
          },
          {
            "vendor": "Amazon",
            "resourceIdentifier": "i-02b379cab2292a66e"
          },
          {
            "vendor": "Amazon",
            "resourceIdentifier": "i-04d2edb03deb725a8"
          }
        ]
      },
      {
        "id": "dfd2581f-480f-11e8-b253-42010a80003a",
        "name": "cluster-gke",
        "firstSeen": "2018-04-24T00:00:00Z",
        "lastSeen": "2018-11-02T00:00:00Z",
        "provisionedAt": "2018-04-24T00:00:00Z",
        "nodes": [
          {
            "vendor": "GCP",
            "resourceIdentifier": "my-cluster-386473/us-central1-a/gke-staging-gke-default-pool-38d4xy10-dm97"
          },
          {
            "vendor": "GCP",
            "resourceIdentifier": "my-cluster-386473/us-central1-a/gke-staging-gke-default-pool-38d4xy10-t9h8"
          },
          {
            "vendor": "GCP",
            "resourceIdentifier": "my-cluster-386473/us-central1-a/gke-staging-gke-default-pool-38d4xy10-xtm9"
          }
        ]
      },
      {
        "id": "81dbeaa8-489f-11e8-a546-0a58ac1f024c",
        "name": "provisioned-cluster",
        "firstSeen": "2018-04-25T00:00:00Z",
        "lastSeen": "2018-11-05T00:00:00Z",
        "provisionedAt": "2018-04-25T00:00:00Z",
        "nodes": []
      },
    ],
    "meta": {
      "orgHasProvisioned": true,
      "orgHasData": true,
      "firstSeenDate": "2018-04-13T00:00:00Z"
    }
  }
}
```
