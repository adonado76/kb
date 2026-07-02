---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Deployment Configurations"
breadcrumb:
  - "Cloudability Premium"
  - "Governance"
  - "Setup Cloudability Governance"
source_path: "admin/governance-deployment-configurations.html"
images:
  - "images/gov6.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Deployment Configurations

Note: A deployment is a unit managed by Terraform, that is typically tied to a specific
service, environment, and region. It represents a single, versioned unit of change applied to the
infrastructure environment. **A deployment corresponds to a workspace in HCP
Terraform**.

***For example:*** *A team owns a ServiceA and deploys it in several
environments like (beta, staging, production) then they can configure deployments in Governance for
ServiceA-beta, ServiceA-staging, ServiceA-production.*

Deployments are automatically generated and listed on the Governance
Configuration page when either: 

- A GitHub Action is invoked from CI/CD workflows, or
- A Run Task is triggered in HCP Terraform after setup is completed.

No manual addition of deployments is required in the Cloudability Governance
Configuration UI. We recommend grouping these “Deployments” into “Projects” to
facilitate the application of policies. “Projects” represent grouping mechanisms specific to
Cloudability Governance.

Below are the associated fields for each of your deployments
(retrieved automatically – except for “Project”):

- **IaC Provider**: Terraform or Terragrunt
- **Deployment Name:** Name given to the deployment to identify it (needs to be unique among all
  your deployments)
- **Project:** Grouping mechanism specific to Cloudability Governance
- **GitHub Repository:** Repository where the infrastructure code is located
- **Base Branch:** Branch monitored by Governance and is the target for pull request merges. It
  typically represents your main or master branch and serves as the reference point for detecting
  infrastructure cost changes.

![image](../../../../03-media/cloudability-premium/images/gov6.png)

**Parent topic:** [Setup Cloudability Governance](../admin/governance-setup-cldy-governance.html)
