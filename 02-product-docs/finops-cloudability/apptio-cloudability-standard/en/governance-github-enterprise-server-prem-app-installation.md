---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "GitHub Enterprise Server (on-prem) App Installation"
breadcrumb:
  - "Governance"
  - "Setup Cloudability Governance"
  - "GitHub Enterprise Server (on-prem) App Installation"
source_path: "SSVCLNQ/admin/governance-github-enterprise-installation.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# GitHub Enterprise Server (on-prem) App Installation

This guide explains how to register a GitHub App within Cloudability for use with GitHub Enterprise Server (GHES). This process allows you to connect and manage your GHES repositories within the Cloudability Governance workflow.

## Prerequisites

- Access to a Cloudability instance with Governance permissions.
- Administrative access to your GitHub Enterprise Server instance.

## Step-by-Step Instructions

1. Navigate to Configuration In the Cloudability sidebar, go to Governance > Configuration . Select the Integrations tab and choose GitHub Enterprise from the left-hand menu.
1. Initiate Registration Click the Register GitHub App button located at the top right of the GitHub Enterprise section.
1. Enter App Details A "Register a New GitHub App" modal will appear. Provide the following information: Account Type: Select either Personal Account or Organization Account . When selecting Organization Account , user will also have to enter the unique identifier for their GitHub organization. App Name: Enter a unique name for your application. HTML URL: Provide the base URL of your GitHub Enterprise Server. API URL: Enter the API endpoint for your server (typically https://[your-ghes-domain]/api/v3 ). Click Submit to continue.
1. Authenticate with GitHub Enterprise The system will redirect you to your GitHub Enterprise Server. If prompted, sign in using your enterprise credentials or identity provider (SSO). Once authenticated, you will see a GitHub confirmation page. Click Create GitHub App for [Your Name/Org] .
1. Finalize the Integration After clicking create, you will be automatically redirected back to the Cloudability interface. A success message ("Successfully created GitHub Enterprise app") will appear briefly.
1. Verify Registration The new application will now be listed under the GitHub Enterprise App column. You can proceed to click Install next to the app name to select specific repositories for integration.

## Troubleshooting

- Redirect Issues: If your browser does not automatically redirect you during the authentication steps, look for the "click here" links provided on the transition screens.
- API URL Errors: Ensure the API URL includes the /api/v3 suffix, as this is required for Cloudability to communicate with GitHub Enterprise Server.
