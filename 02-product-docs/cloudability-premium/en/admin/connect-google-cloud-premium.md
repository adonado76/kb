---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Connect Google Cloud"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
source_path: "admin/connect-google-cloud-premium.html"
images:
  - "images/GCP10_Billing_Export.jpg"
  - "images/GCP11_Billing_Export.jpg"
  - "images/GCP12_Billing_Export.jpg"
  - "images/GCP13_Creds.png"
  - "images/GCP14_Script.jpg"
  - "images/GCP15_EditCredst.png"
  - "images/GCP1_Billing_Export.jpg"
  - "images/GCP2_Billing_Export.jpg"
  - "images/GCP3_Billing_Export.png"
  - "images/GCP4_Billing_Export.jpg"
  - "images/GCP5_Billing_Export.jpg"
  - "images/GCP6_Billing_Export.jpg"
  - "images/GCP7_Billing_Export.jpg"
  - "images/GCP8_Billing_Export.jpg"
  - "images/GCP9_Billing_Export.jpg"
  - "images/connect-google-cloud-premium.png"
  - "images/connect-google-cloud-premium1.png"
  - "images/connect-google-cloud-premium2.png"
  - "images/regenerate_cloudability_more_options.jpg"
  - "images/setup_overview_guide_gcp-error-ok.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connect Google Cloud

**Overview**

This guide walks you through the process of connecting your Google Cloud Platform to IBM
Cloudability. Cloudability supports

- GCP Standard Billing

- GCP Detailed Billing.

Once connected, you’ll gain access to the FinOps capabilities within Cloudability.

Note: To ensure full compatibility and support, please follow the connection steps as described.
Custom configurations are not supported. If you have questions, reach out to **IBM
Support**.

**Prerequisites**

- Cloudability uses IAM to create and manage custom roles

- Should have IAM permissions in [GCP for creating a custom role](https://docs.cloud.google.com/iam/docs/creating-custom-roles "(Opens in a new tab or window)")

- Cloudability uses these custom roles with permissions specific to reading billing, commitments
  and pricing data.

  - CloudabilityRole\_Billing – for billing account
  - CloudabilityRole\_Buckets - for GCS bucket access
  - CloudabilityRole\_AdvancedFeatures – for projects

- Should have permissions to create a GCS bucket within GCP .

- The following permissions are required:

  - bigquery.tables.export (export table data out of BigQuery)
  - storage.buckets.getIamPolicy
  - storage.buckets.get
  - storage.multipartUploads.abort
  - storage.multipartUploads.create
  - storage.multipartUploads.list
  - storage.multipartUploads.listParts
  - storage.objects.create
  - storage.objects.delete
  - storage.objects.get
  - storage.objects.list
  - storage.objects.update

- Should be able to execute the GCP shell script in GCP console which will bind the role to
  Cloudability 's service account ( [billing-data-service-acct@cloudability-credentials.iam.gserviceaccount.com](mailto:billing-data-service-acct@cloudability-credentials.iam.gserviceaccount.com "(Opens in a new tab or window)")) as a
  member with the custom role at the billing-project level

- To be able to successfully run our script from within your cloud console, your gcloud user needs
  to be granted the following IAM permissions at the project level:

  - iam.roles.create
  - resourcemanager.projects.setIamPolicy
  - resourcemanager.projects.getIamPolicy

- This gives customers complete control over, and visibility into, all actions taken by any entity
  assuming that role within their GCP projects.

- Admin access to the Cloudability Vendor Credentials

- Familiarity with [GCP Organizations](https://docs.cloud.google.com/resource-manager/docs/creating-managing-organization "(Opens in a new tab or window)")

- Familiarity with [GCP Credentialing using Bulk
  Actions](gcp-credentialing-bulk-actions.html)

- Access and ability to enable the Google Cloud Resource Manager API

**Getting Started:**

Cloudability’s GCP Credentialing process requires two main steps:

- GCP Billing Account Credentialing

- GCP Projects Credentialing (for Advanced features)

The GCP Billing Account Credentialing process involves a few steps which will require you to take
actions in both GCP portal and Cloudability at various phases.

During this process Cloudability will use your billing Table ID and generate a script that
contains gcloud IAM commands which will be required to be run in the GCP console.

- Check the IAM section of the appropriate project to determine whether you have these
  permissions.
- Enable the Google Cloud Resource Manager API
- Cloudability uses Google's Cloud Resource Manager API to test whether the necessary permissions
  have been granted to support the available features.
- Google's Cloud Resource Manager API provides many advantages at zero cost to you. You can read
  more about it at [Resource Manager](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2F "(Opens in a new tab or window)").
- A list of APIs made available via the Resource Manager can be found at [Cloud Resource Manager API](https://docs.cloud.google.com/resource-manager/reference/rest "(Opens in a new tab or window)").

Note: Cloudability relies on the projects.testIamPermissions API to test whether specific
permissions have been granted to support billing and advanced features. For more information,
see [Method: projects.testIamPermissions](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Freference%2Frest%2Fv1%2Fprojects%2Ftestiampermissions "(Opens in a new tab or window)").

**Credentialing** **the GCP Billing account**

**Step 1 - GCP Portal – Enable BigQuery export and Table ID**

- In the GCP Console, under **APIs & Services > Library** , search for **'Cloud Resource
  Manager API'**.
- From the Cloud Resource Manager API page, select **ENABLE** .
- Make sure that API enabled is ticked.

Working in the Google Console, type Billing in the search bar and when the results show select
Billing accounts.

![](../../../../03-media/cloudability-premium/images/GCP1_Billing_Export.jpg)

Select Billing export.

![](../../../../03-media/cloudability-premium/images/GCP2_Billing_Export.jpg)

Select Edit Settings (based on the Type of Export you are putting in place.

![](../../../../03-media/cloudability-premium/images/GCP3_Billing_Export.png)

Select the type of export you want to put in place – Standard or Detailed Billing – by clicking
Edit Settings.

Note: We recommend Detailed Billing as the data is enriched with additional details and provides
much better granular reporting.

Select your Project where your Billing Data (likely your billing project) will be held and then
click in Data Set and select Create a New Data Set.

![](../../../../03-media/cloudability-premium/images/GCP4_Billing_Export.jpg)

Add a Dataset ID and click Create Data Set.

Note: We recommend selecting a multi-region location (EU or US) for your data set, so that your
billing data is added retroactively for the current and previous month in GCP. See [Export Billing Data to BigQuery](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery#dataset_locations_supported_for_use_with_data "(Opens in a new tab or window)") for details and
limitations

![](../../../../03-media/cloudability-premium/images/GCP5_Billing_Export.jpg)

Select Save to complete the process.

![](../../../../03-media/cloudability-premium/images/GCP6_Billing_Export.jpg)

Note: When you enable the **BigQuery** export for a **Billing** Account . A table is
automatically created for you within the specified dataset. This table is referred to as the billing
table

- GCP Standard usage cost table name should be in this
  format **gcp\_billing\_export\_v1\_<BILLING\_ACCOUNT\_ID>**.

- GCP Detailed usage cost table name should be in this
  format **gcp\_billing\_export\_resource\_v1\_<BILLING\_ACCOUNT\_ID>** .

Standard usage / Detailed usage cost table should have the below partitioning detail as mentioned
in the below image.

![](../../../../03-media/cloudability-premium/images/GCP7_Billing_Export.jpg)

Note: Google tutorial: [Export Billing Data to BigQuery](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fbilling%2Fdocs%2Fhow-to%2Fexport-data-bigquery "(Opens in a new tab or window)").

After you have enabled the BigQuery export, it will take a few hours for the billing table to be
created, after which you will be able to locate the Table ID.

You can find the billing Table ID by navigating to the project that contains the BigQuery export
of your billing data, **under Table info > Table ID** .

![](../../../../03-media/cloudability-premium/images/GCP8_Billing_Export.jpg)

You must specify a project and dataset to which the billing data will be exported, when you
enable the **BigQuery**export for a **Billing Account**. A table is automatically created
for you within the specified dataset. This table is referred to as the billing table and
Cloudability’s **Service Account**must be able to read data from this table.

**Create a storage bucket**

A Storage bucket is required to copy data from the BQ table export into, for Cloudability to then
retrieve this data.

Working in the Google Console ; type Cloud Storage in the Search bar and select it when it shows.

![](../../../../03-media/cloudability-premium/images/GCP9_Billing_Export.jpg)

Click Create to create a Bucket.

Enter a name for your storage bucket (eg: cloudability-export and click Create).

![](../../../../03-media/cloudability-premium/images/GCP10_Billing_Export.jpg)

When prompted keep defaults and click Confirm.

![](../../../../03-media/cloudability-premium/images/GCP11_Billing_Export.jpg)

Bucket will be created.

![](../../../../03-media/cloudability-premium/images/GCP12_Billing_Export.jpg)

**Step 2 - Cloudability –** **Add Credentials details in Cloudability**

**Standard Billing with GCS**

Note: For Standard Billing we recommend the use of a storage bucket and not streaming via API

Once you’ve gathered the information listed above, you can enter it into Cloudability to update
your GCP credential.

Cloudability will use this information to generate a Shell script. When the script is run from
your Cloud Shell in the GCP Portal, it will create and grant rights for Cloudability via the custom
role in order to provide access to the storage account.

- In Cloudability , navigate to
- **Settings**> **Vendor Credentials**> **Add Datasource**> **GCP**.
- Click Next
- Select GCP - the **Add GCP Account**panel opens.

Or

- **Settings**> **Vendor Credentials**> **Ingress**> **GCP**.
- Click Next
- Select GCP Standard Billing **- t**he Add a Credential panel opens.
- Enter Complete table id which is combination of project, dataset, table e.g.
  project:dataset.gcp\_billing\_export\_v1\_<BILLING\_ACCOUNT\_ID>
- Enter the GCS bucket name
- Enter Organization id (Recommended, helps in quick onboarding)

  - *GCP customers can quickly credential the projects in an automated way by using*[*GCP organization*](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Fdocs%2Fcreating-managing-organization "(Opens in a new tab or window)")*. You will need to move any
    projects you created under "No organization" into your new organization resource.*
  - *For instructions on how to move your projects, see*[*Migrating projects into an organizational
    resource*](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Fdocs%2Fproject-migration "(Opens in a new tab or window)")*.*
- Choose Advanced Rightsizing as **Read only** vs Automate Actions:
  - **Read Only** implies that customers are allowing both Cloudability cost, Turbonomic cost and
    Turbonomic monitoring permissions.
  - **Automate Actions** Only implies that customers are allowing all Cloudability and all
    Turbonomic permissions including the ones for automated actions i.e Turbonomic execution and
    Turbonomic billing execution.
- Click on generate setup script
- Click Download Script
- A GCP shell script template will be downloaded locally – save this in a secure place for your
  next step as this will need to be uploaded into the GCP console

**Standard Billing with BQ Streaming**

- **Settings**> **Vendor Credentials**> **Add Datasource**> **GCP**.
- Click Next
- Select GCP - the **Add GCP Account**panel opens.

Or

- **Settings**> **Vendor Credentials**> **Ingress**> **GCP**.
- Click Next
- Select GCP Standard Billing **- t**he Add a Credential panel opens.
- Enter Complete table id which is combination of project, dataset, table e.g.
  project:dataset.gcp\_billing\_export\_v1\_<BILLING\_ACCOUNT\_ID
- Bucket name (Optional - can be left blank)
- Organization id (Recommended, helps in quick onboarding)

  - *GCP customers can quickly credential the projects in an automated way by using*[*GCP organization*](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Fdocs%2Fcreating-managing-organization "(Opens in a new tab or window)")*. You will need to move any
    projects you created under "No organization" into your new organization resource.*
  - *For instructions on how to move your projects, see*[*Migrating projects into an organizational
    resource*](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Fdocs%2Fproject-migration "(Opens in a new tab or window)")*.*

- Choose Advanced Rightsizing options as **Read only** vs **Automate Actions**:
  - **Read Only** implies that customers are allowing both Cloudability cost, Turbonomic cost and
    Turbonomic monitoring permissions.
  - **Automate Actions** Only implies that customers are allowing all Cloudability and all
    Turbonomic permissions including the ones for automated actions i.e Turbonomic execution and
    Turbonomic billing execution.
- Click on generate setup script
- Click Download Script
- A GCP shell script template will be downloaded locally – save this in a secure place for your
  next step as this will need to be uploaded into the GCP console

![](../../../../03-media/cloudability-premium/images/GCP13_Creds.png)

**Detailed Billing with GCS (Recommended)**

- **Settings**> **Vendor Credentials**> **Add Datasource**> **GCP**.
- Click Next
- Select GCP - the **Add GCP Account**panel opens.

Or

- **Settings**> **Vendor Credentials**> **Ingress**> **GCP**.
- Click Next
- Select GCP Detailed Billing **- t**he Add a Credential panel opens.
- Enter **Complete table id** which is combination of project, dataset, table e.g.
  project:dataset.gcp\_billing\_export\_resource\_v1\_<BILLING\_ACCOUNT\_ID
- Enter the **GCS bucket name**.
- Enter the **Detailed Billing Date**.

  Note: This date indicates the month and the year from when you have detailed billing exports
  enabled. If you are doing this for the first time it is the current month as YYYY-MM.

- **Organization id** (Recommended, helps in quick onboarding)

  - *GCP customers can quickly credential the projects in an automated way by using*[*GCP organization*](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Fdocs%2Fcreating-managing-organization "(Opens in a new tab or window)")*. You will need to move any
    projects you created under "No organization" into your new organization resource.*
  - *For instructions on how to move your projects, see*[*Migrating projects into an organizational
    resource*](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Fdocs%2Fproject-migration "(Opens in a new tab or window)")*.*
- Choose Advanced Rightsizing options as **Read only** vs **Automate Actions**:
  - **Read Only** implies that customers are allowing both Cloudability cost, Turbonomic cost and
    Turbonomic monitoring permissions.
  - **Automate Actions** Only implies that customers are allowing all Cloudability and all
    Turbonomic permissions including the ones for automated actions i.e Turbonomic execution and
    Turbonomic billing execution.
- Click on generate setup script
- Click Download Script
- A GCP shell script template will be downloaded locally – save this in a secure place for your
  next step as this will need to be uploaded into the GCP console

**Step 3 – Upload and run the GCP shell script**

The script performs two steps: it first sets up a custom role within the billing project and then
adds Cloudability’s Service Account as a member of the project, binding the custom role. This
ensures that our Service Account can read data only from BigQuery tables within a billing project.
We do not access BigQuery data in non-billing projects.

In case of GCS bucket, we follow the above process, export the BigQuery data into GCS via
BigQuery export job and pull that data into Cloudability.

**1. Custom roles setup**

The script first creates custom roles within the billing project. The script attaches the
permissions necessary to read billing data to the custom role

# Example: Create billing custom role for my-billing-project-123 # Billing project ID is
my-billing-project-123 gcloud iam roles create CloudabilityRole\_Billing \ --project \
my-billing-project-123 \ --title \ "Cloudability Billing Role" \ --description \ "Allows
Cloudability access to billing account data" \ --permissions \
bigquery.jobs.create,bigquery.tables.getData \ --stage=GA

**2. Add Service Account as Member and Bind Custom role**

Once the custom role has been created, the script adds Cloudability 's **Service Account**as
a member of the billing project and binds the custom role to it.

# Example: Add Cloudability's Service Account as member of my-billing- project-123 # Billing
project ID is my-billing-project-123 gcloud projects add-iam-policy-binding my-billing-project-123 \
--member serviceAccount:billing-data-service-acct@cloudability- credentials.iam.gserviceaccount.com
\ --role 'projects/my-billing-project- 123/roles/CloudabilityRole\_Billing'

**3. GCS Bucket**

If you are opting for GCP standard billing with GCS bucket or GCP detailed billing, a GCP GCS
bucket must be configured. Cloudability will export data to this GCS bucket temporarily from the
configured GCP BigQuery table to ingest this data to Cloudability. Once the data ingestion is
complete Cloudability will delete the data from the bucket.

**Note:** Same GCP Payer Account IDs cannot be used in both standard and detailed billing at
the same instance.

**Run the script**

Follow the below steps to run the script via the Cloud Shell within your cloud console. It does
not matter from where within the Cloud Shell you run the script.

- Activate the Cloud Shell, select the ![](../../../../03-media/cloudability-premium/images/regenerate_cloudability_more_options.jpg) icon and
  select **Upload file**. Choose the downloaded script from the file explorer and confirm.
- chmod +x <scriptname> to make the script executable
- Next, run the script in your Cloud Shell:

`./ script-name`

Note: In the commands below, replace script-name with the full name and extension of the actual
script.

- Check for any errors. For example,

![](../../../../03-media/cloudability-premium/images/setup_overview_guide_gcp-error-ok.jpg)

- If the script is successful, you will see a similar output to the following in your Cloud Shell:

![](../../../../03-media/cloudability-premium/images/GCP14_Script.jpg)

**Step 4 – Cloudability Verify credentials**

- Select Verify Credentials .
- Select the refresh icon to update the status.

The green check-mark indicates that this billing account has been successfully credentialed.

Note: Your projects will not be immediately visible – this will take upto 24 hours until they all
appear in Cloudability.

You have now successfully added your billing account to Cloudability. We ingest data at regular
intervals and your billing data will be available starting from the next ingest cycle. Upon the next
ingest, we will also enumerate the projects associated with this billing account.

Lastly, if your organization has additional GCP billing accounts that you would like to add, then
please repeat this process for each of those billing accounts.

Note: While setting up your GCP accounts, turn off any applied domain restrictions. You can turn it
on once the credentialing process is completed.

After completion of this process, within a few hours,

- Cloudability will start showing your Billing data and GCP labels within Cloudability.
- Retail Pricing data would also be pulled in, for enabling custom pricing please check [**Setting up Custom Pricing Support for GCP**](https://www.ibm.com/docs/en/SSSVH06/cloudability/product/gcp-rightsizing-custom-pricing-support.html "(Opens in a new tab or window)")
- Cloudability will also display the projects.

As a next step you will need to credential the GCP projects.

**GCP Projects Credentialing (Advanced features)**

The purpose of this section is to help you walk through the process of credentialing your
projects to enable Cloudability's Advanced Features. If your organization has multiple GCP projects,
then this process must be repeated for each project for which you would like to enable Advanced
Features.

Before you begin, make sure you’ve gone through the prerequisites

To credential your project:

- Add a new project credential, as described in Configure project-level credentials.
- Run the script, as described in [Run the script](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=cloudability-connect-google-cloud#/Run "(Opens in a new tab or window)").
- Familiarize yourself with [GCP Credentialing
  using Bulk Actions](gcp-credentialing-bulk-actions.html)

**Add a new project credential**

To enable Advanced Features for a GCP project:

- Navigate to **Vendor Credentials**, and select the **GCP**tab
- Select the **Edit**icon to open Edit a Credential panel.
- - If GCP Organization Id was added at the Billing account level, then the selection of **Read
    Only** vs **Automate Actions** at the project level follows the selection made at the parent
    level
  - If GCP Organization Id was not added at the Billing account level, then the selection of **Read
    Only** vs **Automate Actions** at the project level is available on the individual
    projects.

  Select Update Credential.
- Select **Download Script**.
- If your browser prompts you with a warning, select **Keep**.

![](../../../../03-media/cloudability-premium/images/GCP15_EditCredst.png)

Run the script

For more information, see run the script section

**How to confirm success**

This can be done via bulk actions or manually.

- Bulk Verification via UI: [GCP Credentialing
  using Bulk Actions](gcp-credentialing-bulk-actions.html)

- Manual Verification via UI:

- Select **Verify Credentials  on each project**.

- Select **Details**to verify that the project has the necessary permissions for Advanced
  Features.

**Upgrading existing Cloudability customers to Cloudability Premium**

Upon
upgrading to Cloudability Premium, existing Cloudability credentials would continue to work for
Cloudability but not for Turbonomic. For both Cloudability and Turbonomic to work together,
customers would need to re-credential their accounts. This is because more permissions are required
for them to work seamlessly

1. In Cloudability, navigate to **Settings > Vendor Credentials > GCP.**
2. Select an existing account ant click on ellipses.
3. Select the pencil icon to open Edit a Credential.
4. Enter **Organization ID** (Optional): This helps in Automating the credentials at the Billing
   account level.
5. Choose Advanced Rightsizing options as **Read only** vs **Automate Actions**:
   - **Read Only** implies that customers are allowing both Cloudability cost, Turbonomic cost and
     Turbonomic monitoring permissions.
   - Automate Actions Only implies that customers are allowing all Cloudability and all Turbonomic
     permissions including the ones for automated actions i.e Turbonomic execution and Turbonomic billing
     execution.
6. Download the template.
7. Update the permissions by executing the script in GCP console.
8. Re-verify the account in Cloudability UI.
9. Successful verification with be indicated with a green tick.

Automate Actions status displays as below:

- It would be displayed as **OFF** if the **Advanced Rightsizing** toggle was selected
  as **Read Only**.
- It would be displayed as **ON** if the **Advanced Rightsizing** toggle was selected
  as **Automate Actions**.

**Note:** Automate actions just displays the status of the template which was selected for
download and does not display the Turbonomic status yet.

- If the Automated credentialing is selected using GCP Organization ID

  - Automate Actions: **ON/ OFF** will follow the selection based on the GCP Billing account.
    - If GCP Billing account is set to **Automate Actions (ON)**, all the GCP projects would be
      **ON** for accounts in the selected GCP Organization.
    - If GCP Billing account is set to **Read Only (OFF)**, all the GCP projects would be
      **OFF** for accounts in the selected GCP Organization.
  - GCP projects status cannot be changed on individual linked accounts when opted for Automated
    Credentialing via Organization ID.
- If the Automated credentialing is not selected using Organization ID.

  - Both GCP Billing accounts and projects can have different **ON/ OFF** status under Automate
    Actions.
  - The **ON/ OFF** status can be changed individually without any dependency between GCP Billing
    accounts and projects.

When switching from Advanced Rightsizing to Read only, a pop up notification is displayed
requiring confirmation.

![](../../../../03-media/cloudability-premium/images/connect-google-cloud-premium.png)

**Display of Turbonomic
Permissions**

There are additional Turbonomic permissions that gets added to basic (Billing
Data), advanced (Utilization Data) and Optimize Resources (execute actions) which are documented in
the help center documents. Once your account is verified, the list of permissions can be viewed by
choosing the **Details** option on each GCP account listed under Cloudability.

![](../../../../03-media/cloudability-premium/images/connect-google-cloud-premium1.png)

If the existing customers
do not re-credential their accounts in then:

- In Cloudability, GCP billing data ingestion will continue.
- The Automate actions will be marked as **OFF**.
- In the **Details** tab, all **Turbonomic permissions** appear with a RED x mark.

If the existing customers re-credential their accounts in Cloudability using the powershell
script with **Read Only** permissions and account(s) is verified then:

- The Automate actions will be shown as **OFF.**
- In the Details tab, related Turbonomic permissions will appear with a Green tick mark.
- Turbonomic would start working based on **Read Only** permissions.

Once the new permissions are enabled with **Automate Actions** in the GCP console and
account(s) is verified:

- The Automate actions will be marked as **ON**.
- In the Details tab, all and permissions appear with a Green tick mark.
- Turbonomic would start working with Automate Actions permissions.

Note: The Automate Actions **ON/ OFF** is displayed on the Vendor Credentials UI based
on the selection in the Toggle and download of the template.

**Credentials
Status**

Cloudability Vendor credential screen displays both account status from:

- Cloudability
- Turbonomic

Once the latest templates are run the account status should be in sync between Cloudability
and Turbonomic. For details on the account status please check account details section for more
information.

![](../../../../03-media/cloudability-premium/images/connect-google-cloud-premium2.png)

**Frequently Asked Questions**

**The details provided on the Billing Export page differ from those on the BigQuery page for
your Billing table.**

Specifically, the Table ID on the BigQuery page is constructed using the Billing Project ID,
while the Billing Export page lists the Billing Project Name. IDs are unique, while names are not.

Solution: Review prerequisites.

**What to do if Project ID, Dataset, or Table ID is getting truncated?**

Context: You enter your complete GCP Billing Table ID into and notice that there are errors.
Additionally, when you edit the credential, you notice that the Project ID, Dataset, or Table ID are
truncated. You might have retrieved or constructed your GCP Billing Table ID from the Billing Export
page.

Solution: You must copy the complete Table ID from the BigQuery page for your Billing table.

**How should I download updated template with latest permissions if there has been update of
permissions?**

Updated Template can be downloaded by editing the existing billing account and downloading the
latest template for it. Once downloaded follow the credentialing steps mentioned after download of
template.

**[Script] Error: (gcloud.iam.roles.create) A resource in the project is a subject of
conflict.**

Context: This can occur when you have an existing role within your billing project with role\_id
CloudabilityRole\_Billing. The error indicates that the script is unable to create a new role with
role\_id CloudabilityRole\_Billing because one already exists.

Solution: Ignore this error.

**[Script] Error: (gcloud.iam.roles.create) FAILED\_PRECONDITION: You can't create a role with
role\_id (CloudabilityRole\_Billing) where there is an existing role with that role\_id in a deleted
state.**

Context: This can occur when you run the script after deleting an existing role from your billing
project with role\_id CloudabilityRole\_Billing. The role could be in a deleted state and the script
can't create a new role with that role\_id. You can view the role's status (Enabled, Disabled,
Deleted) in your cloud console.

Solution: Undelete the existing role with role\_id CloudabilityRole\_Billing from your billing
project and re-run the script.

**How to handle GCP Domain Restrictions?**

If you have domain restrictions, then you might observe error messages. To overcome this,
whitelist Cloudability to query the data by adding Cloudability 's GCP workspace customer id in
their Organisation policy.

The domain is cloudability.com and the ID is C03n3dgoi

**VPC Service Controls**

[Getting Recommendations Based on GPU Data](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=cloudability-connect-google-cloud "(Opens in a new tab or window)")

**Prerequisites:**

1. Each VM must have [GPUs attached](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fcompute%2Fdocs%2Fgpus%2Fcreate-vm-with-gpus "(Opens in a new tab or window)").

1. Each VM must have a [GPU driver installed](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fcompute%2Fdocs%2Fgpus%2Finstall-drivers-gpu%23verify-driver-install "(Opens in a new tab or window)").

1. Each VM must have Python 3.6 or newer installed.

1. Each VM must have the packages required for creation of Python virtual environments installed.

Also, see [Set up GCP Monitoring Agent for
rightsizing](gcp-memory-metrics.html).

- **The Cloudability account status and Turbonomic target status do not match in the Vendor
  Credentials screens? What could be the reasons?**

  Existing Cloudability customers upgrading
  to Cloudability Premium need to re credential their accounts in order to get the latest Turbonomic
  permissions.

  Mismatch in Account status can be because of a few reasons:
  - Re-Credentialing was not done based on the latest templates/permissions.
  - If Re-Credentialing was done then possibly it was done using a previous template version and
    since then a few new permissions have been added for Cloudability Premium.
  - If Re-Credentialing does not help, please reach out to IBM support teams.

  **Where can I find different icons on accounts status descriptions?**

  [Vendor Credentials status indicators](vendor-credentials.html)

  **To view the complete SCUD
  enhancements in the Cloudability reporting UI for a GCP Payer account, which billing export should
  be used for credential setup?**

  The **GCP Detailed Billing export** is recommended, as it
  provides full visibility into over‑utilized and under‑utilized scenarios within Cloudability
  reporting

- [GCP Credentialing using Bulk Actions](gcp-credentialing-bulk-actions.html)
- [Permissions Reference - GCP](permissions-reference-gcp.html)
- [Set up GCP Monitoring Agent for rightsizing](gcp-memory-metrics.html)
- [Support for GCP Tags](gcp-tags.html)
- [Setting up Custom Pricing
  Support for GCP](../product/gcp-rightsizing-custom-pricing-support.html)
- [Setting up Commitment Portfolio for GCP](commitment-portfolio-gcp.html)

- **[GCP Credentialing using Bulk Actions](../admin/gcp-credentialing-bulk-actions.html)**
- **[Permissions Reference - GCP](../admin/permissions-reference-gcp.html)**
- **[Set up GCP Monitoring Agent for rightsizing](../admin/gcp-memory-metrics.html)**
- **[GCP Tags and Labels](../admin/gcp-tags.html)**
- **[Setting up Custom Pricing Support for GCP](../product/gcp-rightsizing-custom-pricing-support.html)**
- **[Setting up Commitment Portfolio for GCP](../admin/commitment-portfolio-gcp.html)**
