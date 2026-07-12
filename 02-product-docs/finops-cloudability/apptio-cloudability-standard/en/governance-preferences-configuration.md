---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Preferences Configuration"
breadcrumb:
  - "Governance"
  - "Setup Cloudability Governance"
  - "Preferences Configuration"
source_path: "SSVCLNQ/admin/governance-preferences-configurations.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Preferences Configuration

Overview

In order to fetch account specific pricing, Cloudability Governance currently looks for provider account information as follows:

AWS Resources

HCP TF/Terraform Enterprise customers - Provider account information within the Terraform plan itself from aws_caller_identity data source ( https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity ). This information if present in Terraform plan output, has the highest precedence. If account information is not available through aws_caller_identity then Cloudability Governance uses the default account configured in preferences of Cloudability Governance Configuration page. If default account is not configured in preferences, then retail (list) pricing will be used.

TF Community customers (through GitHub action) - Provider account information within the Terraform plan itself from aws_caller_identity data source ( https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity ). This information if present in Terraform plan output has the highest precedence. If account information is not available through aws_caller_identity then Cloudability Governance uses "provider-accounts" map as input for GitHub Action if configured. This is second in the order of preference. If account information is not available through GitHub action input then Cloudability Governance uses the default account configured in preferences of Cloudability Governance Configuration page. If default account is not configured in preferences, then retail (list) pricing will be used.

Azure Resources

For Azure resources, Cloudability Governance looks for subscription information in the following order of precedence:

HCP TF/Terraform Enterprise customers - Provider subscription information within the Terraform plan itself from azurerm_subscription resource or azurerm_subscription data source ( https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription ). This information if present in Terraform plan output, has the highest precedence. If subscription information is not available through azurerm_subscription then Cloudability Governance uses the default account configured in preferences of Cloudability Governance Configuration page. If default account is not configured in preferences, then retail (list) pricing will be used.

TF Community customers (through GitHub action) - Provider subscription information within the Terraform plan itself from azurerm_subscription resource or azurerm_subscription data source ( https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription ). This information if present in Terraform plan output has the highest precedence. If subscription information is not available through azurerm_subscription then Cloudability Governance uses "provider-accounts" map as input for GitHub Action if configured. This is second in the order of preference. If subscription information is not available through GitHub action input then Cloudability Governance uses the default account configured in preferences of Cloudability Governance Configuration page. If default account is not configured in preferences, then retail (list) pricing will be used.
