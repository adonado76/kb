---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Deployment, Project, Preferences Management"
breadcrumb:
  - "Cloudability API"
  - "Governance End Points"
  - "Deployment, Project, Preferences Management"
source_path: "SSVCLNQ/api-v3/deployment_project_preferences_management.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Deployment, Project, Preferences Management

## Deployments

Deployments represent infrastructure configurations linked to repositories and cloud accounts.

List Deployments

| Endpoint | GET /v3/governance/deployments |
| --- | --- |
| Endpoint | GET /v3/governance/deployments |
| Access | Public |
| Description | Returns deployments with optional filtering. Includes accounts for each deployment |

Query Parameters

| project_id | string (optional) - Filter by project ID |
| --- | --- |
| project_id | string (optional) - Filter by project ID |
| name | string (optional) - Filter by deployment name |

Response (200 OK)

```

{
  "result": [
    {
      "id": "deploy-123",
      "name": "prod-deployment",
      "project_id": "proj-123",
      "org_id": 12345,
      "iac": "terragrunt",
      "vcs": "github",
      "repo_owner": "example-org",
      "repo_name": "infrastructure",
      "repo_id": "repo-456",
      "branch": "main",
      "accounts": [
        {
          "id": "acc-789",
          "deployment_id": "deploy-123",
          "account_id": "123456789012",
          "account_vendor": "aws"
        }
      ]
    }
  ]
}
```

Create Deployment

| Endpoint | POST /v3/governance/deployments |
| --- | --- |
| Endpoint | POST /v3/governance/deployments |
| Description | Creates a new deployment with associated accounts |

Request Body Fields

| name | string (required) - Deployment name |
| --- | --- |
| name | string (required) - Deployment name |
| project_id | string (optional) - Project ID |
| iac | string (required) - Infrastructure as code tool (e.g., terragrunt) |
| vcs | string (required) - Version control system (e.g., github) |
| repo_owner | string (required) - Repository owner |
| repo_name | string (required) - Repository name |
| repo_id | string (required) - Repository ID |
| branch | string (required) - Branch name |
| accounts | array (required) - Associated accounts |

Example Request

```
{
  "name": "prod-deployment",
  "project_id": "proj-123",
  "iac": "terragrunt",
  "vcs": "github",
  "repo_owner": "example-org",
  "repo_name": "infrastructure",
  "repo_id": "repo-456",
  "branch": "main",
  "accounts": [
    {
      "account_id": "123456789012",
      "account_vendor": "aws"
    }
  ]
}
```

## Deployment Operations

Get Deployment by ID

| Endpoint | GET /v3/governance/deployments/{id} |
| --- | --- |
| Endpoint | GET /v3/governance/deployments/{id} |
| Description | Retrieves deployment details including accounts |

Update Deployment

| Endpoint | PUT /v3/governance/deployments/{id} |
| --- | --- |
| Endpoint | PUT /v3/governance/deployments/{id} |
| Description | Replaces existing deployment data |

Delete Deployment

| Endpoint | DELETE /v3/governance/deployments/{id} |
| --- | --- |
| Endpoint | DELETE /v3/governance/deployments/{id} |
| Description | Removes deployment and associated accounts |
| Response | 204 No Content |

Get Deployment Policies

| Endpoint | GET /v3/governance/deployments/{id}/policies |
| --- | --- |
| Endpoint | GET /v3/governance/deployments/{id}/policies |
| Description | Get all policies applicable for a deployment |

Get Deployment Cost Guardrails

| Endpoint | GET /v3/governance/deployments/{id}/guardrails/cost |
| --- | --- |
| Endpoint | GET /v3/governance/deployments/{id}/guardrails/cost |
| Description | Get all cost guardrails for a deployment |

Move Deployments to Project

| Endpoint | PATCH /v3/governance/deployments/move |
| --- | --- |
| Endpoint | PATCH /v3/governance/deployments/move |
| Description | Move deployments to a project or unassigned group |
| Request Body | { "deployment_ids": [ "deploy-1", "deploy-2" ], "project_id": "proj-123" } |
| Response | 204 No Content |

## Projects

Projects are logical groupings for organizing deployments within an organization.

## List Projects

| Endpoint | GET /v3/governance/projects |
| --- | --- |
| Endpoint | GET /v3/governance/projects |
| Description | Returns a list of projects with optional filtering by name |

Query Parameters

| name | string (optional) - Filter by project name |
| --- | --- |
| name | string (optional) - Filter by project name |

Response (200 OK)

```
{
  "result": [
    {
      "id": "proj-123",
      "name": "Production",
      "org_id": 12345
    }
  ]
}
```

## Create Project

| Endpoint | POST /v3/governance/projects |
| --- | --- |
| Endpoint | POST /v3/governance/projects |
| Description | Creates a new project for an organization |

Request Body

```
{
  "name": "Production"
}
```

Response (201 Created)

```
{
  "result": {
    "id": "proj-123",
    "name": "Production",
    "org_id": 12345
  }
}
```

## Get, Update, and Delete Project

Get Project by ID

| Endpoint | GET /v3/governance/projects/{id} |
| --- | --- |
| Endpoint | GET /v3/governance/projects/{id} |
| Description | Retrieves details of a specific project |

Update Project

| Endpoint | PATCH /v3/governance/projects/{id} |
| --- | --- |
| Endpoint | PATCH /v3/governance/projects/{id} |
| Description | Updates project name |
| Request Body | { "name": "Updated Name" } |

Delete Project

| Endpoint | DELETE /v3/governance/projects/{id} |
| --- | --- |
| Endpoint | DELETE /v3/governance/projects/{id} |
| Description | Deletes project and moves deployments to unassigned |
| Response | 204 No Content |

## Organization Preferences

Manage organization-level preferences for governance configuration.

## Preferences Management

Get Preferences

| Endpoint | GET /v3/governance/preferences |
| --- | --- |
| Endpoint | GET /v3/governance/preferences |
| Description | Get organization preferences |

Response (200 OK)

```
{
  "result": {
    "org_id": 12345,
    "created_at": "2025-01-01T00:00:00Z",
    "updated_at": "2025-01-02T00:00:00Z",
    "default_aws_account": "123456789012"
  }
}
```

Create/Update Preferences

| Endpoint | PUT /v3/governance/preferences |
| --- | --- |
| Endpoint | PUT /v3/governance/preferences |
| Request Body | { "default_aws_account": "123456789012" } |

Get Default Accounts

| Endpoint | GET /v3/governance/preferences/default-accounts |
| --- | --- |
| Endpoint | GET /v3/governance/preferences/default-accounts |
| Description | Get default accounts for organization |
