---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Governance - Getting Started"
breadcrumb:
  - "Governance"
  - "Governance - Getting Started"
source_path: "SSVCLNQ/admin/governance-getting-started.html"
images:
  - "03-media/apptio-cloudability-standard/Workflow_Terraform.png"
  - "03-media/apptio-cloudability-standard/Terraform2.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Governance - Getting Started

## What you can do with Cloudability Governance

Shape Our Governance Roadmap: 2‑Minute Survey

Cloudability Governance empowers teams to proactively manage cloud costs and enforce FinOps policies directly within developer workflows. With this feature, you can:

- Estimate Costs Before Deployment: Get real-time cost estimates for cloud resources, including custom pricing and EA discounts, directly in GitHub and HCP Terraform
- Optimize Resource Selection: Receive recommendations for lower-cost AWS EC2 and RDS alternatives with similar configurations
- Enforce Policies at the IaC Level: Ensure compliance by enforcing mandatory tag keys/values, blocking legacy resource provisioning, and setting budget thresholds for teams and applications.
- Monitor Compliance: Use a centralized dashboard to track adherence to FinOps policies across your organization.
- Manage Non-Compliant PRs: Identify and review pull requests that violate cost or policy rules, with built-in approval workflows

This feature shifts cloud cost management from reactive to proactive, helping prevent overspending and policy violations before infrastructure is deployed.

## Supported Integrations

- IaC tooling : HCP Terraform, Terraform Enterprise, Terraform Editions (version 1.10.5); Terragrunt (version 0.72.6)
- VCS: GitHub.com, GitHub Enterprise Server
- Cloud Provider: AWS, Azure

## Workflow - HCP Terraform/Terraform Enterprise

Capabilities represented in the diagram are available for VCS-driven workflow and for customers that use GitHub.

- Workflow triggers driven by CLI or API do not appear on the Cloudability Governance → Pull Request page.
- Status update and validation checks are not posted back to the initiating environment (Github PR page if created)
- Governance actions such as policy validation, enforcement blocking, or manual approval are unavailable through Cloudability Governance interface.

## Workflow - Terraform Community

## Overview of permissions

Cloudability Governance access is controlled through four specific permissions. Ensure that you have the right roles/permissions assigned.

- GovernanceFeatureViewOnly - This permission allows users to view all the pages under Cloudability "Governance" feature menu item. This permission is included in “Cloudability User” role.
- GovernanceFeatureConfigurationFullAccess - This permission allows users to access the configuration functionality (view, create, update configuration details). This permission is included in “Cloudability Admin” and “Cloudability Governance Automation User” role.
- GovernanceFeaturePolicyFullAccess - This permission allows user the access the policy configuration functionality (view, create, update policies) under the Cloudability "Governance" feature menu item. This permission is included in “Cloudability Governance Policy Admin” role.
- GovernanceFeaturePRApproval - This permission allows users to approve Pull Requests that are blocked when they don’t comply with policies. This permission is included in “Cloudability Governance PR Approver” role.

## Security – How your code and CSP infrastructure are protected

Cloudability Governance is designed with security and privacy in mind, ensuring that your code and cloud service provider (CSP) infrastructure remain protected throughout the cost and policy check process.

1. GitHub Integration Security: The IBM Cloudability GitHub App is used only to read pull request (PR) metadata, post comments to pull request and set PR check statuses. It requires minimal permissions : Read-only access to metadata and pull requests. Read/write access to pull requests. Write access to pull requests is needed to be able to post comments to the pull requests. Read/write access to checks (required to add Governance-related checks in GitHub PRs and update their status as failing, neutral, or successful). For Terraform Community users, the GitHub Action that invokes Cloudability Governance runs entirely within your environment , ensuring no external access to your codebase.
1. AWS/Azure Infrastructure Protection : Cloudability Governance does not access your AWS/Azure environment . Instead, it analyzes static Terraform plan outputs passed via the GitHub Action or HCP Terraform. The Terraform plan outputs do not persist on the Cloudability side and any secrets/sensitive information in terraform plan can be redacted before providing as input to Cloudability Governance. AWS/Azure account IDs are used only for pricing tier determination —no credentials are required, and no direct AWS/Azure API calls on customer accounts are made. All pricing data is sourced from Cloudability’s internal pricing service , not from your infrastructure.

This architecture ensures that your IaC code and cloud infrastructure remain secure, with no exposure of sensitive data or elevated access requirements.

Setup Cloudability Governance

Create and Manage Policies

Pull Requests - Approval Workflow

Resource Recommendations

Usage and Configuration-Based Cost Estimation

Troubleshooting
