---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Troubleshooting"
breadcrumb:
  - "Cloudability Premium"
  - "Governance"
source_path: "admin/governance-troubleshooting.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Troubleshooting

Before troubleshooting, ensure the following are completed:

- You have the correct Cloudability role and permissions assigned.
- The IBM Cloudability GitHub App is installed in your GitHub org.
- **HCP / TFE Customers:** Run Task has been configured.
- **Terraform Community Customers:**

  - Your GitHub Actions workflows are set up to invoke Cloudability Governance actions and the
    Required GitHub secrets are configured.
  - Terraform plan output is available in the PR workflow

## Troubleshooting Details

| Problem | Possible Cause | Resolution |
| --- | --- | --- |
| **“Access Denied” is displayed in Cloudability UI**  **Missing Governance Features – example: inability to create policies** | Incorrect role/permissions assignment in Cloudability | Ensure your user has the appropriate permissions listed in [Overview of permissions](governance-getting-started.html#governance-getting-started__overview) |
| **Cannot Install GitHub App** | - Lack of admin permissions in GitHub.  - Attempting to install from the wrong location. | - Ensure you are a **GitHub Org Admin** or have **admin access to the target repositories**.  - Use the **“Install GitHub App”** link from the **Governance Settings tab** in Cloudability. |
| **GitHub App Installed but Not Working** | - App not granted access to required repositories. - Missing permissions during installation. | Reinstall the app and ensure:   - It has read-only access to metadata and pull requests. - It has read/write access to checks. - It is installed for **all or selected repositories** containing Terraform code. |
| **A PR change is blocked due to a failed gated policy in Cloudability and is not getting approved** |  | 1. Please request a review and approval from a user with either the **GovernanceFeaturePRApproval**permission or the **Cloudability Governance PR Approver** role. 2. If the approver is temporarily unavailable and the PR needs to be unblocked urgently, you have    two options:    - Ask a GitHub Admin to temporarily remove the branch protection rule that requires Governance      check runs to pass before merging.    - Ask a user with **GovernanceFeaturePolicyFullAccess** permission or the **Cloudability      Governance Policy Admin** role to temporarily update the policy scope so that it does not apply to      the project associated with this specific PR |
| **GitHub Action Fails to Run (for Terraform Community users)** | - Missing secrets or incorrect environment variables.  - Terraform plan not generated. | Verify the following GitHub secrets are set:  - FD\_URL (e.g., [https://frontdoor.apptio.com](https://frontdoor.apptio.com/ "(Opens in a new tab or window)")) - FD\_KEY and FD\_SECRET (from a user with “Cloudability Governance Automation User” role) - FD\_ENV\_ID - CLOUDABILITY\_HOST (e.g., https://api.cloudability.com)   Ensure your workflow includes:   - Terraform plan generation - Metadata retrieval steps - Frontdoor token fetch step   Note: Note: Cloudability Governance expects only one top level terraform plan json for each invocation. |
| **A PR change that failed a gated Cloudability policy has been approved but the change can’t be applied in HCP** | The HCP Run task has its own enforcement level that can be set as advisory or mandatory. If its enforcement is set as Mandatory, and a gated policy failed, the change can’t be applied, regardless of the approval. | Update the Run Task enforcement level to “Advisory” and trigger another run to allow the change to be applied. |
| **Repositories don't show up after installing GitHub App** | The issue happens because the installation is split into two stages via GitHub's approval workflow. When an admin approves the pending installation later, the original session context is lost. As a result, Cloudability is never notified that the installation completed. | 1. Delete the current, incomplete installation. 2. Re-install the App using a GitHub account that holds immediate installation permissions to    complete the process in a single step. |
