---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Governance Set Up"
breadcrumb:
  - "Cloudability API"
  - "Governance End Points"
  - "Governance Set Up"
source_path: "SSVCLNQ/api-v3/governance_set_up.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Governance Set Up

## GitHub Integration

Manage GitHub installations, repositories, and check runs for workflow integration.

GitHub Installations

Get Installation by ID

| Endpoint | GET /v3/governance/github/installations/{installation_id} |
| --- | --- |
| Endpoint | GET /v3/governance/github/installations/{installation_id} |

Delete Installation

| Endpoint | DELETE /v3/governance/github/installations/{installation_id} |
| --- | --- |
| Endpoint | DELETE /v3/governance/github/installations/{installation_id} |
| Description | Soft deletes installation |
| Response | 204 No Content |

## Repositories

| Endpoint | GET /v3/governance/repositories/github |
| --- | --- |
| Endpoint | GET /v3/governance/repositories/github |
| Description | Fetch all repositories registered for organization |

Response (200 OK)

```
{
  "total_count": 10,
  "result": [
    {
      "id": "repo-123",
      "repo_full_name": "org/infrastructure",
      "repo_name": "infrastructure",
      "repo_owner": "org"
    }
  ]
}
```

## HCP Terraform Integration

Integrate with HashiCorp Cloud Platform (HCP) Terraform run tasks.

HCP Runtask Credentials

Create Credentials

| Endpoint | POST /v3/governance/hcp/runtask/credentials |
| --- | --- |
| Endpoint | POST /v3/governance/hcp/runtask/credentials |
| Description | Create new credentials for HCP Runtasks |
| Request Body | { "description": "Production credentials" } (optional) |

Response (201 Created)

```
{
  "result": {
    "id": "cred-123",
    "hmac_key": "hmac_key_value",
    "callback_url_path": "/callback/123",
    "description": "Production credentials",
    "created_at": "2025-01-01T00:00:00Z",
    "created_by": 12345,
    "state": "active"
  }
}
```

Get Active Credentials

| Endpoint | GET /v3/governance/hcp/runtask/credentials/active |
| --- | --- |
| Endpoint | GET /v3/governance/hcp/runtask/credentials/active |
| Description | Retrieve currently active credentials |

Handle Callback

| Endpoint | POST /v3/governance/hcp/runtask/{callback_path} |
| --- | --- |
| Endpoint | POST /v3/governance/hcp/runtask/{callback_path} |
| Description | Handle HCP Runtask callback with HMAC authentication |
| Header | X-Tfc-Task-Signature (required) - HMAC signature |
