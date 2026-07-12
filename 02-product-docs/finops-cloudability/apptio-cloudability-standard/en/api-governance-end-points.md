---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Governance End Points"
breadcrumb:
  - "Cloudability API"
  - "Governance End Points"
source_path: "SSVCLNQ/api-v3/governance_endpoints.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Governance End Points

Summary

Cloud costs are easier to control before resources are deployed than after they're running in production. Cloudability's Governance API integrates directly into your development workflow, enabling teams to estimate costs, enforce policies, and catch budget issues during the pull request stage—before they impact your cloud bill.

Base URL and Versioning

All API endpoints use path-based versioning with the following base path: /v3/governance

API Categories

The Governance API is organized into the following categories:

1. Governance Set Up GitHub Integration: /github/installations, /github/check-runs, repositories/github HCP Terraform Integration: /hcp/runtask/credentials, /hcp/runtask/credentials/active, /hcp/runtask/{callback_path}
1. Deployment, Project & Preferences Management Manage deployments: /deployments, /deployments/{id}, deployments/{id}/policies, deployments/{id}/guardrails/cost Organize deployments into projects: deployments/move Create and manage projects: /projects, /projects/{id} Manage preferences: /preferences, /preferences/default-accounts
1. Policy Management & Evaluation Create and manage tagging and resource type policies: /policies, policies/{id}, /policies/options/{vendor_key} Create and manage cost guardrails: /guardrails/cost, /guardrails/cost/{id} Evaluate Terraform changes against resource type and tagging policies: /policy-evaluation/terraform
1. Cost Estimation & Resource Recommendation Calculate infrastructure cost differences from Terraform plans: /cost-estimate/terraform/diff Evaluate cost guardrails based on cost estimation Track cost impacts across deployments Generate resource recommendations: /recommendation/terraform
1. Pull Requests Tracking Get pull request details: /pull-requests, /pull-requests/{id} Approve pull requests
1. Metrics & Reporting Repository adoption metrics: /metrics/repo-adoption Policy compliance statistics: /metrics/policy-compliance Pull Request Statistics: /metrics/pr-stats Cost difference tracking by project: /total-cost-diff
