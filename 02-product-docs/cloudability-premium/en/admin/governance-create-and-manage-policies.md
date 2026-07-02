---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Create and Manage Policies"
breadcrumb:
  - "Cloudability Premium"
  - "Governance"
source_path: "admin/governance-create-and-manage-policies.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Create and Manage Policies

Governance allows teams to enforce FinOps best practices through governance policies:

## Types of Policies

1. **Tagging Policies**: Ensure resources have required tags (e.g., "Environment: Production").
2. **Resource Type Policies (AWS/Azure Resource)**: Define rules for resource attributes (e.g.,
   enforces instance size, memory).
3. **Cost Guardrails**: Set maximum allowed cost deltas for IaC changes.

## Enforcement Levels

- **Advisory**: These policy failures do not block the Pull Request workflow. A warning is
  displayed, allowing the workflow to proceed without interruption. **We recommend using this
  enforcement level as a start.**
- **Gated**: These policy failures halt the Pull Request workflow when combined with
  configuration in Github repository to block PR for failed Governance check runs. Users with the
  Cloudability Governance PR Approver Role can override and continue the workflow from the Governance
  Pull Request Details page.

## Implications for HCP Terraform or Terraform Enterprise Customers

HCP Terraform applies its own enforcement level to Run Tasks, which can be set to **Advisory**
or **Mandatory**. This setting can sometimes conflict with the enforcement levels defined in
Cloudability policies.

We recommend configuring the HCP Terraform Run Task enforcement level as **Advisory**. For
example:

- If a Cloudability **Advisory** policy fails, the PR is not blocked, and engineers can still
  apply the change in HCP Terraform.
- If a Cloudability **Gated** policy fails, the PR is blocked, and engineers cannot apply the
  change in HCP Terraform until the issue is resolved.
  - Once the change is reviewed and approved in Cloudability, engineers can merge the PR, and a new
    run must be triggered in HCP Terraform to apply the change.
  - This approval workflow does **not** work if the HCP Run Task is set to **Mandatory**,
    because Cloudability cannot override the HCP status.

## Policy Application

Policies can be applied at the:

- **Organization Level**: Applies to all workflows.
- **Project Level**: Applies to specific deployments.

Policy evaluation results are displayed as PR comments highlighting failing resources and
rules.

Note: Org-level policies are scoped to cloudability org; GitHub org is not relevant, i.e., an
org-wide policy will affect all deployments regardless of which GitHub org they are associated
with.

## Creating a Policy

Navigate to the “Policies” page, select “Resource & Tag”. Follow the 4 steps:

- **Policy Build**: Select a Policy Name & Policy Type (Vendor or Tagging)
- **Policy Type**:

  - Select one of the two enforcement levels.

    You have the option to enforce the selected policies on all existing resources defined in your
    infrastructure code within that directory, not only the resources that have changed in the PR.
  - **For Tagging Policy Type:** you can add tag keys and a tag values. You can leave the “tag
    values” field empty if you want to allow all values

    **Example:** Tag key: “Application”
  - **For Resource Type Policy:**You can create rules by selecting resource types, attributes,
    operators and a value(s). You can enter multiple values and separate them with a comma.
    **Example:** Resource type = “Compute Instance (EC2)” ; Attribute = “Instance Type”; Operator :
    “Not In”; Value: “t4g.medium, t4g.small, t3a.medium”
- **Deployment Scope**: Select at least one project or the whole organization
- **Overview Details**: Review and validate the information entered

## Creating a Cost Guardrail

Navigate to the “Policies” page, select “Cost Guardrails”. You can define a name, select an
enforcement level and specify a max allowed cost limit / delta for each change
