---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Policy Management & Evaluation"
breadcrumb:
  - "Cloudability API"
  - "Governance End Points"
  - "Policy Management & Evaluation"
source_path: "SSVCLNQ/api-v3/policy_management_evaluation.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Policy Management & Evaluation

## Tagging & Resource Type policies

Policies define governance rules including tagging requirements and attribute constraints.

List Policies

| Endpoint | GET /v3/governance/policies |
| --- | --- |
| Endpoint | GET /v3/governance/policies |
| Description | Returns all policies with optional filtering and pagination |

Query Parameters

| category | string (optional) - Filter by category |
| --- | --- |
| category | string (optional) - Filter by category |
| vendor | string (optional) - Filter by vendor |
| org_level | boolean (optional) - Filter org-level policies |
| offset | integer (optional) - Pagination offset |
| limit | integer (optional) - Pagination limit |

Response (200 OK)

```
{
  "meta": {
    "total": 50,
    "limit": 20,
    "offset": 0
  },
  "result": [
    {
      "id": "pol-123",
      "name": "Required Tags Policy",
      "category": "tagging",
      "vendor": "aws",
      "org_id": 12345,
      "evaluate_existing_resources": true,
      "enforcement_level": "advisory",
      "is_org_level": true,
      "tag_rules": [
        {
          "tag_key": "Environment",
          "allowed_values": [
            "prod",
            "dev",
            "staging"
          ]
        }
      ],
      "attribute_rules": [],
      "attached_projects": []
    }
  ]
}
```

Get Resource Type Policy Options for a Specific Vendor

| Endpoint | GET /v3/governance/policies/options/{vendor_key} |
| --- | --- |
| Endpoint | GET /v3/governance/policies/options/{vendor_key} |
| Description | Retrieve available policy options for a vendor with optional filtering |

Parameters

| vendor_key | string (path, required) - Vendor identifier (aws, gcp, azure) |
| --- | --- |
| vendor_key | string (path, required) - Vendor identifier (aws, gcp, azure) |
| resource | string (query, optional) - Filter by resource name (EC2 - Compute Instance, EBS Volume) |
| attribute | string (query, optional) - Filter by attribute (Read Capacity, Write Capacity) |

## Create Policy

| Endpoint | POST /v3/governance/policies |
| --- | --- |
| Endpoint | POST /v3/governance/policies |
| Description | Creates a new policy. Either tag_rules or attribute_rules required |

Required Fields

| name | string - Policy name |
| --- | --- |
| name | string - Policy name |
| category | string - Policy category |
| vendor | string - Vendor (aws, gcp, azure) |
| evaluate_existing_resources | boolean - Evaluate existing resources |
| enforcement_level | string - Enforcement level (advisory, mandatory) |
| tag_rules OR attribute_rules | array - At least one required |

Optional Fields

| org_id | integer - Organization ID |
| --- | --- |
| org_id | integer - Organization ID |
| attached_projects | array[string] - Project IDs |
| is_org_level | boolean - Organization-level policy |

Example Request

```
{
  "name": "Required Tags Policy",
  "category": "tagging",
  "vendor": "aws",
  "evaluate_existing_resources": true,
  "enforcement_level": "advisory",
  "tag_rules": [
    {
      "tag_key": "Environment",
      "allowed_values": [
        "prod",
        "dev",
        "staging"
      ]
    }
  ],
  "is_org_level": true
}
```

## Policy Operations

Get Policy by ID

| Endpoint | GET /v3/governance/policies/{id} |
| --- | --- |
| Endpoint | GET /v3/governance/policies/{id} |
| Description | Retrieve specific policy details |

Update Policy

| Endpoint | PUT /v3/governance/policies/{id} |
| --- | --- |
| Endpoint | PUT /v3/governance/policies/{id} |
| Description | Updates policy. Same fields as create |
| Note | If attached_projects and is_org_level not set, all mappings removed |

Delete Policy

| Endpoint | DELETE /v3/governance/policies/{id} |
| --- | --- |
| Endpoint | DELETE /v3/governance/policies/{id} |
| Description | Deletes policy |
| Response | 200 OK |

## Resource Type & Tagging Policy Evaluation

Evaluate infrastructure changes against governance policies including tagging rules and resource attribute constraints.

## Evaluate Terraform Policies

| Endpoint | POST /v3/governance/policy-evaluation/terraform |
| --- | --- |
| Endpoint | POST /v3/governance/policy-evaluation/terraform |
| Operation ID | evaluateTerraformPolicies |
| Description | Analyzes Terraform state changes against defined policies to identify compliance issues |

Request Body

| terraform_plan | object (required) - Terraform plan JSON |
| --- | --- |
| terraform_plan | object (required) - Terraform plan JSON |
| deployment_id | string (optional) - UUID of deployment |
| resource_usage | object (optional) - Usage metrics |

Example Request

```
{
  "deployment_id": "123e4567-e89b-12d3-a456-426614174000",
  "terraform_plan": {},
  "resource_usage": {}
}
```

Response (200 OK)

Key Response Fields:

| meta.passed | Overall pass/fail status |
| --- | --- |
| meta.passed | Overall pass/fail status |
| meta.vendor_policy_passed | Vendor policy compliance |
| meta.tagging_policy_passed | Tagging policy compliance |
| meta.total_failed_policies | Count of failed policies |
| meta.highest_failure_level | Highest severity level |
| result.failed_policies | Array of policy failures with details |

Example Response

```
{
  "meta": {
    "deployment_id": "123e4567-e89b-12d3-a456-426614174000",
    "deployment_name": "production",
    "passed": false,
    "vendor_policy_passed": true,
    "tagging_policy_passed": false,
    "total_failed_policies": 1,
    "highest_failure_level": "mandatory"
  },
  "result": {
    "failed_policies": [
      {
        "policy_id": "pol-123",
        "policy_name": "Required Tags",
        "policy_category": "tagging",
        "enforcement_level": "mandatory",
        "failed_tag_rules": [
          {
            "tag_key": "Environment",
            "allowed_values": [
              "prod",
              "dev",
              "staging"
            ],
            "actual_key": "Environment",
            "actual_value": "test",
            "resource_name": "web_server",
            "resource_address": "aws_instance.web",
            "is_existing_resource": false,
            "resource_vendor": "aws"
          }
        ],
        "failed_attribute_rules": []
      }
    ]
  }
}
```

## Cost Guardrails

Cost guardrails enforce spending limits and thresholds for infrastructure changes.

List Cost Guardrails

| Endpoint | GET /v3/governance/guardrails/cost |
| --- | --- |
| Endpoint | GET /v3/governance/guardrails/cost |
| Description | Retrieve guardrails with optional filtering |

Query Parameters

| project_id | string (optional) - Filter by project |
| --- | --- |
| project_id | string (optional) - Filter by project |
| org_level | boolean (optional) - Org-level only |

Response (200 OK)

```
{
  "result": [
    {
      "id": "guard-123",
      "name": "Production Cost Limit",
      "category": "cost",
      "enforcement_level": "mandatory",
      "org_id": 12345,
      "cost_diff": {
        "max_allowed_diff": "1000.00"
      },
      "is_org_level": false,
      "attached_projects": [
        "proj-123"
      ]
    }
  ]
}
```

Create Cost Guardrail

| Endpoint | POST /v3/governance/guardrails/cost |
| --- | --- |
| Endpoint | POST /v3/governance/guardrails/cost |
| Description | Create a cost guardrail |

Required Fields

| name | string - Guardrail name |
| --- | --- |
| name | string - Guardrail name |
| category | string - Category |
| enforcement_level | string - Enforcement level |

Example Request

```
{
  "name": "Production Cost Limit",
  "category": "cost",
  "enforcement_level": "mandatory",
  "cost_diff": {
    "max_allowed_diff": "1000.00"
  },
  "is_org_level": false,
  "attached_projects": [
    "proj-123"
  ]
}
```

## Cost Guardrail Operations

Get Guardrail by ID

| Endpoint | GET /v3/governance/guardrails/cost/{id} |
| --- | --- |
| Endpoint | GET /v3/governance/guardrails/cost/{id} |

Update Guardrail

| Endpoint | PUT /v3/governance/guardrails/cost/{id} |
| --- | --- |
| Endpoint | PUT /v3/governance/guardrails/cost/{id} |

Delete Guardrail

| Endpoint | DELETE /v3/governance/guardrails/cost/{id} |
| --- | --- |
| Endpoint | DELETE /v3/governance/guardrails/cost/{id} |
| Response | 200 OK |

Note: The “Cost Guardrail” evaluation is done part of the Cost Estimation check – see endpoint “POST /v3/governance/cost-estimate/terraform/diff” for details.
