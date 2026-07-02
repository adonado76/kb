---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Setup IBM Cloud Credentials using Cloudability Method"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connect IBM Cloud"
source_path: "product/setup_ibm_cloud_credentials_using_cldy_method.html"
images:
  - "images/ibm1.jpg"
  - "images/ibm10.jpg"
  - "images/ibm11.jpg"
  - "images/ibm12.jpg"
  - "images/ibm13.jpg"
  - "images/ibm14.jpg"
  - "images/ibm15.jpg"
  - "images/ibm16.jpg"
  - "images/ibm17.jpg"
  - "images/ibm18.jpg"
  - "images/ibm19.jpg"
  - "images/ibm2.jpg"
  - "images/ibm20.jpg"
  - "images/ibm21.jpg"
  - "images/ibm22.jpg"
  - "images/ibm23.jpg"
  - "images/ibm24.jpg"
  - "images/ibm25.jpg"
  - "images/ibm26.jpg"
  - "images/ibm3.jpg"
  - "images/ibm4.jpg"
  - "images/ibm5.jpg"
  - "images/ibm6.jpg"
  - "images/ibm7.jpg"
  - "images/ibm8.jpg"
  - "images/ibm9.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Setup IBM Cloud Credentials using Cloudability Method

## Summary

Connect or credential your IBM Cloud accounts to Cloudability
to enable the ingestion of cost and usage data. This document focuses on the Cloudability method and provides a step-by-step guide for setting up
an IBM Cloud workspace using Terraform. The workspace will be used to deploy infrastructure using
Terraform configurations hosted on a GitHub repository.

## Prerequisite

Enabling your IBM account to export usage data

Before you can enable your IBM account to export usage data, you need to have administrator or
editor role on the Billing account management service. For more information, see  [IAM access](https://cloud.ibm.com/docs/account?topic=account-userroles "(Opens in a new tab or window)").

To enable your account to export usage data, use the following steps:

1. From the IBM Cloud console, go to  Manage  >  Billing and
   usage , and select  Settings .
2. Click  Connect .
3. Select a  Cloud Object Storage  instance and  Bucket  . By selecting these, you
   are choosing which bucket will store your usage reports.
   - Optional: If you don't want to select an existing instance, click  Select an instance
      >  Create new .
   - Optional: Select a bucket or create a new bucket by clicking  Create new bucket
      from the dropdown. For more information, see  [Getting started with IBM Cloud Object Storage](https://cloud.ibm.com/docs/cloud-object-storage?topic=cloud-object-storage-getting-started-cloud-object-storage "(Opens in a new tab or window)") .
4. For service to service authorizations, click  Authorize  . For the
   required access, select  Object Writer  and  Content Reader
    . Click  Review  and then  Assign .
5. Click  Connect  after you review your folder details.

Reference:  [Exporting your usage data for continual insights](https://cloud.ibm.com/docs/billing-usage?topic=billing-usage-exporting-your-usage&interface=ui "(Opens in a new tab or window)")

Copy Account Details for account where Enterprise is configured

Copy Enterprise ID:

1. Navigate to  Manage  .
2. Select  Enterprise  from the dropdown.

   ![ibm enterprise screenshot](../../../../03-media/cloudability-premium/images/ibm1.jpg)
3. Access  Dashboard  and locate the  ID  field.

   ![ibm enterprise dashboard screenshot](../../../../03-media/cloudability-premium/images/ibm2.jpg)

Copy Account ID

1. Navigate to  Manage  .
2. Click  Enterprise  from the dropdown and then select  Accounts
   .
3. Identify the account labeled as 'This account is the enterprise account' and copy its ID.

   ![ibm enterprise cpoy account id screenshot](../../../../03-media/cloudability-premium/images/ibm3.jpg)

Copy Account Details for Account where Enterprise is not configured

Copy Account ID:

1. Navigate to  Manage  .
2. Click  Account  from the dropdown and then select  Account
   Settings .
3. Copy its ID.

   ![ibm enterprise account settings screenshot](../../../../03-media/cloudability-premium/images/ibm4.jpg)

   ![ibm enterprise account settings 2 screenshot](../../../../03-media/cloudability-premium/images/ibm5.jpg)

Copy Storage Instance Name 

1. Access the IBM Cloud navigation menu.
2. Go to  Resource List  and select  Storage .
3. Choose the  Cloud Object Storage  instance that contains the Bucket where
   the Usage Report is exported.

   ![ibm enterprise copy storage screenshot](../../../../03-media/cloudability-premium/images/ibm6.jpg)

   ![ibm enterprise copy storage 2 screenshot](../../../../03-media/cloudability-premium/images/ibm7.jpg)

Copy Bucket Name and Bucket Region 

1. Access the IBM Cloud Navigation Menu.
2. Go to  Resource List  , select  Storage  and then choose  Storage Instance 
   .
3. Find the  Buckets  section and select the Bucket where the Usage Report is exported.
4. Navigate to  Configuration  and copy the Bucket Name and Location
   (Region).

   ![ibm enterprise copy bucket name screenshot](../../../../03-media/cloudability-premium/images/ibm8.jpg)

Copy Cost Prefix 

1. Access the IBM Cloud Navigation Menu.
2. Go to  Resource List  , select  Storage  and then choose  Storage Instance 
   .
3. Find the  Buckets  section and select the Bucket where the Usage Report is exported.
4. Access the IBM Cloud Navigation menu and select the Bucket where the Usage Report is exported.

Copy the prefix located between the Bucket Name and the folder name (containing year and month;
e.g., 2023-10), excluding both the Bucket Name and the Year-Month folder name.

![ibm enterprise copy cost prefix screenshot](../../../../03-media/cloudability-premium/images/ibm9.jpg)

Copy Cost Report Name 

1. Access the IBM Cloud Navigation Menu.
2. Go to  Resource List  , select  Storage  and then choose  Storage Instance 
   .
3. Find the  Buckets  section and select the Bucket where the Usage Report is exported.
4. Access the IBM Cloud Navigation menu and select the Bucket where the Usage Report is exported.
5. Navigate to any Year-Month folder and copy the file name named 'manifest' (the default file name
   is manifest).

   ![ibm enterprise copy cost report screenshot](../../../../03-media/cloudability-premium/images/ibm10.jpg)

   Note:

   Do not copy the file name extension. It should be just ‘manifest’ and not manifest.json.

## Generate Terraform Template from Cloudability

1. Ensure all details are copied and readily accessible.
2. Login to Cloudability UI and navigate to Settings: Vendor Credentials: Click ‘Add Datasource’
   and select 'IBM'.

   ![ibm enterprise terraform template screenshot](../../../../03-media/cloudability-premium/images/ibm11.jpg)
3. Under  Add IBM Account  side panel, click  Next  .
4. Enter all the details copied earlier and click  Generate Template  .

   Note:

   Cost Report Name should not have the filename extension (.json).

   ![ibm enterprise add ibm account  screenshot](../../../../03-media/cloudability-premium/images/ibm12.jpg)

## Executing the Terraform

Prerequisites for Terraform 

1. Ensure that Terraform has been downloaded and is hosted on a repository such as GitHub.

   Note: If
   your GitHub repository is private, you will need to generate a Personal Access Token (PAT) as
   described here.
2. Also, make sure that you have Account Owner or Manager Service access and Administrator Platform
   access for Schematics Service in your IAM Access.

Note: The downloaded Terraform can also be executed using the local CLI

Steps for Execution

**Step 1: Login to IBM Cloud**

1. Navigate to the IBM Cloud login page.
2. Enter your IBM Cloud credentials and log in to your IBM Cloud account.

**Step 2: Access Schematics and Create a Workspace**

1. After logging in, access the Navigation menu within IBM Cloud.
2. From the Navigation menu, select  Schematics  .
3. Click  Workspaces  to access the workspace management interface.

   ![ibm enterprise access schematics screenshot](../../../../03-media/cloudability-premium/images/ibm13.jpg)

**Step 3: Configure the Workspace**

1. Click  Create Workspace  to initiate the workspace creation process.

   ![ibm enterprise create workspace  screenshot](../../../../03-media/cloudability-premium/images/ibm14.jpg)
2. Provide the GitHub repository URL where your Terraform configuration files are hosted.
3. If your GitHub repository is private, provide the Personal Access Token (PAT) that you generated
   during the prerequisites.

   Reference:  [Managing your personal access tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token "(Opens in a new tab or window)")
4. Select the latest Terraform Version, in this case,  terraform\_v1.5  .

   Note:

   Terraform version should be v1.5 and above.
5. Click  Next  to proceed.

   ![ibm enterprise schematics screenshot](../../../../03-media/cloudability-premium/images/ibm15.jpg)

**Step 4: Define Variables**

1. Provide a name for your workspace, e.g., 'CldyWorkspace'.
2. Under  Tags  , add a tag named "createdFor" with the value 'Cldy'.
3. Leave the Resource Group as 'Default'.
4. Choose a location for your workspace, as it determines where workspace actions will be executed.
5. Description is optional.
6. Click  Next  to continue.

   ![ibm enterprise define variables  screenshot](../../../../03-media/cloudability-premium/images/ibm16.jpg)

**Step 5: Apply the Terraform Plan**

1. Click  Create  to confirm and create the workspace.
2. Your CldyWorkspace will be created.

   ![ibm enterprise apply terraform plan screenshot](../../../../03-media/cloudability-premium/images/ibm17.jpg)

**Step 6: Access Created Resources**

1. Select 'CldyWorkspace' from the list of workspaces.
2. Navigate to  Settings  for 'CldyWorkspace'.
3. From the  Variables  section, expand three dots (ellipsis), and select
    Edit  .

   ![ibm enterprise access created resources screenshot](../../../../03-media/cloudability-premium/images/ibm18.jpg)
4. Your CldyWorkspace will be created. Provide your ibmcloud\_api\_key, which must
   have the necessary access to create IAM resources.

   Reference:  [Managing user API Keys](https://cloud.ibm.com/docs/account?topic=account-userapikey&interface=ui#create_user_key "(Opens in a new tab or window)")
5. Select  Sensitive  checkbox if you want to treat this variable value as
   sensitive or secret information. This prevents it from being exposed in workspace details, CLI
   output, or log output.

   ![ibm enterprise secret information screenshot](../../../../03-media/cloudability-premium/images/ibm19.jpg)
6. After configuring the variables, return to 'CldyWorkspace' and go to the  Jobs
    section.
7. Click  Apply plan  to initiate the deployment of Terraform configuration.

   ![ibm enterprise apply plan screenshot](../../../../03-media/cloudability-premium/images/ibm20.jpg)

   ![ibm enterprise log details  screenshot](../../../../03-media/cloudability-premium/images/ibm21.jpg)
8. Once  Apply plan  is successful, you can access the resources that were
   created in the  Manage  section.

   ![ibm enterprise access IAM screenshot](../../../../03-media/cloudability-premium/images/ibm22.jpg)
9. Custom Roles  can be found under  Access (IAM) 
   >  Roles  .

   ![ibm enterprise custom roles screenshot](../../../../03-media/cloudability-premium/images/ibm23.jpg)
10. This concludes you have successfully deployed resources and can manage access and roles as
    needed  .

**Step 7: Verify Credentials in Cloudability**

1. Once terraform plan is applied successfully, come back to the Cloudability UI and click
    Verify Credentials  . The green check mark indicates that the credentialing
   process has been successful. 

   ![ibm enterprise verify credentials screenshot](../../../../03-media/cloudability-premium/images/ibm24.jpg)

   **Verify Credentials**
   **via Bulk Actions**

   In order to Verify multiple accounts quickly, click on Bulk Actions
   button. This screen displays all the accounts except the ones with Credentials Needed status
   (X).

   1. Select the accounts which are needed to be verified.
   2. Click on **Review Selection**
   3. Click on **Verify.**

   This would trigger the bulk verify process and the bulk actions button would be disabled
   until the process completes.

   Once completed, the accounts will move to either a Verified
   Credentialed status or Invalid Credential status (because of errors).

   Note: In case the number of
   accounts is huge this might take a few minutes.

   Sample Terraform Script

   (Expandable Header)

   ![ibm enterprisesample terraform  screenshot](../../../../03-media/cloudability-premium/images/ibm25.jpg)

   ![ibm enterprise sample terraform continued screenshot](../../../../03-media/cloudability-premium/images/ibm26.jpg)

**Parent topic:** [Connect IBM Cloud](../product/apptio_help_center_ibm_cloud.html)
