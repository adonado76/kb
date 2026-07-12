---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Connect Google Cloud"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Google Cloud"
source_path: "SSVCLNQ/admin/connect-google-cloud.html"
images:
  - "03-media/apptio-cloudability-standard/GCP1_Billing_Export.jpg"
  - "03-media/apptio-cloudability-standard/GCP2_Billing_Export.jpg"
  - "03-media/apptio-cloudability-standard/GCP3_Billing_Export.png"
  - "03-media/apptio-cloudability-standard/GCP4_Billing_Export.jpg"
  - "03-media/apptio-cloudability-standard/GCP5_Billing_Export.jpg"
  - "03-media/apptio-cloudability-standard/GCP6_Billing_Export.jpg"
  - "03-media/apptio-cloudability-standard/GCP7_Billing_Export.jpg"
  - "03-media/apptio-cloudability-standard/GCP8_Billing_Export.jpg"
  - "03-media/apptio-cloudability-standard/GCP9_Billing_Export.jpg"
  - "03-media/apptio-cloudability-standard/GCP10_Billing_Export.jpg"
  - "03-media/apptio-cloudability-standard/GCP11_Billing_Export.jpg"
  - "03-media/apptio-cloudability-standard/GCP12_Billing_Export.jpg"
  - "03-media/apptio-cloudability-standard/GCP13_Creds.png"
  - "03-media/apptio-cloudability-standard/regenerate_cloudability_more_options.jpg"
  - "03-media/apptio-cloudability-standard/setup_overview_guide_gcp-error-ok.jpg"
  - "03-media/apptio-cloudability-standard/GCP14_Script.jpg"
  - "03-media/apptio-cloudability-standard/GCP15_EditCredst.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connect Google Cloud

Overview

This guide walks you through the process of connecting your Google Cloud Platform to IBM Cloudability. Cloudability supports

- GCP Standard Billing

- GCP Detailed Billing.

Once connected, you’ll gain access to the FinOps capabilities within Cloudability.

Prerequisites

- Cloudability uses IAM to create and manage custom roles

- Should have IAM permissions in GCP for creating a custom role

- Cloudability uses these custom roles with permissions specific to reading billing, commitments and pricing data. CloudabilityRole_Billing – for billing account CloudabilityRole_Buckets - for GCS bucket access CloudabilityRole_AdvancedFeatures – for projects

- Should have permissions to create a GCS bucket within GCP .
- The following permissions are required: bigquery.tables.export (export table data out of BigQuery) storage.buckets.getIamPolicy storage.buckets.get storage.buckets.list storage.multipartUploads.abort storage.multipartUploads.create storage.multipartUploads.list storage.multipartUploads.listParts storage.objects.create storage.objects.delete storage.objects.get storage.objects.list storage.objects.update

- Should be able to execute the GCP shell script in GCP console which will bind the role to Cloudability 's service account ( billing-data-service-acct@cloudability-credentials.iam.gserviceaccount.com ) as a member with the custom role at the billing-project level

- To be able to successfully run our script from within your cloud console, your gcloud user needs to be granted the following IAM permissions at the project level: iam.roles.create resourcemanager.projects.setIamPolicy resourcemanager.projects.getIamPolicy

- This gives customers complete control over, and visibility into, all actions taken by any entity assuming that role within their GCP projects.

- Admin access to the Cloudability Vendor Credentials

- Familiarity with GCP Organizations

- Familiarity with GCP Credentialing using Bulk Actions

- Access and ability to enable the Google Cloud Resource Manager API

Getting Started:

Cloudability’s GCP Credentialing process requires two main steps:

- GCP Billing Account Credentialing

- GCP Projects Credentialing (for Advanced features)

The GCP Billing Account Credentialing process involves a few steps which will require you to take actions in both GCP portal and Cloudability at various phases.

During this process Cloudability will use your billing Table ID and generate a script that contains gcloud IAM commands which will be required to be run in the GCP console.

- Check the IAM section of the appropriate project to determine whether you have these permissions.
- Enable the Google Cloud Resource Manager API
- Cloudability uses Google's Cloud Resource Manager API to test whether the necessary permissions have been granted to support the available features.
- Google's Cloud Resource Manager API provides many advantages at zero cost to you. You can read more about it at Resource Manager .
- A list of APIs made available via the Resource Manager can be found at Cloud Resource Manager API .

Credentialing the GCP Billing account

Step 1 - GCP Portal – Enable BigQuery export and Table ID

- In the GCP Console, under APIs & Services > Library , search for 'Cloud Resource Manager API' .
- From the Cloud Resource Manager API page, select ENABLE .
- Make sure that API enabled is ticked.

Working in the Google Console, type Billing in the search bar and when the results show select Billing accounts.

Select Billing export.

Select Edit Settings (based on the Type of Export you are putting in place.

Select the type of export you want to put in place – Standard or Detailed Billing – by clicking Edit Settings.

Select your Project where your Billing Data (likely your billing project) will be held and then click in Data Set and select Create a New Data Set.

Add a Dataset ID and click Create Data Set.

Select Save to complete the process.

- GCP Standard usage cost table name should be in this format gcp_billing_export_v1_<BILLING_ACCOUNT_ID> .

- GCP Detailed usage cost table name should be in this format gcp_billing_export_resource_v1_<BILLING_ACCOUNT_ID> .

Standard usage / Detailed usage cost table should have the below partitioning detail as mentioned in the below image.

After you have enabled the BigQuery export, it will take a few hours for the billing table to be created, after which you will be able to locate the Table ID.

You can find the billing Table ID by navigating to the project that contains the BigQuery export of your billing data, under Table info > Table ID .

You must specify a project and dataset to which the billing data will be exported, when you enable the BigQuery export for a Billing Account . A table is automatically created for you within the specified dataset. This table is referred to as the billing table and Cloudability’s Service Account must be able to read data from this table.

Create a storage bucket

A Storage bucket is required to copy data from the BQ table export into, for Cloudability to then retrieve this data.

Working in the Google Console ; type Cloud Storage in the Search bar and select it when it shows.

Click Create to create a Bucket.

Enter a name for your storage bucket (eg: cloudability-export and click Create).

When prompted keep defaults and click Confirm.

Bucket will be created.

Step 2 - Cloudability – Add Credentials details in Cloudability

Standard Billing with GCS

Once you’ve gathered the information listed above, you can enter it into Cloudability to update your GCP credential.

Cloudability will use this information to generate a Shell script. When the script is run from your Cloud Shell in the GCP Portal, it will create and grant rights for Cloudability via the custom role in order to provide access to the storage account.

- In Cloudability , navigate to
- Settings > Vendor Credentials > Add Datasource > GCP .
- Click Next
- Select GCP - the Add GCP Account panel opens.

Or

- Settings > Vendor Credentials > Ingress > GCP .
- Click Next
- Select GCP Standard Billing - t he Add a Credential panel opens.
- Enter Complete table id which is combination of project, dataset, table e.g. project:dataset.gcp_billing_export_v1_<BILLING_ACCOUNT_ID>
- Enter the GCS bucket name
- Enter Organization id (Recommended, helps in quick onboarding) GCP customers can quickly credential the projects in an automated way by using GCP organization . You will need to move any projects you created under "No organization" into your new organization resource. For instructions on how to move your projects, see Migrating projects into an organizational resource .
- Click on generate setup script
- Click Download Script
- A GCP shell script template will be downloaded locally – save this in a secure place for your next step as this will need to be uploaded into the GCP console

Standard Billing with BQ Streaming

- Settings > Vendor Credentials > Add Datasource > GCP .
- Click Next
- Select GCP - the Add GCP Account panel opens.

Or

- Settings > Vendor Credentials > Ingress > GCP .
- Click Next
- Select GCP Standard Billing - t he Add a Credential panel opens.
- Enter Complete table id which is combination of project, dataset, table e.g. project:dataset.gcp_billing_export_v1_<BILLING_ACCOUNT_ID
- Bucket name (Optional - can be left blank)
- Organization id (Recommended, helps in quick onboarding) GCP customers can quickly credential the projects in an automated way by using GCP organization . You will need to move any projects you created under "No organization" into your new organization resource. For instructions on how to move your projects, see Migrating projects into an organizational resource .

- Click on generate setup script
- Click Download Script
- A GCP shell script template will be downloaded locally – save this in a secure place for your next step as this will need to be uploaded into the GCP console

Detailed Billing with GCS (Recommended)

- Settings > Vendor Credentials > Add Datasource > GCP .
- Click Next
- Select GCP - the Add GCP Account panel opens.

Or

- Settings > Vendor Credentials > Ingress > GCP .
- Click Next
- Select GCP Detailed Billing - t he Add a Credential panel opens.
- Enter Complete table id which is combination of project, dataset, table e.g. project:dataset.gcp_billing_export_resource_v1_<BILLING_ACCOUNT_ID
- Enter the GCS bucket name .
- Enter the Detailed Billing Date . Note: This date indicates the month and the year from when you have detailed billing exports enabled. If you are doing this for the first time it is the current month as YYYY-MM.

- Organization id (Recommended, helps in quick onboarding) GCP customers can quickly credential the projects in an automated way by using GCP organization . You will need to move any projects you created under "No organization" into your new organization resource. For instructions on how to move your projects, see Migrating projects into an organizational resource .
- Click on generate setup script
- Click Download Script
- A GCP shell script template will be downloaded locally – save this in a secure place for your next step as this will need to be uploaded into the GCP console

Step 3 – Upload and run the GCP shell script

The script performs two steps: it first sets up a custom role within the billing project and then adds Cloudability’s Service Account as a member of the project, binding the custom role. This ensures that our Service Account can read data only from BigQuery tables within a billing project. We do not access BigQuery data in non-billing projects.

In case of GCS bucket, we follow the above process, export the BigQuery data into GCS via BigQuery export job and pull that data into Cloudability.

1. Custom roles setup

The script first creates custom roles within the billing project. The script attaches the permissions necessary to read billing data to the custom roles

# Example: Create billing custom role for my-billing-project-123 # Billing project ID is my-billing-project-123 gcloud iam roles create CloudabilityRole_Billing \ --project \ my-billing-project-123 \ --title \ "Cloudability Billing Role" \ --description \ "Allows Cloudability access to billing account data" \ --permissions \ bigquery.jobs.create,bigquery.tables.getData \ --stage=GA

2. Add Service Account as Member and Bind Custom role

Once the custom role has been created, the script adds Cloudability 's Service Account as a member of the billing project and binds the custom role to it.

# Example: Add Cloudability's Service Account as member of my-billing- project-123 # Billing project ID is my-billing-project-123 gcloud projects add-iam-policy-binding my-billing-project-123 \ --member serviceAccount:billing-data-service-acct@cloudability- credentials.iam.gserviceaccount.com \ --role 'projects/my-billing-project- 123/roles/CloudabilityRole_Billing'

3. GCS Bucket

If you are opting for GCP standard billing with GCS bucket or GCP detailed billing, a GCP GCS bucket must be configured. Cloudability will export data to this GCS bucket temporarily from the configured GCP BigQuery table to ingest this data to Cloudability. Once the data ingestion is complete Cloudability will delete the data from the bucket.

Note: Same GCP Payer Account IDs cannot be used in both standard and detailed billing at the same instance.

Run the script

Follow the below steps to run the script via the Cloud Shell within your cloud console. It does not matter from where within the Cloud Shell you run the script.

- Activate the Cloud Shell, select the icon and select Upload file . Choose the downloaded script from the file explorer and confirm.
- chmod +x <scriptname> to make the script executable
- Next, run the script in your Cloud Shell:

./ script-name

- Check for any errors. For example,

- If the script is successful, you will see a similar output to the following in your Cloud Shell:

Step 4 – Cloudability Verify credentials

- Select Verify Credentials .
- Select the refresh icon to update the status.

The green check-mark indicates that this billing account has been successfully credentialed.

You have now successfully added your billing account to Cloudability. We ingest data at regular intervals and your billing data will be available starting from the next ingest cycle. Upon the next ingest, we will also enumerate the projects associated with this billing account.

Lastly, if your organization has additional GCP billing accounts that you would like to add, then please repeat this process for each of those billing accounts.

After completion of this process, within a few hours,

- Cloudability will start showing your Billing data and GCP labels within Cloudability.
- Retail Pricing data would also be pulled in, for enabling custom pricing please check Setting up Custom Pricing Support for GCP
- Cloudability will also display the projects.

As a next step you will need to credential the GCP projects.

GCP Projects Credentialing (Advanced features)

The purpose of this section is to help you walk through the process of credentialing your projects to enable Cloudability's Advanced Features. If your organization has multiple GCP projects, then this process must be repeated for each project for which you would like to enable Advanced Features.

Before you begin, make sure you’ve gone through the prerequisites

To credential your project:

- Add a new project credential, as described in Configure project-level credentials.
- Run the script, as described in Run the script .
- Familiarize yourself with GCP Credentialing using Bulk Actions

Add a new project credential

To enable Advanced Features for a GCP project:

- Navigate to Vendor Credentials , and select the GCP tab
- Select the Edit icon to open Edit a Credential panel.
- Select Update Credential.
- Select Download Script .
- If your browser prompts you with a warning, select Keep .

Run the script

For more information, see run the script section

How to confirm success

This can be done via bulk actions or manually.

- Bulk Verification via UI: GCP Credentialing using Bulk Actions

- Manual Verification via UI:

- Select Verify Credentials on each project .

- Select Details to verify that the project has the necessary permissions for Advanced Features. s

Frequently Asked Questions

The details provided on the Billing Export page differ from those on the BigQuery page for your Billing table.

Specifically, the Table ID on the BigQuery page is constructed using the Billing Project ID, while the Billing Export page lists the Billing Project Name. IDs are unique, while names are not.

Solution: Review prerequisites.

What to do if Project ID, Dataset, or Table ID is getting truncated?

Context: You enter your complete GCP Billing Table ID into and notice that there are errors. Additionally, when you edit the credential, you notice that the Project ID, Dataset, or Table ID are truncated. You might have retrieved or constructed your GCP Billing Table ID from the Billing Export page.

Solution: You must copy the complete Table ID from the BigQuery page for your Billing table.

How should I download updated template with latest permissions if there has been update of permissions?

Updated Template can be downloaded by editing the existing billing account and downloading the latest template for it. Once downloaded follow the credentialing steps mentioned after download of template.

[Script] Error: (gcloud.iam.roles.create) A resource in the project is a subject of conflict.

Context: This can occur when you have an existing role within your billing project with role_id CloudabilityRole_Billing. The error indicates that the script is unable to create a new role with role_id CloudabilityRole_Billing because one already exists.

Solution: Ignore this error.

[Script] Error: (gcloud.iam.roles.create) FAILED_PRECONDITION: You can't create a role with role_id (CloudabilityRole_Billing) where there is an existing role with that role_id in a deleted state.

Context: This can occur when you run the script after deleting an existing role from your billing project with role_id CloudabilityRole_Billing. The role could be in a deleted state and the script can't create a new role with that role_id. You can view the role's status (Enabled, Disabled, Deleted) in your cloud console.

Solution: Undelete the existing role with role_id CloudabilityRole_Billing from your billing project and re-run the script.

How to handle GCP Domain Restrictions?

If you have domain restrictions, then you might observe error messages. To overcome this, whitelist Cloudability to query the data by adding Cloudability 's GCP workspace customer id in their Organisation policy.

The domain is cloudability.com and the ID is C03n3dgoi

To view the complete SCUD enhancements in the Cloudability reporting UI for a GCP Payer account, which billing export should be used for credential setup?

The GCP Detailed Billing export is recommended, as it provides full visibility into over‑utilized and under‑utilized scenarios within Cloudability reporting.

How to migrate from GCP Standard Billing to GCP Detailed Billing?

- Set Up detailed billing in GCP Console
- If you have custom pricing , Configure the pricing export as well
- Credential the same account via detailed billing in Cloudability
- Verify the GCP account
- Once the projects are displayed , Enable advance features.

VPC Service Controls

Getting Recommendations Based on GPU Data

Prerequisites:

1. Each VM must have GPUs attached .

1. Each VM must have a GPU driver installed .

1. Each VM must have Python 3.6 or newer installed.

1. Each VM must have the packages required for creation of Python virtual environments installed.

- GCP Credentialing using Bulk Actions
- Permissions Reference - GCP
- Set up GCP Monitoring Agent for rightsizing
- Support for GCP Tags
- Setting up Custom Pricing Support for GCP
- Setting up Commitment Portfolio for GCP
