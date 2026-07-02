---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Setup Cloudability Governance"
breadcrumb:
  - "Cloudability Premium"
  - "Governance"
source_path: "admin/governance-setup-cldy-governance.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Setup Cloudability Governance

## Before You Begin

This documentation is intended for the following roles within an organization:

- **Platform Admins** – They are responsible for configuring the feature and installing the
  GitHub app. For organizations using HCP or Terraform Enterprise, they will need to configure the
  Cloudability Governance Run Task and ensure it is aligned with organizational guardrails.
- **FinOps Teams** – They will define and manage their organization policies (such as approved
  instance families, required tags, or regional restrictions).
- **Cloud Engineers** – They will consume the integration of Cloudability Governance with GitHub
  and Terraform. Developers run Terraform plans and applies as part of their workflows and receive
  immediate cost and compliance feedback.

To successfully use this feature, ensure you have the following prerequisites in place:

- **For GitHub Users:**

  - Repository containing sample Terraform code.
  - IP Allow List - If your GitHub organization uses an IP allow list, you must ensure that
    Cloudability’s outbound IP ranges are included. Without these entries, Cloudability Governance will
    not be able to communicate with your GitHub repositories, and policy checks may fail. The following
    IP ranges should be added to your GitHub organization’s allow list:
    - **185.115.88.0/22**
    - **103.195.128.0/22**
    - **129.41.0.0/22**
- An IBM Cloudability account with the right Governance permissions assigned.
- **For HCP Terraform / Terraform customers**: An HCP Terraform account with permissions to
  create workspaces and manage Run Tasks.
- **For Terraform Community users**: GitHub Actions are available in your GitHub account.

## Overview

To set up Governance, Cloudability Admins need to configure Github integration, which will be
used for the Pull Requests (PR) approval workflow across all customer types. Then, depending on the
Terraform platform in use, setup steps differ:

- **For HCP Terraform or Terraform Enterprise users**, GitHub Actions are not required. Instead,
  Admins must configure a Run Task within their Terraform workspace by retrieving the HMAC key and
  endpoint URL from Cloudability and adding them to the Run Task configuration.
- **For Terraform Community users**, Admins need to set up a few organization-level
  variables/secrets in GitHub to store Frontdoor API keys, the Frontdoor URL, Frontdoor Environment
  ID, and Cloudability API URL. They also need to create or configure their own GitHub Action
  workflows that invoke the Cloudability Governance GitHub Actions.

Once completed, Governance will identify their “deployments” (units managed by Terraform, also
called “workspaces” in HCP Terraform) and display them in the Governance Configuration page. Users
will need to map them to projects (which are groups of deployments), which will have policies
associated with them. Customers can choose to define projects by application, team, service or
environment. A project name for a deployment can also be provided as optional input within GitHub
action workflow itself.

- **[GitHub.com (Cloud) App Installation](../admin/governance-github-app-installation.html)**
- **[GitHub Enterprise Server (on-prem) App Installation](../admin/governance-github-enterprise-installation.html)**
- **[HCP Terraform/Terraform Enterprise](../admin/governance-hcp-terraform-terraform-enterprise.html)**
- **[Configure GitHub Actions for Terraform Community](../admin/governance-configure-github-actions-for-terraform-community.html)**
- **[Deployment Configurations](../admin/governance-deployment-configurations.html)**
- **[Preferences Configuration](../admin/governance-preferences-configurations.html)**
