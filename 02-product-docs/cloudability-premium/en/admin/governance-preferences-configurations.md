---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Preferences Configuration"
breadcrumb:
  - "Cloudability Premium"
  - "Governance"
  - "Setup Cloudability Governance"
source_path: "admin/governance-preferences-configurations.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Preferences Configuration

Overview

In order to fetch account specific pricing, Cloudability Governance currently looks for provider
account information as follows:

**AWS Resources**

**HCP TF/Terraform Enterprise customers** - Provider account information within the
Terraform plan itself from aws\_caller\_identity data source ([https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller\_identity](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity "(Opens in a new tab or window)")).
This information if present in Terraform plan output, has the highest precedence. If account
information is not available through aws\_caller\_identity then Cloudability Governance uses the
default account configured in preferences of Cloudability Governance Configuration page. If default
account is not configured in preferences, then retail (list) pricing will be used.

**TF Community customers (through GitHub action)** - Provider account information
within the Terraform plan itself from aws\_caller\_identity data source ([https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller\_identity](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity "(Opens in a new tab or window)")).
This information if present in Terraform plan output has the highest precedence. If account
information is not available through aws\_caller\_identity then Cloudability Governance uses
"provider-accounts" map as input for GitHub Action if configured. This is second in the order of
preference. If account information is not available through GitHub action input then Cloudability
Governance uses the default account configured in preferences of Cloudability Governance
Configuration page. If default account is not configured in preferences, then retail (list) pricing
will be used.

**Azure Resources**

For Azure resources, Cloudability Governance looks for subscription information in the following
order of precedence:

**HCP TF/Terraform Enterprise customers** - Provider subscription information within
the Terraform plan itself from azurerm\_subscription resource or azurerm\_subscription data source
([https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription "(Opens in a new tab or window)")).
This information if present in Terraform plan output, has the highest precedence. If subscription
information is not available through azurerm\_subscription then Cloudability Governance uses the
default account configured in preferences of Cloudability Governance Configuration page. If default
account is not configured in preferences, then retail (list) pricing will be used.

**TF Community customers (through GitHub action)** - Provider subscription information
within the Terraform plan itself from azurerm\_subscription resource or azurerm\_subscription data
source ([https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription "(Opens in a new tab or window)")).
This information if present in Terraform plan output has the highest precedence. If subscription
information is not available through azurerm\_subscription then Cloudability Governance uses
"provider-accounts" map as input for GitHub Action if configured. This is second in the order of
preference. If subscription information is not available through GitHub action input then
Cloudability Governance uses the default account configured in preferences of Cloudability
Governance Configuration page. If default account is not configured in preferences, then retail
(list) pricing will be used.

**Parent topic:** [Setup Cloudability Governance](../admin/governance-setup-cldy-governance.html)
