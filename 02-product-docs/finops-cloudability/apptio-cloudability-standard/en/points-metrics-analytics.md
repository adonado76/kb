---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Metrics & Analytics"
breadcrumb:
  - "Cloudability API"
  - "Governance End Points"
  - "Metrics & Analytics"
source_path: "SSVCLNQ/api-v3/metrics_analytics.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Metrics & Analytics

Retrieve organizational metrics for adoption, compliance, and cost tracking.

## Repository Adoption Metrics

| Endpoint | GET /v3/governance/metrics/repo-adoption |
| --- | --- |
| Endpoint | GET /v3/governance/metrics/repo-adoption |
| Description | Repository adoption statistics with CostGuard |

Response (200 OK)

```
{
  "result": {
    "total": 100,
    "onboarded": 80,
    "percentage": "80%"
  }
}
```

## Policy Compliance Metrics

| Endpoint | GET /v3/governance/metrics/policy-compliance |
| --- | --- |
| Endpoint | GET /v3/governance/metrics/policy-compliance |
| Description | Tagging and vendor policy compliance statistics |

Response (200 OK)

```
{
  "result": {
    "tagging_compliance": {
      "complaint": 25,
      "percentage": "80%"
    },
    "total": 100,
    "vender_policy_compliance": {
      "complaint": 25,
      "percentage": "80%"
    }
  }
}
```

Pull Request Statistics

| Endpoint | GET /v3/governance/metrics/pr-stats |
| --- | --- |
| Endpoint | GET /v3/governance/metrics/pr-stats |
| Description | Detailed breakdown of PR statuses |

Response Fields

| total | Total PRs |
| --- | --- |
| total | Total PRs |
| cancelled | Cancelled PRs |
| open_error | Open PRs with errors |
| open_passed | Open PRs that passed |
| open_failed | Open PRs that failed |
| open_fixed | Open PRs that were fixed |
| open_approved | Open PRs that are approved |
| merged_error | Merged PRs with errors |
| merged_passed | Merged PRs that passed |
| merged_failed | Merged PRs that failed |
| merged_fixed | Merged PRs that were fixed |
| merged_approved | Merged PRs that were approved |

Total Cost Difference by Projects

| Endpoint | GET /v3/governance/metrics/total-cost-diff |
| --- | --- |
| Endpoint | GET /v3/governance/metrics/total-cost-diff |
| Description | Total cost difference by project from start of current month to today |

Response (200 OK)

```
{
  "result": {
    "total_cost_diff": 12345.67,
    "start_date": "2025-01-01",
    "end_date": "2025-01-11",
    "cost_diff_by_project": {
      "projectA": {
        "cost_diff": 123.45
      },
      "projectB": {
        "cost_diff": -123
      }
    }
  }
}
```
