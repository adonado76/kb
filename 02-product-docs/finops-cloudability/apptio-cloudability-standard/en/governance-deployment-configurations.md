---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Deployment Configurations"
breadcrumb:
  - "Governance"
  - "Setup Cloudability Governance"
  - "Deployment Configurations"
source_path: "SSVCLNQ/admin/governance-deployment-configurations.html"
images:
  - "03-media/apptio-cloudability-standard/gov6.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Deployment Configurations

For example: A team owns a ServiceA and deploys it in several environments like (beta, staging, production) then they can configure deployments in Governance for ServiceA-beta, ServiceA-staging, ServiceA-production.

- A GitHub Action is invoked from CI/CD workflows, or
- A Run Task is triggered in HCP Terraform after setup is completed.

No manual addition of deployments is required in the Cloudability Governance Configuration UI . We recommend grouping these “Deployments” into “Projects” to facilitate the application of policies. “Projects” represent grouping mechanisms specific to Cloudability Governance.

Below are the associated fields for each of your deployments (retrieved automatically – except for “Project”):

- IaC Provider : Terraform or Terragrunt
- Deployment Name: Name given to the deployment to identify it (needs to be unique among all your deployments)
- Project: Grouping mechanism specific to Cloudability Governance
- GitHub Repository: Repository where the infrastructure code is located
- Base Branch: Branch monitored by Governance and is the target for pull request merges. It typically represents your main or master branch and serves as the reference point for detecting infrastructure cost changes.

![image](../images/gov6.png)
