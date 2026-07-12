---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Pull Requests Tracking"
breadcrumb:
  - "Cloudability API"
  - "Governance End Points"
  - "Pull Requests Tracking"
source_path: "SSVCLNQ/api-v3/pull_requests_tracking.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Pull Requests Tracking

Track infrastructure changes through pull requests with policy evaluations and cost impacts.

List Pull Requests

| Endpoint | GET /v3/governance/pull-requests |
| --- | --- |
| Endpoint | GET /v3/governance/pull-requests |
| Description | Get all pull requests with filtering and pagination |

Query Parameters

| state | string (optional) - Filter by state |
| --- | --- |
| state | string (optional) - Filter by state |
| approved_by | array[integer] (optional) - Filter by approver user IDs |
| repository | string (optional) - Filter by repository |
| workflow_status | string (optional) - Filter by workflow status |
| order_by | array[string] (optional) - Order results |
| offset | integer (optional) - Pagination offset |
| limit | integer (optional) - Pagination limit |

Response (200 OK)

```
{
  "meta": {
    "total": 100,
    "limit": 20,
    "offset": 0
  },
  "result": [
    {
      "id": "pr-123",
      "title": "Update infrastructure config",
      "org_id": 12345,
      "state": "open",
      "vcs": "github",
      "url": "https://github.com/org/repo/pull/123",
      "repo_full_name": "org/repo",
      "base_branch": "main",
      "head_sha": "abc123",
      "created_at": "2025-01-01T00:00:00Z",
      "updated_at": "2025-01-02T00:00:00Z",
      "action_required": false,
      "is_approved": true,
      "status": "passed",
      "cost_diff": 50,
      "approvals": [],
      "affected_deployments": []
    }
  ]
}
```

## Pull Request Operations

Get Pull Request Detail

| Endpoint | GET /v3/governance/pull-requests/{id} |
| --- | --- |
| Endpoint | GET /v3/governance/pull-requests/{id} |
| Description | Get PR detail including latest workflow run |

Approve Pull Request

| Endpoint | POST /v3/governance/pull-requests/{id}/approve |
| --- | --- |
| Endpoint | POST /v3/governance/pull-requests/{id}/approve |
| Response | 204 No Content |
