---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cost Estimation & Resource Recommendation"
breadcrumb:
  - "Cloudability API"
  - "Governance End Points"
  - "Cost Estimation & Resource Recommendation"
source_path: "SSVCLNQ/api-v3/cost_estimation_resource_recommendation.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cost Estimation & Resource Recommendation

These endpoints help you understand the cost impact of infrastructure changes before deployment.

## Calculate Terraform Cost Difference – including cost guardrail evaluation

| Endpoint | POST /v3/governance/cost-estimate/terraform/diff |
| --- | --- |
| Endpoint | POST /v3/governance/cost-estimate/terraform/diff |
| Operation ID | calculateTerraformCostDiff |
| Description | Analyzes Terraform state changes to calculate cost differences and evaluate cost guardrails |

Request Body

| terraform_plan | object (required) - Terraform plan JSON |
| --- | --- |
| terraform_plan | object (required) - Terraform plan JSON |
| deployment_id | string (optional) - UUID of deployment for guardrail evaluation |
| resource_usage | object (optional) - Additional usage metrics |
| provider_accounts | object (optional) - Mapping of provider to account info |

Example Request

```
{
  "deployment_id": "123e4567-e89b-12d3-a456-426614174000",
  "terraform_plan": {},
  "resource_usage": {},
  "provider_accounts": {
    "aws": {
      "account_id": "123456789012",
      "vendor": "aws"
    }
  }
}
```

Response (200 OK)

Key Response Fields:

| meta.currency_used | Currency used for calculations |
| --- | --- |
| meta.currency_used | Currency used for calculations |
| meta.cost_guardrail_status | Pass/Fail/Warning status |
| meta.highest_failure_level | Highest severity level encountered |
| meta.unsupported_resources | Resources not supported for cost calculation |
| meta.errored_resources | Resources that encountered errors |
| result.total_cost_before | Totalcost before changes |
| result.total_cost_after | Total cost after changes |
| result.total_cost_diff | Net cost difference |
| result.cloud_resource_diffs | Per-resource cost breakdowns |
| result.cost_guardrails | Guardrail evaluation results |

Example Response

```
{
  "meta": {
    "currency_used": "USD",
    "exchange_rate_used": 1,
    "deployment_id": "123e4567-e89b-12d3-a456-426614174000",
    "deployment_name": "production",
    "highest_failure_level": "warning",
    "cost_guardrail_status": "passed",
    "unsupported_resources": {},
    "no_cost_resources": {},
    "errored_resources": {}
  },
  "result": {
    "total_cost_before": "120.00",
    "total_cost_after": "150.00",
    "total_cost_diff": "30.00",
    "cloud_resource_diffs": [
      {
        "vendor": "aws",
        "selector": "aws_instance.web",
        "resource_type": "instance",
        "cost_before": "50.00",
        "cost_after": "80.00",
        "cost_diff": "30.00",
        "custom_price": false,
        "csp_account": {
          "account_id": "123456789012",
          "vendor": "aws"
        }
      }
    ],
    "cost_guardrails": []
  }
}
```

## Generate Resource Recommendations

| Endpoint | POST /v3/governance/recommendation/terraform |
| --- | --- |
| Endpoint | POST /v3/governance/recommendation/terraform |
| Operation ID | generateTerraformRecommendations |
| Description | Analyzes Terraform state to suggest optimized resource configurations |

Request Body

| terraform_plan | object (required) - Terraform plan JSON |
| --- | --- |
| terraform_plan | object (required) - Terraform plan JSON |
| resource_usage | object (optional) - Usage metrics |
| provider_accounts | object (optional) - Provider to account mapping |

Example Request

```
{
  "terraform_plan": {},
  "resource_usage": {},
  "provider_accounts": {
    "aws": {
      "account_id": "123456789012",
      "vendor": "aws"
    }
  }
}
```

Response (200 OK)

| selector | Resource identifier in Terraform configuration |
| --- | --- |
| selector | Resource identifier in Terraform configuration |
| vendor | Cloud provider (aws, gcp, azure) |
| resource_type | Type of cloud resource |
| current_resource | Current resource configuration |
| recommended_resource | Recommended configuration |

Example Response

```
{
  "cloud_resource_recommendations": [
    {
      "selector": "aws_instance.web",
      "vendor": "aws",
      "resource_type": "instance",
      "current_resource": {
        "instance_type": "t3.large",
        "vcpu": 2,
        "memory_gb": 8
      },
      "recommended_resource": {
        "instance_type": "t3.medium",
        "vcpu": 2,
        "memory_gb": 4,
        "reason": "Current utilization suggests smaller instance"
      }
    }
  ]
}
```
