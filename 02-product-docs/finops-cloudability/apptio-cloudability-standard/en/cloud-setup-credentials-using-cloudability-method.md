---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Setup IBM Cloud Credentials using Cloudability Method"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect IBM Cloud"
  - "Setup IBM Cloud Credentials using Cloudability Method"
source_path: "SSVCLNQ/product/setup_ibm_cloud_credentials_using_cldy_method.html"
images:
  - "03-media/apptio-cloudability-standard/ibm1.jpg"
  - "03-media/apptio-cloudability-standard/ibm2.jpg"
  - "03-media/apptio-cloudability-standard/ibm3.jpg"
  - "03-media/apptio-cloudability-standard/ibm4.jpg"
  - "03-media/apptio-cloudability-standard/ibm5.jpg"
  - "03-media/apptio-cloudability-standard/ibm6.jpg"
  - "03-media/apptio-cloudability-standard/ibm7.jpg"
  - "03-media/apptio-cloudability-standard/ibm8.jpg"
  - "03-media/apptio-cloudability-standard/ibm9.jpg"
  - "03-media/apptio-cloudability-standard/ibm10.jpg"
  - "03-media/apptio-cloudability-standard/ibm11.jpg"
  - "03-media/apptio-cloudability-standard/ibm12.jpg"
  - "03-media/apptio-cloudability-standard/ibm13.jpg"
  - "03-media/apptio-cloudability-standard/ibm14.jpg"
  - "03-media/apptio-cloudability-standard/ibm15.jpg"
  - "03-media/apptio-cloudability-standard/ibm16.jpg"
  - "03-media/apptio-cloudability-standard/ibm17.jpg"
  - "03-media/apptio-cloudability-standard/ibm18.jpg"
  - "03-media/apptio-cloudability-standard/ibm19.jpg"
  - "03-media/apptio-cloudability-standard/ibm20.jpg"
  - "03-media/apptio-cloudability-standard/ibm21.jpg"
  - "03-media/apptio-cloudability-standard/ibm22.jpg"
  - "03-media/apptio-cloudability-standard/ibm23.jpg"
  - "03-media/apptio-cloudability-standard/ibm24.jpg"
  - "03-media/apptio-cloudability-standard/ibm25.jpg"
  - "03-media/apptio-cloudability-standard/ibm26.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Setup IBM Cloud Credentials using Cloudability Method

## Summary

Connect or credential your IBM Cloud accounts to Cloudability to enable the ingestion of cost and usage data. This document focuses on the Cloudability method and provides a step-by-step guide for setting up an IBM Cloud workspace using Terraform. The workspace will be used to deploy infrastructure using Terraform configurations hosted on a GitHub repository.

## Prerequisite

Enabling your IBM account to export usage data

Before you can enable your IBM account to export usage data, you need to have administrator or editor role on the Billing account management service. For more information, see IAM access .

1. From the IBM Cloud console, go to Manage > Billing and usage , and select Settings .
1. Click Connect .
1. Select a Cloud Object Storage instance and Bucket . By selecting these, you are choosing which bucket will store your usage reports. Optional: If you don't want to select an existing instance, click Select an instance > Create new . Optional: Select a bucket or create a new bucket by clicking Create new bucket from the dropdown. For more information, see Getting started with IBM Cloud Object Storage .
1. For service to service authorizations, click Authorize . For the required access, select Object Writer and Content Reader . Click Review and then Assign .
1. Click Connect after you review your folder details.

Reference: Exporting your usage data for continual insights

Copy Account Details for account where Enterprise is configured

1. Navigate to Manage .
1. Select Enterprise from the dropdown.
1. Access Dashboard and locate the ID field.

1. Navigate to Manage .
1. Click Enterprise from the dropdown and then select Accounts .
1. Identify the account labeled as 'This account is the enterprise account' and copy its ID.

Copy Account Details for Account where Enterprise is not configured

1. Navigate to Manage .
1. Click Account from the dropdown and then select Account Settings .
1. Copy its ID.

1. Access the IBM Cloud navigation menu.
1. Go to Resource List and select Storage .
1. Choose the Cloud Object Storage instance that contains the Bucket where the Usage Report is exported.

1. Access the IBM Cloud Navigation Menu.
1. Go to Resource List , select Storage and then choose Storage Instance .
1. Find the Buckets section and select the Bucket where the Usage Report is exported.
1. Navigate to Configuration and copy the Bucket Name and Location (Region).

1. Access the IBM Cloud Navigation Menu.
1. Go to Resource List , select Storage and then choose Storage Instance .
1. Find the Buckets section and select the Bucket where the Usage Report is exported.
1. Access the IBM Cloud Navigation menu and select the Bucket where the Usage Report is exported.

Copy the prefix located between the Bucket Name and the folder name (containing year and month; e.g., 2023-10), excluding both the Bucket Name and the Year-Month folder name.

1. Access the IBM Cloud Navigation Menu.
1. Go to Resource List , select Storage and then choose Storage Instance .
1. Find the Buckets section and select the Bucket where the Usage Report is exported.
1. Access the IBM Cloud Navigation menu and select the Bucket where the Usage Report is exported.
1. Navigate to any Year-Month folder and copy the file name named 'manifest' (the default file name is manifest). Note: Do not copy the file name extension. It should be just ‘manifest’ and not manifest.json.

## Generate Terraform Template from Cloudability

1. Ensure all details are copied and readily accessible.
1. Login to Cloudability UI and navigate to Settings: Vendor Credentials: Click ‘Add Datasource’ and select 'IBM'.
1. Under Add IBM Account side panel, click Next .
1. Enter all the details copied earlier and click Generate Template . Note: Cost Report Name should not have the filename extension (.json).

## Executing the Terraform

1. Ensure that Terraform has been downloaded and is hosted on a repository such as GitHub. Note: If your GitHub repository is private, you will need to generate a Personal Access Token (PAT) as described here.
1. Also, make sure that you have Account Owner or Manager Service access and Administrator Platform access for Schematics Service in your IAM Access.

Steps for Execution

Step 1: Login to IBM Cloud

1. Navigate to the IBM Cloud login page.
1. Enter your IBM Cloud credentials and log in to your IBM Cloud account.

Step 2: Access Schematics and Create a Workspace

1. After logging in, access the Navigation menu within IBM Cloud.
1. From the Navigation menu, select Schematics .
1. Click Workspaces to access the workspace management interface.

Step 3: Configure the Workspace

1. Click Create Workspace to initiate the workspace creation process.
1. Provide the GitHub repository URL where your Terraform configuration files are hosted.
1. If your GitHub repository is private, provide the Personal Access Token (PAT) that you generated during the prerequisites. Reference: Managing your personal access tokens
1. Select the latest Terraform Version, in this case, terraform_v1.5 . Note: Terraform version should be v1.5 and above.
1. Click Next to proceed.

Step 4: Define Variables

1. Provide a name for your workspace, e.g., 'CldyWorkspace'.
1. Under Tags , add a tag named "createdFor" with the value 'Cldy'.
1. Leave the Resource Group as 'Default'.
1. Choose a location for your workspace, as it determines where workspace actions will be executed.
1. Description is optional.
1. Click Next to continue.

Step 5: Apply the Terraform Plan

1. Click Create to confirm and create the workspace.
1. Your CldyWorkspace will be created.

Step 6: Access Created Resources

1. Select 'CldyWorkspace' from the list of workspaces.
1. Navigate to Settings for 'CldyWorkspace'.
1. From the Variables section, expand three dots (ellipsis), and select Edit .
1. Your CldyWorkspace will be created. Provide your ibmcloud_api_key, which must have the necessary access to create IAM resources. Reference: Managing user API Keys
1. Select Sensitive checkbox if you want to treat this variable value as sensitive or secret information. This prevents it from being exposed in workspace details, CLI output, or log output.
1. After configuring the variables, return to 'CldyWorkspace' and go to the Jobs section.
1. Click Apply plan to initiate the deployment of Terraform configuration.
1. Once Apply plan is successful, you can access the resources that were created in the Manage section.
1. Custom Roles can be found under Access (IAM) > Roles .
1. This concludes you have successfully deployed resources and can manage access and roles as needed .

Step 7: Verify Credentials in Cloudability

1. Once terraform plan is applied successfully, come back to the Cloudability UI and click Verify Credentials . The green check mark indicates that the credentialing process has been successful. Verify Credentials via Bulk Actions In order to Verify multiple accounts quickly, click on Bulk Actions button. This screen displays all the accounts except the ones with Credentials Needed status (X). Select the accounts which are needed to be verified. Click on Review Selection Click on Verify. This would trigger the bulk verify process and the bulk actions button would be disabled until the process completes. Once completed, the accounts will move to either a Verified Credentialed status or Invalid Credential status (because of errors). Note: In case the number of accounts is huge this might take a few minutes. Sample Terraform Script (Expandable Header)
