---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "GitHub.com (Cloud) App Installation"
breadcrumb:
  - "Governance"
  - "Setup Cloudability Governance"
  - "GitHub.com (Cloud) App Installation"
source_path: "SSVCLNQ/admin/governance-github-app-installation.html"
images:
  - "03-media/apptio-cloudability-standard/Gov3.png"
  - "03-media/apptio-cloudability-standard/Gov4.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# GitHub.com (Cloud) App Installation

A GitHub app is used to set/update check run status in the pull request. Customers need to install IBM Cloudability GitHub app in their GitHub organizations by accessing the installation link from Governance configuration page. To install the app, the user who performs these operations needs to have admin permissions for the GitHub org or for the repositories in the org.

Below is the first landing page for Governance. The first action that needs to be taken is to install IBM Cloudability GitHub App in customer’s GitHub org.

![image](../images/Gov3.png)

1. Click on “Install GitHub App” link (present in front and center of Settings tab if setting up for the first time) to access the installation link from the Governance page.
1. You will be redirected to GitHub · Build and ship software on a single, collaborative platform for the installation.
1. Choose the GitHub organization and then you can install the app for all repositories or only selected repositories in that GitHub organization. Once the GitHub org is selected, an option will be given to: install the app to access all repositories in the GitHub org only selected repositories in the GitHub org
1. When installing the app, the following permissions are required: Read-only access to metadata (To be able to identify pull requests metadata) Read/write access to pull requests (Write access to pull requests is needed to be able to post comments to the pull requests) Read and write access to checks (Need to set and update check run state results)

Once access is granted, the page redirects back to the Cloudability Governance page.
