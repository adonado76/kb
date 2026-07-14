---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "06-Governance"
source_files_count: 13
last_updated: "2026-07-13"
---

# 06-Governance

## Create and Manage Policies

<!-- sub-header -->
- **breadcrumb:** Governance > Create and Manage Policies
- **source_path:** SSVCLNQ/admin/governance-create-and-manage-policies.html
- **original_file:** governance-create-manage-policies.md
- **images:** []

Governance allows teams to enforce FinOps best practices through governance policies:

### Types of Policies

1. Tagging Policies : Ensure resources have required tags (e.g., "Environment: Production").
1. Resource Type Policies (AWS/Azure Resource) : Define rules for resource attributes (e.g., enforces instance size, memory).
1. Cost Guardrails : Set maximum allowed cost deltas for IaC changes.

### Enforcement Levels

- Advisory : These policy failures do not block the Pull Request workflow. A warning is displayed, allowing the workflow to proceed without interruption. We recommend using this enforcement level as a start.
- Gated : These policy failures halt the Pull Request workflow when combined with configuration in Github repository to block PR for failed Governance check runs. Users with the Cloudability Governance PR Approver Role can override and continue the workflow from the Governance Pull Request Details page.

### Implications for HCP Terraform or Terraform Enterprise Customers

HCP Terraform applies its own enforcement level to Run Tasks, which can be set to Advisory or Mandatory . This setting can sometimes conflict with the enforcement levels defined in Cloudability policies.

We recommend configuring the HCP Terraform Run Task enforcement level as Advisory . For example:

- If a Cloudability Advisory policy fails, the PR is not blocked, and engineers can still apply the change in HCP Terraform.
- If a Cloudability Gated policy fails, the PR is blocked, and engineers cannot apply the change in HCP Terraform until the issue is resolved. Once the change is reviewed and approved in Cloudability, engineers can merge the PR, and a new run must be triggered in HCP Terraform to apply the change. This approval workflow does not work if the HCP Run Task is set to Mandatory , because Cloudability cannot override the HCP status.

### Policy Application

- Organization Level : Applies to all workflows.
- Project Level : Applies to specific deployments.

Policy evaluation results are displayed as PR comments highlighting failing resources and rules.

### Creating a Policy

- Policy Build : Select a Policy Name & Policy Type (Vendor or Tagging)
- Policy Type : Select one of the two enforcement levels. You have the option to enforce the selected policies on all existing resources defined in your infrastructure code within that directory, not only the resources that have changed in the PR. For Tagging Policy Type: you can add tag keys and a tag values. You can leave the “tag values” field empty if you want to allow all values Example: Tag key: “Application” For Resource Type Policy: You can create rules by selecting resource types, attributes, operators and a value(s). You can enter multiple values and separate them with a comma. Example: Resource type = “Compute Instance (EC2)” ; Attribute = “Instance Type”; Operator : “Not In”; Value: “t4g.medium, t4g.small, t3a.medium”
- Deployment Scope : Select at least one project or the whole organization
- Overview Details : Review and validate the information entered

### Creating a Cost Guardrail

Navigate to the “Policies” page, select “Cost Guardrails”. You can define a name, select an enforcement level and specify a max allowed cost limit / delta for each change

---

## Governance - Getting Started

<!-- sub-header -->
- **breadcrumb:** Governance > Governance - Getting Started
- **source_path:** SSVCLNQ/admin/governance-getting-started.html
- **original_file:** governance-getting-started.md
- **images:**
  - 03-media/apptio-cloudability-standard/Workflow_Terraform.png
  - 03-media/apptio-cloudability-standard/Terraform2.png

### What you can do with Cloudability Governance

Shape Our Governance Roadmap: 2‑Minute Survey

Cloudability Governance empowers teams to proactively manage cloud costs and enforce FinOps policies directly within developer workflows. With this feature, you can:

- Estimate Costs Before Deployment: Get real-time cost estimates for cloud resources, including custom pricing and EA discounts, directly in GitHub and HCP Terraform
- Optimize Resource Selection: Receive recommendations for lower-cost AWS EC2 and RDS alternatives with similar configurations
- Enforce Policies at the IaC Level: Ensure compliance by enforcing mandatory tag keys/values, blocking legacy resource provisioning, and setting budget thresholds for teams and applications.
- Monitor Compliance: Use a centralized dashboard to track adherence to FinOps policies across your organization.
- Manage Non-Compliant PRs: Identify and review pull requests that violate cost or policy rules, with built-in approval workflows

This feature shifts cloud cost management from reactive to proactive, helping prevent overspending and policy violations before infrastructure is deployed.

### Supported Integrations

- IaC tooling : HCP Terraform, Terraform Enterprise, Terraform Editions (version 1.10.5); Terragrunt (version 0.72.6)
- VCS: GitHub.com, GitHub Enterprise Server
- Cloud Provider: AWS, Azure

### Workflow - HCP Terraform/Terraform Enterprise

Capabilities represented in the diagram are available for VCS-driven workflow and for customers that use GitHub.

- Workflow triggers driven by CLI or API do not appear on the Cloudability Governance → Pull Request page.
- Status update and validation checks are not posted back to the initiating environment (Github PR page if created)
- Governance actions such as policy validation, enforcement blocking, or manual approval are unavailable through Cloudability Governance interface.

### Workflow - Terraform Community

### Overview of permissions

Cloudability Governance access is controlled through four specific permissions. Ensure that you have the right roles/permissions assigned.

- GovernanceFeatureViewOnly - This permission allows users to view all the pages under Cloudability "Governance" feature menu item. This permission is included in “Cloudability User” role.
- GovernanceFeatureConfigurationFullAccess - This permission allows users to access the configuration functionality (view, create, update configuration details). This permission is included in “Cloudability Admin” and “Cloudability Governance Automation User” role.
- GovernanceFeaturePolicyFullAccess - This permission allows user the access the policy configuration functionality (view, create, update policies) under the Cloudability "Governance" feature menu item. This permission is included in “Cloudability Governance Policy Admin” role.
- GovernanceFeaturePRApproval - This permission allows users to approve Pull Requests that are blocked when they don’t comply with policies. This permission is included in “Cloudability Governance PR Approver” role.

### Security – How your code and CSP infrastructure are protected

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

---

## Pull Requests - Approval Workflow

<!-- sub-header -->
- **breadcrumb:** Governance > Pull Requests - Approval Workflow
- **source_path:** SSVCLNQ/admin/governance-pull-requests-and-approval-workflow.html
- **original_file:** governance-pull-requests-approval-workflow.md
- **images:** []

Governance integrates with GitHub to manage PR approvals. As a reminder, PRs that don’t comply with the “Gated” enforcement level are blocked but they can be unblocked by users with the “Cloudability Governance PR Approver” role.

GitHub Configuration

GitHub repository owner needs to create a branch protection rule which requires Governance check runs to pass before merging.

1. Navigate to the "Pull Requests" tab in the Governance dashboard and review PRs that require approval. Only PRs that are “open” and that have a “failed” status can be approved.
1. Select the PR and click "Approve."
1. In GitHub, the PR check run status updates to "Pass," allowing the Cloud Engineer to merge that change.

---

## Resource Recommendations

<!-- sub-header -->
- **breadcrumb:** Governance > Resource Recommendations
- **source_path:** SSVCLNQ/admin/governance-resource-recommendations.html
- **original_file:** governance-resource-recommendations.md
- **images:** []

Governance provides recommendations for new EC2 and RDS resources being deployed when a similar configuration (matching CPU and Memory requirements) is available at a lower cost. Recommendations are posted as comments on the pull request (PR).

If Governance does not identify a more cost-effective resource, no recommendation will be posted.

Example: Upgrade RDS instance from db.m5.8xlarge to db.m6g.8xlarge to save costs while maintaining performance.

---

## Setup Cloudability Governance

<!-- sub-header -->
- **breadcrumb:** Governance > Setup Cloudability Governance
- **source_path:** SSVCLNQ/admin/governance-setup-cldy-governance.html
- **original_file:** governance-setup-cloudability.md
- **images:** []

### Before You Begin

This documentation is intended for the following roles within an organization:

- Platform Admins – They are responsible for configuring the feature and installing the GitHub app. For organizations using HCP or Terraform Enterprise, they will need to configure the Cloudability Governance Run Task and ensure it is aligned with organizational guardrails.
- FinOps Teams – They will define and manage their organization policies (such as approved instance families, required tags, or regional restrictions).
- Cloud Engineers – They will consume the integration of Cloudability Governance with GitHub and Terraform. Developers run Terraform plans and applies as part of their workflows and receive immediate cost and compliance feedback.

To successfully use this feature, ensure you have the following prerequisites in place:

- For GitHub Users: Repository containing sample Terraform code. IP Allow List - If your GitHub organization uses an IP allow list, you must ensure that Cloudability’s outbound IP ranges are included. Without these entries, Cloudability Governance will not be able to communicate with your GitHub repositories, and policy checks may fail. The following IP ranges should be added to your GitHub organization’s allow list: 185.115.88.0/22 103.195.128.0/22 129.41.0.0/22
- An IBM Cloudability account with the right Governance permissions assigned.
- For HCP Terraform / Terraform customers : An HCP Terraform account with permissions to create workspaces and manage Run Tasks.
- For Terraform Community users : GitHub Actions are available in your GitHub account.

### Overview

To set up Governance, Cloudability Admins need to configure Github integration, which will be used for the Pull Requests (PR) approval workflow across all customer types. Then, depending on the Terraform platform in use, setup steps differ:

- For HCP Terraform or Terraform Enterprise users , GitHub Actions are not required. Instead, Admins must configure a Run Task within their Terraform workspace by retrieving the HMAC key and endpoint URL from Cloudability and adding them to the Run Task configuration.
- For Terraform Community users , Admins need to set up a few organization-level variables/secrets in GitHub to store Frontdoor API keys, the Frontdoor URL, Frontdoor Environment ID, and Cloudability API URL. They also need to create or configure their own GitHub Action workflows that invoke the Cloudability Governance GitHub Actions.

Once completed, Governance will identify their “deployments” (units managed by Terraform, also called “workspaces” in HCP Terraform) and display them in the Governance Configuration page. Users will need to map them to projects (which are groups of deployments), which will have policies associated with them. Customers can choose to define projects by application, team, service or environment. A project name for a deployment can also be provided as optional input within GitHub action workflow itself.

---

## Configure GitHub Actions for Terraform Community

<!-- sub-header -->
- **breadcrumb:** Governance > Setup Cloudability Governance > Configure GitHub Actions for Terraform Community
- **source_path:** SSVCLNQ/admin/governance-configure-github-actions-for-terraform-community.html
- **original_file:** governance-configure-github-actions-terraform-community.md
- **images:** []

For users leveraging Terraform Community, Cloudability Governance GitHub Action is triggered as part of the CI/CD workflow for pull requests. This integration enables Cloudability Governance to provide cost-related insights directly within the PR via comments and GitHub check runs.

Please refer to this page to get the latest information/updates: https://GitHub.com/IBM/ibm-cloudability-governance/blob/main/README.md

Prerequisite: Ensure that you have installed IBM Cloudability GitHub app before proceeding with your GitHub Actions configuration.

Inputs required for Governance GitHub Actions:

1. Output of the terraform plan for the change in PR - Run terraform plan for the changes in PR. Customers can configure this in GitHub action based on how on their terraform code is organized and configured.

You can find in this link https://GitHub.com/IBM/ibm-cloudability-governance examples to update GitHub Actions for repositories that contains IaC code for one deployment or multiple ones.

The example uses aws-actions/configure-aws-credentials@v4.1.0 GitHub action to fetch AWS credentials to be able to run terraform plan. GitHub variables/secrets can be used to store the ARN of the AWS_ROLE to be used here. Customers can also choose to achieve this through other ways as well.

1. Example where a repo contains IaC code for only one deployment: name: Demo Pipeline run-name: Deployment on: pull_request: types: [opened, reopened, synchronize] paths: - '**.tf' - 'usage.yaml' - '!README.md' jobs: terraform: runs-on: ubuntu-latest permissions: id-token: write contents: read defaults: run: shell: bash # Can change to specific directory here where Terraform files are present working-directory: ./ steps: - name: Checkout repository uses: actions/checkout@v4 - name: Setup AWS credentials uses: aws-actions/configure-aws-credentials@v4.1.0 with: aws-region: us-west-2 role-to-assume: ${{ secrets.AWS_ROLE }} role-session-name: ${{ GitHub.run_id }} - name: Setup Terraform with specified version on the runner uses: hashicorp/setup-terraform@v3 with: terraform_version: 1.10.5 terraform_wrapper: false - name: Terraform init id: init run: terraform init - name: Terraform plan id: plan run: | terraform plan -lock=false -input=false -out=tfplan terraform show -json tfplan > tfplan.json continue-on-error: false - name: Redact secrets from tfplan run: | sed -i 's/"password":"[^"]*"/"password":""/g' tfplan.json sed -i 's/"secret_string":"{[^}]*}"/"secret_string":""/g' tfplan.json
1. Frontdoor API Keys - Frontdoor token is needed to invoke Governance actions. Below GitHub action should be able to fetch Frontdoor token using the provided API keys. Can set the following variables as GitHub variables/secret FD_URL (example: https://frontdoor.apptio.com ) FD_KEY (Generate API key and Secret for a Frontdoor user with role “Cloudability Governance Automation User”) FD_SECRET (Generate API key and Secret for a Frontdoor user with role “Cloudability Governance Automation User”) - name: Get Frontdoor token uses: cloudability/costguard-GitHub-action/actions/frontdoor/login@main with: fd-url: ${{ secrets.FD_URL }} fd-public-key: ${{ secrets.FD_KEY }} fd-secret-key: ${{ secrets.FD_SECRET }}
1. Metadata – The metadata associated with a pull-request and Cloudability Governance is required to capture Governance configuration for customers organization. Get GitHub PR metadata - Call GitHub API to fetch metadata related to the PR from GitHub - name: Get GitHub PR metadata uses: ibm/ibm-cloudability-governance/actions/GitHub-info@v0.1.0 with: GitHub-token: ${{ secrets.GitHub_TOKEN }} pr-number: ${{ GitHub.event.pull_request.number }} Run Cloudability Governance Metadata Retrieval - Fetch metadata related to Governance configuration (project, deployment, pull request, GitHub app installations) from Cloudability - name: Run Cloudability Governance Metadata Retrieval uses: ibm/ibm-cloudability-governance/actions/metadata@v0.1.0 with: cloudability-host: ${{ vars.CLOUDABILITY_HOST }} fd-env-id: ${{ secrets.FD_ENV_ID }} Download tfplan (optional) - If terraform plan is uploaded as artifact in a separate job This step requires the Frontdoor Environment Id for customers Cloudability organization and the Cloudability url host. They can be set as GitHub repository secrets or variables. FD_ENV_ID (Frontdoor Environment Id) CLOUDABILITY_HOST (example: https://api.cloudability.com )
1. Governance – The next steps allow you to get insights on cost estimation, policy evaluation, alternative recommendations For these three steps, the input needed is “provider-accounts” map. It is a mapping from terraform provider key to cloud vendor (AWS) account id. This is needed to fetch the pricing information from the correct cloud vendor (AWS) account id. The provider key can either be “*” which indicates that it’s the default account for all providers, or the exactly provider config key shown in the configuration.provider_config map in a terraform plan json. For example, if a provider with local name “aws_usw2” is defined in a module called “database” and the root terraform module is calling the “database” module, the provider key will be module.database:aws_usw2. Example for a deployment to a single cloud vendor account (use * for key in provider-accounts map) - name: Run Cloudability Cost Estimation uses: ibm/ibm-cloudability-governance/actions/cost-estimation@v0.1.0 with: GitHub-token: ${{ secrets.GitHub_TOKEN }} pr-number: ${{ GitHub.event.pull_request.number }} cloudability-host: ${{ secrets.CLOUDABILITY_HOST }} fd-env-id: ${{ secrets.FD_ENV_ID }} deployment-name: "demo" provider-accounts: | { "*": { "account_id": "${{ secrets.AWS_ACCOUNT_ID }}", "vendor": "aws" } } tf-plan: "tfplan.json" resource-usage: "usage.json" - name: Run Cloudability Governance Policy Evaluation uses: ibm/ibm-cloudability-governance/actions/policy-evaluation@v0.1.0 with: GitHub-token: ${{ secrets.GitHub_TOKEN }} pr-number: ${{ GitHub.event.pull_request.number }} cloudability-host: ${{ secrets.CLOUDABILITY_HOST }} fd-env-id: ${{ secrets.FD_ENV_ID }} deployment-name: "demo" provider-accounts: | { "*": { "account_id": "${{ secrets.AWS_ACCOUNT_ID }}", "vendor": "aws" } } tf-plan: "tfplan.json" resource-usage: "usage.json" - name: Run Cloudability Recommendation uses: ibm/ibm-cloudability-governance/actions/recommendation@v0.1.0 with: GitHub-token: ${{ secrets.GitHub_TOKEN }} pr-number: ${{ GitHub.event.pull_request.number }} cloudability-host: ${{ secrets.CLOUDABILITY_HOST }} fd-env-id: ${{ secrets.FD_ENV_ID }} deployment-name: "demo" provider-accounts: | { "*": { "account_id": "${{ secrets.AWS_ACCOUNT_ID }}", "vendor": "aws" } } tf-plan: "tfplan.json" resource-usage: "usage.json" Alternatively, this is the setup for a scenario with a specific account alias. - name: Run Cloudability Cost Estimation uses: ibm/ibm-cloudability-governance/actions/cost-estimation@v0.1.0 with: GitHub-token: ${{ secrets.GitHub_TOKEN }} pr-number: ${{ GitHub.event.pull_request.number }} cloudability-host: ${{ secrets.CLOUDABILITY_HOST }} fd-env-id: ${{ secrets.FD_ENV_ID }} deployment-name: "demo" provider-accounts: | { "module.database:aws_usw2": { "account_id": "${{ secrets.AWS_ACCOUNT_ID }}", "vendor": "aws" }, "*": { "account_id": "${{ secrets.SECOND_AWS_ACCOUNT_ID }}", "vendor": "aws" } } tf-plan: "tfplan.json" resource-usage: "usage.json" pr-number: ${{ GitHub.event.pull_request.number }} cloudability-host: ${{ secrets.CLOUDABILITY_HOST }} fd-env-id: ${{ secrets.FD_ENV_ID }} deployment-name: "demo" provider-accounts: | { "module.database:aws_usw2": { "account_id": "${{ secrets.AWS_ACCOUNT_ID }}", "vendor": "aws" } } tf-plan: "tfplan.json" resource-usage: "usage.json"

---

## Deployment Configurations

<!-- sub-header -->
- **breadcrumb:** Governance > Setup Cloudability Governance > Deployment Configurations
- **source_path:** SSVCLNQ/admin/governance-deployment-configurations.html
- **original_file:** governance-deployment-configurations.md
- **images:**
  - 03-media/apptio-cloudability-standard/gov6.png

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

---

## GitHub Enterprise Server (on-prem) App Installation

<!-- sub-header -->
- **breadcrumb:** Governance > Setup Cloudability Governance > GitHub Enterprise Server (on-prem) App Installation
- **source_path:** SSVCLNQ/admin/governance-github-enterprise-installation.html
- **original_file:** governance-github-enterprise-server-prem-app-installation.md
- **images:** []

This guide explains how to register a GitHub App within Cloudability for use with GitHub Enterprise Server (GHES). This process allows you to connect and manage your GHES repositories within the Cloudability Governance workflow.

### Prerequisites

- Access to a Cloudability instance with Governance permissions.
- Administrative access to your GitHub Enterprise Server instance.

### Step-by-Step Instructions

1. Navigate to Configuration In the Cloudability sidebar, go to Governance > Configuration . Select the Integrations tab and choose GitHub Enterprise from the left-hand menu.
1. Initiate Registration Click the Register GitHub App button located at the top right of the GitHub Enterprise section.
1. Enter App Details A "Register a New GitHub App" modal will appear. Provide the following information: Account Type: Select either Personal Account or Organization Account . When selecting Organization Account , user will also have to enter the unique identifier for their GitHub organization. App Name: Enter a unique name for your application. HTML URL: Provide the base URL of your GitHub Enterprise Server. API URL: Enter the API endpoint for your server (typically https://[your-ghes-domain]/api/v3 ). Click Submit to continue.
1. Authenticate with GitHub Enterprise The system will redirect you to your GitHub Enterprise Server. If prompted, sign in using your enterprise credentials or identity provider (SSO). Once authenticated, you will see a GitHub confirmation page. Click Create GitHub App for [Your Name/Org] .
1. Finalize the Integration After clicking create, you will be automatically redirected back to the Cloudability interface. A success message ("Successfully created GitHub Enterprise app") will appear briefly.
1. Verify Registration The new application will now be listed under the GitHub Enterprise App column. You can proceed to click Install next to the app name to select specific repositories for integration.

### Troubleshooting

- Redirect Issues: If your browser does not automatically redirect you during the authentication steps, look for the "click here" links provided on the transition screens.
- API URL Errors: Ensure the API URL includes the /api/v3 suffix, as this is required for Cloudability to communicate with GitHub Enterprise Server.

---

## GitHub.com (Cloud) App Installation

<!-- sub-header -->
- **breadcrumb:** Governance > Setup Cloudability Governance > GitHub.com (Cloud) App Installation
- **source_path:** SSVCLNQ/admin/governance-github-app-installation.html
- **original_file:** governance-githubcom-cloud-app-installation.md
- **images:**
  - 03-media/apptio-cloudability-standard/Gov3.png
  - 03-media/apptio-cloudability-standard/Gov4.png

A GitHub app is used to set/update check run status in the pull request. Customers need to install IBM Cloudability GitHub app in their GitHub organizations by accessing the installation link from Governance configuration page. To install the app, the user who performs these operations needs to have admin permissions for the GitHub org or for the repositories in the org.

Below is the first landing page for Governance. The first action that needs to be taken is to install IBM Cloudability GitHub App in customer’s GitHub org.

![image](../images/Gov3.png)

1. Click on “Install GitHub App” link (present in front and center of Settings tab if setting up for the first time) to access the installation link from the Governance page.
1. You will be redirected to GitHub · Build and ship software on a single, collaborative platform for the installation.
1. Choose the GitHub organization and then you can install the app for all repositories or only selected repositories in that GitHub organization. Once the GitHub org is selected, an option will be given to: install the app to access all repositories in the GitHub org only selected repositories in the GitHub org
1. When installing the app, the following permissions are required: Read-only access to metadata (To be able to identify pull requests metadata) Read/write access to pull requests (Write access to pull requests is needed to be able to post comments to the pull requests) Read and write access to checks (Need to set and update check run state results)

Once access is granted, the page redirects back to the Cloudability Governance page.

---

## HCP Terraform/Terraform Enterprise

<!-- sub-header -->
- **breadcrumb:** Governance > Setup Cloudability Governance > HCP Terraform/Terraform Enterprise
- **source_path:** SSVCLNQ/admin/governance-hcp-terraform-terraform-enterprise.html
- **original_file:** governance-hcp-terraformterraform-enterprise.md
- **images:**
  - 03-media/apptio-cloudability-standard/Gov5.png

### Overview

Cloudability Governance integrates with HCP Terraform and Terraform Enterprise via a Run Task , enabling automated cost analysis and policy enforcement during pull request workflows.

Once configured, the Run Task evaluates Terraform plans and provides real-time feedback — flagging cost risks, missing tags, and non-compliant resources — before deployment.

Prerequisite: Ensure that you have installed IBM Cloudability GitHub app before proceeding with the Run Task set up.

### Generate Credentials in Cloudability

1. In the Cloudability UI, go to Configuration > Integrations .
1. Generate a Callback URL and HMAC Key . These credentials authenticate and route Run Task callbacks from HCP Terraform. Each key pair represents a single HCP credential for your organization.

### Create a Run Task in HCP Terraform

1. In the HCP Terraform UI, navigate to Settings → Integrations → Run Tasks .
1. Create a new Run Task with the following details: Stage : Post-plan Endpoint URL : Use the Callback URL from Cloudability HMAC Key : Use the key generated in Cloudability Enforcement Level : Choose Advisory (warn only) or Mandatory (block on failure). Tip: Start with Advisory to evaluate impact before enforcing.
1. Attach the Run Task to one or more workspaces: You can apply it globally to all workspaces or attach it individually. Reusing a single Run Task across multiple workspaces is recommended. Once the setup is complete, head to the Deployment Configuration page.

### Configuration with Terraform Enterprise

If your Terraform Enterprise instance is hosted behind a firewall, ensure it allows incoming requests from Cloudability so that Run Task results can be posted successfully.

Refer to the Terraform Enterprise Run Task API documentation for technical details on callback configuration.

If you run into any issues, reach out to your Cloudability Account Team. They will connect you with the Product Team for support.

### How to include provider-account information in Terraform plan output

For AWS resources, this can be achieved by include aws_caller_identity as data source in your Terraform files.

For Terraform files that deploy resources to a single account, it can be done by adding the following line in your Terraform configuration.

```
data "aws_caller_identity" "defaultidentity" {}
```

```
data "aws_caller_identity" "engineering" {
  provider = aws.engineering
}
data "aws_caller_identity" "staging" {
  provider = aws.staging
}
```

### Integrate your custom pricing and add your usage information for more accurate cost estimation

- Please refer to IBM Cloudability documentation here to see how to get more accurate cost estimation, inclusive of your custom pricing.
- Please refer to IBM Cloudability documentation here to add usage information to get more accurate cost estimation

---

## Preferences Configuration

<!-- sub-header -->
- **breadcrumb:** Governance > Setup Cloudability Governance > Preferences Configuration
- **source_path:** SSVCLNQ/admin/governance-preferences-configurations.html
- **original_file:** governance-preferences-configuration.md
- **images:** []

Overview

In order to fetch account specific pricing, Cloudability Governance currently looks for provider account information as follows:

AWS Resources

HCP TF/Terraform Enterprise customers - Provider account information within the Terraform plan itself from aws_caller_identity data source ( https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity ). This information if present in Terraform plan output, has the highest precedence. If account information is not available through aws_caller_identity then Cloudability Governance uses the default account configured in preferences of Cloudability Governance Configuration page. If default account is not configured in preferences, then retail (list) pricing will be used.

TF Community customers (through GitHub action) - Provider account information within the Terraform plan itself from aws_caller_identity data source ( https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity ). This information if present in Terraform plan output has the highest precedence. If account information is not available through aws_caller_identity then Cloudability Governance uses "provider-accounts" map as input for GitHub Action if configured. This is second in the order of preference. If account information is not available through GitHub action input then Cloudability Governance uses the default account configured in preferences of Cloudability Governance Configuration page. If default account is not configured in preferences, then retail (list) pricing will be used.

Azure Resources

For Azure resources, Cloudability Governance looks for subscription information in the following order of precedence:

HCP TF/Terraform Enterprise customers - Provider subscription information within the Terraform plan itself from azurerm_subscription resource or azurerm_subscription data source ( https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription ). This information if present in Terraform plan output, has the highest precedence. If subscription information is not available through azurerm_subscription then Cloudability Governance uses the default account configured in preferences of Cloudability Governance Configuration page. If default account is not configured in preferences, then retail (list) pricing will be used.

TF Community customers (through GitHub action) - Provider subscription information within the Terraform plan itself from azurerm_subscription resource or azurerm_subscription data source ( https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription ). This information if present in Terraform plan output has the highest precedence. If subscription information is not available through azurerm_subscription then Cloudability Governance uses "provider-accounts" map as input for GitHub Action if configured. This is second in the order of preference. If subscription information is not available through GitHub action input then Cloudability Governance uses the default account configured in preferences of Cloudability Governance Configuration page. If default account is not configured in preferences, then retail (list) pricing will be used.

---

## Troubleshooting

<!-- sub-header -->
- **breadcrumb:** Governance > Troubleshooting
- **source_path:** SSVCLNQ/admin/governance-troubleshooting.html
- **original_file:** governance-troubleshooting.md
- **images:** []

Before troubleshooting, ensure the following are completed:

- You have the correct Cloudability role and permissions assigned.
- The IBM Cloudability GitHub App is installed in your GitHub org.
- HCP / TFE Customers: Run Task has been configured.
- Terraform Community Customers: Your GitHub Actions workflows are set up to invoke Cloudability Governance actions and the Required GitHub secrets are configured. Terraform plan output is available in the PR workflow

### Troubleshooting Details

| Problem | Possible Cause | Resolution |
| --- | --- | --- |
| “Access Denied” is displayed in Cloudability UI Missing Governance Features – example: inability to create policies | Incorrect role/permissions assignment in Cloudability | Ensure your user has the appropriate permissions listed in Overview of permissions |
| Cannot Install GitHub App | Lack of admin permissions in GitHub. Attempting to install from the wrong location. | Ensure you are a GitHub Org Admin or have admin access to the target repositories . Use the “Install GitHub App” link from the Governance Settings tab in Cloudability. |
| GitHub App Installed but Not Working | App not granted access to required repositories. Missing permissions during installation. | Reinstall the app and ensure: It has read-only access to metadata and pull requests. It has read/write access to checks. It is installed for all or selected repositories containing Terraform code. |
| A PR change is blocked due to a failed gated policy in Cloudability and is not getting approved |  | Please request a review and approval from a user with either the GovernanceFeaturePRApproval permission or the Cloudability Governance PR Approver role. If the approver is temporarily unavailable and the PR needs to be unblocked urgently, you have two options: Ask a GitHub Admin to temporarily remove the branch protection rule that requires Governance check runs to pass before merging. Ask a user with GovernanceFeaturePolicyFullAccess permission or the Cloudability Governance Policy Admin role to temporarily update the policy scope so that it does not apply to the project associated with this specific PR |
| GitHub Action Fails to Run (for Terraform Community users) | Missing secrets or incorrect environment variables. Terraform plan not generated. | Verify the following GitHub secrets are set: FD_URL (e.g., https://frontdoor.apptio.com ) FD_KEY and FD_SECRET (from a user with “Cloudability Governance Automation User” role) FD_ENV_ID CLOUDABILITY_HOST (e.g., https://api.cloudability.com) Ensure your workflow includes: Terraform plan generation Metadata retrieval steps Frontdoor token fetch step Note: Note: Cloudability Governance expects only one top level terraform plan json for each invocation. |
| A PR change that failed a gated Cloudability policy has been approved but the change can’t be applied in HCP | The HCP Run task has its own enforcement level that can be set as advisory or mandatory. If its enforcement is set as Mandatory, and a gated policy failed, the change can’t be applied, regardless of the approval. | Update the Run Task enforcement level to “Advisory” and trigger another run to allow the change to be applied. |
| Repositories don't show up after installing GitHub App | The issue happens because the installation is split into two stages via GitHub's approval workflow. When an admin approves the pending installation later, the original session context is lost. As a result, Cloudability is never notified that the installation completed. | Delete the current, incomplete installation. Re-install the App using a GitHub account that holds immediate installation permissions to complete the process in a single step. |

---

## Usage and Configuration-Based Cost Estimation

<!-- sub-header -->
- **breadcrumb:** Governance > Usage and Configuration-Based Cost Estimation
- **source_path:** SSVCLNQ/admin/governance-usage-and-configuration-based-cost-estimation.html
- **original_file:** governance-usage-configuration-based-cost-estimation.md
- **images:** []

Cloudability Governance can estimate costs directly from your Terraform configuration. In addition to configuration-based estimates, you can optionally provide usage-based input parameters for specific resources. These inputs help generate more accurate and tailored cost projections based on your anticipated consumption. For services that require usage data — such as AWS Lambda, SQS, and others — a default usage value will be used when no custom input is provided. If you supply your own expected usage values, they will always override the defaults.

### Terraform/Terragrunt

Terraform Community / GitHub Actions

If you are using GitHub Actions or the Terraform Community edition:

- Cloudability Governance is triggered by a Github action defined for the repository. The expected usage input can be specified through a file usage.json and specified as an input to the IBM/ibm-cloudability-governance/actions/cost-estimation Github Action. You can find an example here: https://github.com/IBM/ibm-cloudability-governance/blob/main/example-workflows/single-deployment/workflow.yaml#L95

HCP Terraform / Terraform Enterprise (TFE)

If you are using HCP Terraform / Terraform Enterprise:

- Cloudability Governance is triggered by a Run Task associated with a specific workspace defined in HCP Terraform.

- If a "usage.json" file is present in the workspace's configured working directory , Cloudability Governance will automatically detect and applies the usage values from this file during cost estimation.

- The file name must match the name "usage.json".

This ensures that usage-based inputs are consistently applied whenever cost estimation is performed for that workspace.

Example of usage.json

```

{
  "version": "0.1",
  "resource_usage": {
    "aws_instance.costguard_demo_ec2_1": {
      "os": "linux_unix"
    },
    "aws_instance.costguard_demo_ec2_2": {
      "term_type": "compute_savings_plan",
      "purchase_option": "partial_upfront",
      "lease_contract_length": "3yr"
    }
  }
}

```

| Key | Description |
| --- | --- |
| Example: "aws_instance.costguard_demo_ec2_1" | Resource Description |
| "os" | Resource Property |
| "linux_unix" | The value being set |

```

version: "0.1" # Version of the schema
resource_usage: # All resource usage values should be listed here
  # The resource is identified as <terraform_resource_name>.<resource_identifier>
  aws_instance.costguard_demo_ec2:
    # Each field represents a specific attribute and its expected usage
    # <attribute_field_name>:<expected_value>
    os: "linux_unix"
  aws_instance.costguard_demo_ec2_2:
    term_type: "compute_savings_plan"
    purchase_option: "partial_upfront"
    lease_contract_length: "3yr"

```

Estimates are displayed as PR comments, providing insights into monthly costs based on usage inputs.

### Supported AWS Service Types

1. EC2
1. EBS
1. EBS Snapshot
1. ElasticMapReduce (EMR)
1. S3
1. RDS
1. ElasticCache
1. DynamoDB
1. Lambda
1. SNS
1. SQS
1. SecretManager
1. EventBridge
1. VPC
1. RedShift
1. Cloudwatch
1. Key Management Service (KMS)
1. FSx
1. Database Migration Service
1. Elastic File System
1. Elastic Load Balancing (ELB)
1. OpenSearch
1. Web Application Firewall (WAF)
1. Glue
1. ECS

### AWS Usage Input details per service type

Compute Resources

aws_instance

```

count:
  desc: Number of instances to launch
term_type:
  values: ["compute_savings_plan", "ec2_savings_plan", "standard_reserved_instance", "convertible_reserved_instance"]
  desc: Type of pricing model
purchase_option:
  values: ["all_upfront", "partial_upfront", "no_upfront"]
  desc: Payment option for reserved instances
lease_contract_length:
  values: ["1yr", "3yr"] or ["1_year", "3_year"]
  desc: Duration of lease in years

```

aws_launch_template

```

count:
  desc: Number of instances to launch
term_type:
  values: "reserved" or "on_demand"
  desc: Type of pricing model
purchase_option:
  values: ["all_upfront", "partial_upfront", "no_upfront"]
  desc: Payment option for reserved instances
lease_contract_length:
  values: ["1yr", "3yr"] or ["1_year", "3_year"]
  desc: Duration of lease in years

```

Database Resources

aws_db_instance

```

term_type:
  values: "reserved" or "on_demand"
  desc: Type of pricing model
purchase_option:
  values: ["all_upfront", "partial_upfront", "no_upfront"]
  desc: Payment option for reserved instances
lease_contract_length:
  values: "1" or "3"
  desc: Duration of lease in years

```

aws_rds_cluster

```

acu_per_hour:
  desc: Aurora Capacity Units per hour for Aurora Serverless V2
aurora_storage_gb:
  desc: Amount of Aurora storage in GB for Aurora Serverless V2

```

aws_dynamodb_table

```

storage_gb:
  desc: Amount of data stored in the table in GB
strongly_consistent_reads_per_month:
  desc: Number of strongly consistent read requests per month
eventually_consistent_reads_per_month:
  desc: Number of eventually consistent read requests per month
transaction_reads_per_month:
  desc: Number of transactional read requests per month
standard_writes_per_month:
  desc: Number of standard write requests per month
transaction_writes_per_month:
  desc: Number of transactional write requests per month
average_item_byte_size:
  desc: Average size of items stored in bytes

```

aws_elasticache_cluster, aws_elasticache_replication_group

```

term_type:
  values: "reserved" or "on_demand"
  desc: Type of pricing model
purchase_option:
  values: ["all_upfront", "partial_upfront", "no_upfront", "heavy_utilization"]
  desc: Payment option for reserved instances
lease_contract_length:
  values: "1" or "3"
  desc: Duration of lease in years

```

aws_redshift_cluster

```

term_type:
  values: "on_demand", "reserved"
  desc: Type of pricing model
backup_storage_gb:
  desc: Backup storage beyond included amount in GB
spectrum_data_scanned_tb:
  desc: Amount of data scanned by Redshift Spectrum in TB
managed_storage_gb:
  desc: Amount of managed storage in GB
data_transfer_gb:
  desc: Amount of data transferred in GB
utilization_hours:
  desc: Number of hours the cluster is utilized per month

```

aws_dms_replication_config

```

avg_dcu:
  desc: Average Data Capacity Units for DMS Serverless replication (default minimum is 1)

```

Storage Resources

aws_ebs_volume

```

count:
  desc: Number of volumes to create
iops:
  desc: Provisioned IOPS (only for io1, io2 volume types)
throughput:
  desc: Throughput in MiB/s (only for gp3 volume type)

```

aws_ebs_snapshot

```

count:
  desc: Number of snapshots
write_churn_rate:
  desc: Fraction of volume size written between snapshots (e.g. 0.01 = 1%)
snapshot_interval_days:
  desc: Number of days between snapshots

```

aws_fsx_lustre_file_system

```

compression_factor:
  desc: Data compression ratio for storage optimization
backup_storage_gb:
  desc: Amount of backup storage in GB

```

aws_s3_bucket

```

standard_storage:
  storage_gb:
    desc: Amount of data stored in standard storage class in GB
  rw_requests:
    desc: Number of read-write API requests per month for standard storage
  ro_requests:
    desc: Number of read-only API requests per month for standard storage
  select_data_returned_gb:
    desc: Amount of data returned by S3 Select in GB
  select_data_scanned_gb:
    desc: Amount of data scanned by S3 Select in GB
standard_ia_storage:
  storage_gb:
    desc: Amount of data stored in standard IA storage class in GB
  rw_requests:
    desc: Number of read-write API requests per month for standard IA storage
  ro_requests:
    desc: Number of read-only API requests per month for standard IA storage
  select_data_returned_gb:
    desc: Amount of data returned by S3 Select in GB
  select_data_scanned_gb:
    desc: Amount of data scanned by S3 Select in GB
  lifecycle_transition_requests:
    desc: Number of lifecycle transition requests
  retrieval_data_gb:
    desc: Amount of data retrieved in GB
glacier_da_storage:
  storage_gb:
    desc: Amount of data stored in Glacier Deep Archive in GB
  avg_object_size_mb:
    desc: Average object size in MB
  rw_requests:
    desc: Number of read-write API requests per month
  lifecycle_transition_requests:
    desc: Number of lifecycle transition requests
  restore_standard_requests:
    desc: Number of standard restore requests
  restore_bulk_requests:
    desc: Number of bulk restore requests
  data_standard_retrieval_gb:
    desc: Amount of data retrieved via standard retrieval in GB
  data_bulk_retrieval_gb:
    desc: Amount of data retrieved via bulk retrieval in GB
glacier_ir_storage:
  storage_gb:
    desc: Amount of data stored in Glacier Instant Retrieval in GB
  rw_requests:
    desc: Number of read-write API requests per month
  ro_requests:
    desc: Number of read-only API requests per month
  lifecycle_transition_requests:
    desc: Number of lifecycle transition requests
  retrieval_data_gb:
    desc: Amount of data retrieved in GB
  select_data_returned_gb:
    desc: Amount of data returned by S3 Select in GB
  select_data_scanned_gb:
    desc: Amount of data scanned by S3 Select in GB
glacier_fr_storage:
  storage_gb:
    desc: Amount of data stored in Glacier Flexible Retrieval in GB
  avg_object_size_mb:
    desc: Average object size in MB
  rw_requests:
    desc: Number of read-write API requests per month
  lifecycle_transition_requests:
    desc: Number of lifecycle transition requests
  restore_standard_requests:
    desc: Number of standard restore requests
  restore_bulk_requests:
    desc: Number of bulk restore requests
  restore_expedited_requests:
    desc: Number of expedited restore requests
  data_standard_retrieval_gb:
    desc: Amount of data retrieved via standard retrieval in GB
  data_bulk_retrieval_gb:
    desc: Amount of data retrieved via bulk retrieval in GB
  data_expedited_retrieval_gb:
    desc: Amount of data retrieved via expedited retrieval in GB
intelligent_tiering_storage:
  storage_gb:
    desc: Amount of data stored in Intelligent-Tiering in GB
  avg_object_size_mb:
    desc: Average object size in MB
  frequent_access_percent:
    desc: Percentage of data in frequent access tier
  infrequent_access_percent:
    desc: Percentage of data in infrequent access tier
  archive_instant_access_percent:
    desc: Percentage of data in archive instant access tier
  archive_access_percent:
    desc: Percentage of data in archive access tier
  deep_archive_access_percent:
    desc: Percentage of data in deep archive access tier
  rw_requests:
    desc: Number of read-write API requests per month
  ro_requests:
    desc: Number of read-only API requests per month
  lifecycle_transition_requests:
    desc: Number of lifecycle transition requests
  select_data_returned_gb:
    desc: Amount of data returned by S3 Select in GB
  select_data_scanned_gb:
    desc: Amount of data scanned by S3 Select in GB
one_zone_ia_storage:
  storage_gb:
    desc: Amount of data stored in One Zone-IA in GB
  rw_requests:
    desc: Number of read-write API requests per month
  ro_requests:
    desc: Number of read-only API requests per month
  lifecycle_transition_requests:
    desc: Number of lifecycle transition requests
  retrieval_data_gb:
    desc: Amount of data retrieved in GB
  select_data_returned_gb:
    desc: Amount of data returned by S3 Select in GB
  select_data_scanned_gb:
    desc: Amount of data scanned by S3 Select in GB
express_one_zone_storage:
  storage_gb:
    desc: Amount of data stored in Express One Zone in GB
  rw_requests:
    desc: Number of read-write API requests per month
  rw_request_size_gb:
    desc: Total size of read-write requests in GB
  ro_requests:
    desc: Number of read-only API requests per month
  ro_request_size_gb:
    desc: Total size of read-only requests in GB

```

aws_efs_file_system

```

storage_gb:
  desc: Total storage capacity in GB
standard_storage_reads_gb:
  desc: GB read from standard storage per month (elastic throughput mode only)
standard_storage_writes_gb:
  desc: GB written to standard storage per month (elastic throughput mode only)
ia_storage_percent:
  desc: Percentage of total storage in Infrequent Access tier (0-100)
ia_tiering_gb:
  desc: GB moved to IA tier per month
ia_reads_gb:
  desc: GB read from IA tier per month
archive_storage_percent:
  desc: Percentage of total storage in Archive tier (Multi-AZ elastic only, 0-100)
archive_tiering_gb:
  desc: GB moved to Archive tier per month (Multi-AZ elastic only)
archive_reads_gb:
  desc: GB read from Archive tier per month (Multi-AZ elastic only)

```

Messaging Resources

aws_sns_topic

```

monthly_requests:
  desc: Number of API requests per month
monthly_storage:
  desc: Amount of data stored for message archive in GB

```

aws_sns_topic_subscription

```

monthly_notifications:
  desc: Number of notifications delivered per month

```

aws_sqs_queue

```

monthly_requests:
  desc: Number of API requests per month

```

Serverless Resources

aws_lambda_function

```

monthly_requests:
  desc: Number of function invocations per month
request_duration_ms:
  desc: Average duration of each invocation in milliseconds

```

aws_lambda_provisioned_concurrency_config

```

monthly_requests:
  desc: Number of function invocations per month
request_duration_ms:
  desc: Average duration of each invocation in milliseconds

```

Big Data Resources

aws_emrserverless_application

```

job_runtime_hour:
  desc: Number of hours the EMR Serverless application runs

```

aws_emrcontainers_job_template

```

job_runtime_hour:
  desc: Number of hours the EMR Containers job runs
job_vcpu:
  desc: Number of vCPUs allocated to the job
job_memory_gb:
  desc: Amount of memory allocated to the job in GB

```

aws_emr_cluster

```

core_node_utilization:
  desc: Percentage utilization of core nodes (0-100)
master_node_utilization:
  desc: Percentage utilization of master nodes (0-100)

```

aws_emr_instance_fleet

```

instance_utilization:
  desc: Percentage utilization of instances in the fleet (0-100)

```

aws_emr_instance_group

```

instance_utilization:
  desc: Percentage utilization of instances in the group (0-100)

```

aws_opensearch_domain

```

data_instances:
  term_type:
    values: "on_demand" or "reserved"
    desc: Pricing model for data instances
  purchase_option:
    values: ["all_upfront", "partial_upfront", "no_upfront"]
    desc: Payment option for reserved data instances
  lease_contract_length:
    values: ["1yr", "3yr"]
    desc: Duration of lease for reserved data instances
master_instances:
  term_type:
    values: "on_demand" or "reserved"
    desc: Pricing model for dedicated master instances
  purchase_option:
    values: ["all_upfront", "partial_upfront", "no_upfront"]
    desc: Payment option for reserved master instances
  lease_contract_length:
    values: ["1yr", "3yr"]
    desc: Duration of lease for reserved master instances
ultrawarm_instances:
  managed_storage_gb:
    desc: Amount of UltraWarm managed storage in GB
cold_storage:
  managed_storage_gb:
    desc: Amount of cold storage in GB

```

aws_opensearchserverless_collection

```

avg_index_ocu_count:
  desc: Average number of indexing OpenSearch Compute Units (OCUs)
avg_query_ocu_count:
  desc: Average number of search/query OpenSearch Compute Units (OCUs)
storage_gb_per_month:
  desc: Amount of data stored per month in GB

```

Event Processing Resources

aws_schemas_schema

```

ingestion_count:
  desc: Number of schema ingestion operations per month

```

aws_pipes_pipe

```

event_count:
  desc: Number of events processed through the pipe per month

```

aws_cloudwatch_event_bus

```

event_count:
  desc: Number of events processed through the event bus per month

```

aws_cloudwatch_event_archive

```

archive_processing:
  desc: Amount of data processed for archiving in GB
archive_storage:
  desc: Amount of archived data stored in GB

```

Monitoring Resources

aws_cloudwatch_metric_alarm

```

avg_metrics_retrieved:
  desc: Average number of metrics retrieved per alarm per month

```

Security Resources

aws_secretsmanager_secret

```

average_duration_in_days:
  desc: Average number of days the secret is stored per month (prorated billing)
monthly_requests:
  desc: Number of API requests per month

```

aws_kms_key

```

monthly_symmetric_requests:
  desc: Number of symmetric encryption/decryption requests per month
monthly_asymmetric_requests_except_rsa2048:
  desc: Number of asymmetric requests per month (excluding RSA 2048)
monthly_asymmetric_rsa2048_requests:
  desc: Number of RSA 2048 asymmetric requests per month
monthly_generatedatakeypair_ecc_requests:
  desc: Number of ECC key pair generation requests per month
monthly_generatedatakeypair_rsa_requests:
  desc: Number of RSA key pair generation requests per month

```

aws_kms_external_key

```

monthly_symmetric_requests:
  desc: Number of symmetric encryption/decryption requests per month
monthly_asymmetric_requests_except_rsa2048:
  desc: Number of asymmetric requests per month (excluding RSA 2048)
monthly_asymmetric_rsa2048_requests:
  desc: Number of RSA 2048 asymmetric requests per month
monthly_generatedatakeypair_ecc_requests:
  desc: Number of ECC key pair generation requests per month
monthly_generatedatakeypair_rsa_requests:
  desc: Number of RSA key pair generation requests per month

```

aws_kms_replica_key

```

monthly_symmetric_requests:
  desc: Number of symmetric encryption/decryption requests per month
monthly_asymmetric_requests_except_rsa2048:
  desc: Number of asymmetric requests per month (excluding RSA 2048)
monthly_asymmetric_rsa2048_requests:
  desc: Number of RSA 2048 asymmetric requests per month
monthly_generatedatakeypair_ecc_requests:
  desc: Number of ECC key pair generation requests per month
monthly_generatedatakeypair_rsa_requests:
  desc: Number of RSA key pair generation requests per month

```

aws_kms_replica_external_key

```

monthly_symmetric_requests:
  desc: Number of symmetric encryption/decryption requests per month
monthly_asymmetric_requests_except_rsa2048:
  desc: Number of asymmetric requests per month (excluding RSA 2048)
monthly_asymmetric_rsa2048_requests:
  desc: Number of RSA 2048 asymmetric requests per month
monthly_generatedatakeypair_ecc_requests:
  desc: Number of ECC key pair generation requests per month
monthly_generatedatakeypair_rsa_requests:
  desc: Number of RSA key pair generation requests per month

```

aws_wafv2_web_acl

```

monthly_requests:
  desc: Number of web requests evaluated per month
request_sizing_weights:
  16KB:
    desc: Weight for requests up to 16KB body size (0-1)
  32KB:
    desc: Weight for requests up to 32KB body size (0-1)
  48KB:
    desc: Weight for requests up to 48KB body size (0-1)
  64KB:
    desc: Weight for requests up to 64KB body size (0-1)
shield_protected:
  values: true or false
  desc: Whether AWS Shield Advanced protection is enabled

```

Networking Resources

aws_vpn_connection

```

data_processing_month_gb:
  desc: Amount of data processed through VPN connection in GB per month

```

aws_ec2_transit_gateway_vpc_attachment

```

data_processing_month_gb:
  desc: Amount of data processed through transit gateway in GB per month

```

aws_ec2_client_vpn_network_association

```

active_users:
  desc: Number of concurrent VPN users
hrs_active_per_month:
  desc: Number of hours the VPN connection is active per month

```

aws_vpc_endpoint (gateway)

```

gateway_endpoint:
  endpoint_az_count:
    desc: Number of availability zones for the endpoint
  processed_bytes_per_hour_gb:
    desc: Amount of data processed per hour in GB

```

Load Balancing Resources

aws_elb (Classic Load Balancer)

```

data_gb:
  desc: Total GB of data processed by the Classic Load Balancer per month

```

aws_lb (Application Load Balancer)

```

application:
  average_new_connections_per_second:
    desc: Average new connections per second
  average_connection_duration_seconds:
    desc: Average connection duration in seconds
  average_processed_bytes_per_hour_gb_ec2:
    desc: Average processed bytes per hour in GB for EC2 targets
  average_processed_bytes_per_hour_gb_lambda:
    desc: Average processed bytes per hour in GB for Lambda targets
  average_requests_per_second:
    desc: Average requests per second
  average_rules_processed:
    desc: Average number of rules processed per request
  on_outposts:
    values: true or false
    desc: Whether the ALB is deployed on AWS Outposts
  reserved_lcu_hours:
    desc: Reserved LCU capacity hours (billed in full)

```

aws_lb (Network Load Balancer)

```

network:
  average_new_tcp_connections_per_second:
    desc: Average new TCP connections per second
  average_tcp_connection_duration_sec:
    desc: Average TCP connection duration in seconds
  average_processed_bytes_tcp_per_hour_gb:
    desc: Average processed bytes for TCP per hour in GB
  average_new_udp_flows_per_second:
    desc: Average new UDP flows per second
  average_udp_flow_duration_sec:
    desc: Average UDP flow duration in seconds
  average_processed_bytes_udp_per_hour_gb:
    desc: Average processed bytes for UDP per hour in GB
  average_new_tls_connections_per_second:
    desc: Average new TLS connections per second
  average_tls_connection_duration_sec:
    desc: Average TLS connection duration in seconds
  average_processed_bytes_tls_per_hour_gb:
    desc: Average processed bytes for TLS per hour in GB
  reserved_nlcu_hours:
    desc: Reserved NLCU capacity hours (billed in full)

```

aws_lb (Gateway Load Balancer)

```

gateway:
  availability_zone_count:
    desc: Number of availability zones
  new_connections_per_second:
    desc: New connections per second
  average_connection_duration_seconds:
    desc: Average connection duration in seconds
  processed_bytes_per_hour_gb:
    desc: Processed bytes per hour in GB
  reserved_glcu_hours:
    desc: Reserved GLCU capacity hours (billed in full)

```

Container Resources

aws_ecs_service

```

external_instances:
  desc: Number of external instances
fargate_utilization:
  desc: Percentage utilization of Fargate tasks (0-100)
external_instances_utilization:
  desc: Percentage utilization of external instances (0-100)
managed_instances_utilization:
  desc: Percentage utilization of managed instances (0-100)

```

aws_ecs_capacity_provider

```

managed_instance_type:
  desc: Instance type for managed capacity provider (e.g. t3.medium)
managed_instance_count:
  desc: Number of managed instances
managed_scaling_instance_count:
  desc: Number of instances for managed scaling

```

AWS Glue Resources

aws_glue_job

```

job_runtime_min:
  desc: Duration of each job run in minutes
monthly_invocations:
  desc: Number of job invocations per month
default_max_capacity:
  desc: Default maximum DPU capacity for the job

```

aws_glue_crawler

```

no_of_dpus:
  desc: Number of DPUs allocated to the crawler
crawl_duration_min:
  desc: Duration of each crawl in minutes
monthly_invocations:
  desc: Number of crawl invocations per month

```

aws_glue_trigger

```

monthly_invocations:
  desc: Number of trigger invocations per month

```

aws_glue_catalog_database, aws_glue_catalog_table

```

catalog_object_count:
  desc: Number of objects stored in the Data Catalog
catalog_access_request_count:
  desc: Number of access requests to the Data Catalog per month
table_statistics_job:
  workers_count:
    desc: Number of DPU workers for table statistics jobs
  duration_min:
    desc: Duration of each statistics job in minutes
  monthly_invocations:
    desc: Number of statistics job invocations per month
table_optimization_job:
  workers_count:
    desc: Number of DPU workers for table optimization jobs
  duration_min:
    desc: Duration of each optimization job in minutes
  monthly_invocations:
    desc: Number of optimization job invocations per month

```

### Supported Azure Service Types

1. Linux Virtual Machine
1. Windows Virtual Machine
1. Virtual Machine (Legacy)
1. Linux Virtual Machine Scale Set
1. Windows Virtual Machine Scale Set
1. Virtual Machine Scale Set (Legacy)
1. Kubernetes Cluster
1. Managed Disk
1. Application Insights
1. Log Analytics Workspace
1. CosmosDB (SQL, Mongo, Cassandra, Gremlin, Table)
1. Firewall
1. PostgreSQL Flexible Server
1. MySQL Flexible Server
1. Function App (Linux and Windows)
1. Autoscale Setting

### Azure Usage Input details per service type

Compute Resources

azurerm_virtual_machine, azurerm_linux_virtual_machine, azurerm_windows_virtual_machine

```

storage_transactions:
  desc: Number of monthly storage transactions for the VM's OS disk

```

azurerm_monitor_autoscale_setting (for Virtual Machine Scale Sets)

```

utilization:
  desc: Expected utilization factor between 0 and 1 (e.g. 0.5 = 50% of max capacity)

```

azurerm_kubernetes_cluster

```

utilization:
  desc: Expected utilization factor between 0 and 1 for autoscaling node pools (e.g. 0.5 = 50% between min and max node count)

```

Storage Resources

azurerm_managed_disk

```

storage_transactions:
  desc: Number of monthly storage transactions (applies to Standard HDD and Standard SSD)

```

Database Resources

azurerm_cosmosdb_sql_container, azurerm_cosmosdb_mongo_collection, azurerm_cosmosdb_cassandra_table, azurerm_cosmosdb_gremlin_graph, azurerm_cosmosdb_table

```

storage_gb:
  desc: Amount of data stored in GB
throughput_serverless:
  desc: Throughput consumption for serverless mode (in RU/s units)

```

azurerm_postgresql_flexible_server

```

backup_storage_gb:
  desc: Amount of backup storage in GB beyond included amount
commitment_type:
  values: "reserved"
  desc: Commitment pricing type
commitment_length:
  values: "1_year" or "3_year"
  desc: Duration of the reserved commitment

```

azurerm_mysql_flexible_server

```

backup_storage_gb:
  desc: Amount of backup storage in GB beyond included amount
commitment_type:
  values: "reserved"
  desc: Commitment pricing type
commitment_length:
  values: "1_year" or "3_year"
  desc: Duration of the reserved commitment

```

Monitoring Resources

azurerm_log_analytics_workspace

```

analytics_logs_gb:
  desc: Monthly ingestion volume for Analytics Logs in GB
basic_logs_gb:
  desc: Monthly ingestion volume for Basic Logs in GB
auxiliary_logs_gb:
  desc: Monthly ingestion volume for Auxiliary Logs in GB
platform_logs_gb:
  desc: Monthly ingestion volume for Platform Logs in GB

```

azurerm_application_insights

```

analytics_logs_gb:
  desc: Monthly data ingestion volume for Analytics Logs in GB

```

Networking Resources

azurerm_firewall

```

data_processed_gb:
  desc: Amount of data processed per month in GB (for AZFW_Hub SKU only)

```

Serverless Resources

azurerm_linux_function_app, azurerm_windows_function_app

```

tier:
  values: "Flex Consumption"
  desc: Function app hosting tier
memory_mb:
  desc: Memory allocation in MB
monthly_active_executions:
  desc: Number of active executions per month
monthly_active_exec_seconds:
  desc: Total active execution seconds per month
execution_time_ms:
  desc: Average execution time in milliseconds
monthly_executions:
  desc: Total number of executions per month

```

azurerm_function_app_flex_consumption

```

monthly_active_executions:
  desc: Number of active executions per month
monthly_active_exec_seconds:
  desc: Total active execution seconds per month
always_ready_baseline_sec:
  desc: Always-ready baseline seconds per month
always_ready_exec_sec:
  desc: Always-ready execution seconds per month
always_ready_exec_count:
  desc: Always-ready execution count per month

```

---
