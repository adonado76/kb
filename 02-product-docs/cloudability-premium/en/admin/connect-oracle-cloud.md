---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Connect Oracle Cloud"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
source_path: "admin/connect-oracle-cloud.html"
images:
  - "images/OCI-api-key.png"
  - "images/OCI-generate-api-key.png"
  - "images/OCI-user-groups-.png"
  - "images/generating__api_oci_3.jpg"
  - "images/oracle-cloud-adding-credentials-child-tenancies.jpg"
  - "images/terraform_script_1.jpg"
  - "images/terraform_script_2.jpg"
  - "images/terraform_script_3.jpg"
  - "images/terraform_script_4.jpg"
  - "images/terraform_script_5.jpg"
  - "images/terraform_script_7.jpg"
  - "images/validating_oci_1.jpg"
  - "images/validating_oci_3.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connect Oracle Cloud

You can connect your Oracle Cloud Infrastructure (OCI) tenancy to Cloudability to enable the
ingestion of cost and usage data.

Note: It takes upto 24 hours before your initial cost and usage
data appears in Cloudability.

To ensure full compatibility and support, please follow the
connection steps as described. Custom configurations are not supported. If you have questions, reach
out to **IBM Support**.

Summary of the integration 

1. Getting your cost and usage data in Cloudability 

   Cloudability gets your OCI cost and usage data from Cost Reports, which are
   owned by OCI and located in the root tenancy of your OCI console. To provide Cloudability with
   access to your OCI cost and usage data, you need to validate the credentials for your root tenancy
   as the data for your child tenancies roll up to the root tenancy.

   The
   credentialing process is done using a Terraform script and your root tenancy OCID is required to
   generate and run the script. The script includes commands to create a group and a user, add the user
   to the group, create policies, and attach them to the group so that Cloudability can access the cost
   reports from the OCI console. Please note that these policies provide Cloudability with read-only
   permission to the OCI data.

   Once the script is executed in the OCI
   console, you will need to generate Signing Keys. The last step will be to paste the home region
   name, user OCID, group OCID, Fingerprint and Private Key in Cloudability UI.
2. Getting your utilization data in Cloudability 

   Once you have completed the credentialing process for your root tenancy, you
   will be getting OCI utilization data only for your parent tenancy. After the credentials are
   verified, your child tenancies are displayed in the credentialing UI, and you will need to go
   through the credentialing process for these child tenancies as well to get their utilization data.
   Getting utilization data will allow Cloudability to provide rightsizing recommendations. You can
   find more details at the bottom of this page under “  Adding Credentials for your child
   tenancies  ”.

**Prerequisites**

Before you begin, ensure the following:

- You are a Cloudability administrator.
- You have administrator permissions in the OCI console.
  - This is required to execute the Terraform script in the OCI console .

Integration Steps

Get your OCI Tenancy ID 

1. Log in to the Oracle Cloud Infrastructure (OCI) Console.
2. Select  Governance & Administration  from the navigation menu at the top left corner
   of the dashboard.
3. Select  Tenancies  in the  Organization Managemen  t header. Your tenancies are
   listed here.
4. Copy your parent tenancy ID, by selecting the copy icon next to your tenancy ID with "Parent
   tenancy" in the name.
5. In Cloudability , navigate to  Settings  > 
   Vendor Credentials  >  OCI.
6. Select  Add a Credential  . The  Add a Credential  panel opens on the left side.
7. Paste the parent tenancy ID.
8. Select  Save  .

Generate the Terraform Script

Once your Tenancy ID is saved, select   Generate Script  . It downloads the terraform
script. Please create a specific folder eg: Cloudability and save
the script in that folder in your local machine. This is done as when you upload the script you
cannot individually upload the script – You have to upload the folder which contains the script.

The following is the terraform content used by Cloudability
to create required resources:

```
variable "cloudablity_user_email" {
				description = "This is a variable to assign the email to user. If not provided, default email will be set."
				type        = string
				default     = "cldyuser@cloudability.com"
				}
				 
				resource "oci_identity_user" "cloudablity_user" {
				compartment_id = "ocid1.tenancy.oc1..aaaaaaaa4pjpasfply4eky7dl6msfdt3doqpfpmbuw2aesigtvedd4oxhufa"
				description = "This is a Cloudability user and they will be accessing cost data from your tenant."
				name = "CloudabilityDataCollector_User"
				freeform_tags = {
				"User_Created_For"= "Cloudability"
				}
				}
				 
				resource "oci_identity_group" "cloudability_group" {
				compartment_id = "ocid1.tenancy.oc1..aaaaaaaa4pjpasfply4eky7dl6msfdt3doqpfpmbuw2aesigtvedd4oxhufa"
				description = "This is a Cloudability group and it will be accessing cost data from your tenant."
				name = "CloudabilityDataCollector_Group"
				freeform_tags = {
				"Group_Created_For"= "Cloudability"
				}
				}
				 
				resource "oci_identity_user_group_membership" "user_group_membership" {
				group_id = oci_identity_group.cloudability_group.id
				user_id = oci_identity_user.cloudablity_user.id
				}
				 
				resource "oci_identity_policy" "cloudability_policy" {
				compartment_id = "ocid1.tenancy.oc1..aaaaaaaa4pjpasfply4eky7dl6msfdt3doqpfpmbuw2aesigtvedd4oxhufa"
				description = "This policy will retrieve permissions to access the cost report and list policy."
				name = "CloudabilityCostDataReaderPolicy"
				freeform_tags = {
				"Policy_Created_For"= "Cloudability"
				}
				statements = [
				"define tenancy reporting as ocid1.tenancy.oc1..aaaaaaaaned4fkpkisbwjlr56u7cj63lf3wffbilvqknstgtvzub7vhqkggq",
				"endorse group ${oci_identity_group.cloudability_group.name} to read objects in tenancy reporting",
				"allow group ${oci_identity_group.cloudability_group.name} to read organizations-tenancy in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read organizations-family in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read policies in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read metrics in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read rate-cards in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read instance-images in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to inspect instances in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read instance-family in tenancy"
				]
		}
```

Note: The variable "cloudablity\_user\_email" is added in the Terraform script, since it is required
information for users that are using Identity Domain in their OCI console. The email address
"cldyuser@cloudability.com" is a placeholder example and can be changed in the terraform script
directly or updated later when it is uploaded in the OCI console.

Upload the Terraform script 

1. In the OCI console, select the navigation menu on the top left corner of the dashboard page, and
   then select  Developer Services  .

   ![OCI terraform screenshot](../../../../03-media/cloudability-premium/images/terraform_script_1.jpg)
2. Select  Stacks  in the  Resource Manager  header.

   Note: Make sure to select the root compartment in the  List Scope  on the
   left side view.

   ![OCI resource manager  screenshot](../../../../03-media/cloudability-premium/images/terraform_script_2.jpg)
3. Select  Create Stack  to create a new stack.

   ![OCI create stack screenshot](../../../../03-media/cloudability-premium/images/terraform_script_3.jpg)
4. In the  Create Stack  page, select  My Configuration  to upload Terraform
   configuration files.

   ![OCI my configuration  screenshot](../../../../03-media/cloudability-premium/images/terraform_script_4.jpg)
5. In Stack configuration section, select  Folder  , and then browse to the folder where the
   configuration file is stored.
6. Select  Upload  on the pop-up.

   Note: Make sure that the selected
   compartment has "(root)" selected under the  Create in Compartment  field.

   ![OCI upload terraform screenshot](../../../../03-media/cloudability-premium/images/terraform_script_5.jpg)
7. In the  Name  textbox, enter ‘ Cloudability ’ as the
   value. Select  Next  .
8. You now have the option to update the email address “cldyuser@cloudability.com” that is provided
   in the Terraform script. This variable is only required if you have  Identity Domain  in your
   OCI console and can be updated at this stage, if required.
9. Select Terraform version as "1.5"
10. Select the  Run Apply  checkbox.

    ![](../images/OCI_Terrform_version%20update.png)
11. Select  Create  to create the stack.

The  Resource Manager  will validate the provided Terraform file and
create a new stack.

Monitor the job status (lifecycle state) by getting the job.  Succeeded  indicates the
job is complete.

This job will create a User, a Group and a Policy. The operation can take some time depending on
the complexity of the job. While the job runs, or after it is completed, you will get the job logs
content.

Once the stack is created, you can see it in the  Stacks  section.

![OCI terraform stack screenshot](../../../../03-media/cloudability-premium/images/terraform_script_7.jpg)

Validate the created resources 

1. Select  Identity & Security  from the navigation menu at the top-left corner of the
   dashboard.

   ![OCI terraform identity and security  screenshot](../../../../03-media/cloudability-premium/images/validating_oci_1.jpg)
2. Select  Users  in the  Identity  header by going
   to Identity → Domain → Select Domain → User Management Tab.

   You can notice
   a user named "CloudabilityDataCollector\_User" that was created by the Terraform job.

   Note: If you
   do not wish Cloudability to create a local user and instead would like to have a “federated” user,
   see  [Federating a User for OCI Credentialing](oci-credentialing.html)  .
3. Select  Groups  in the  Identity  header. If you
   are leveraging  Identity Domain  , you will need to select 
   Domains  in the  Identity header  , and then select 
   Default domain, User management  and select  Groups  . You can
   notice a group named "CloudabilityDataCollector\_Group" that was created by the Terraform job.
4. Select '  CloudabilityDataCollector\_Group  ' to check if ' 
   CloudabilityDataCollector\_User  ' has been added into this group as a  Group Member  .
5. In the  Group Information  , copy the group OCID and save it. This
   information will need to be pasted later in Cloudability UI.

   ![](../../../../03-media/cloudability-premium/images/OCI-user-groups-.png)
6. Select  Policies  in the Identity header.

   ![OCI terraform policies screenshot](../../../../03-media/cloudability-premium/images/validating_oci_3.jpg)

   You can notice the policy named "CloudabilityCostDataReaderPolicy" that was created by the
   Terraform job. This policy contains all the policies required to fetch data from the customer
   environment. Modifying this policy name is not supported.

Generate the API key 

1. Select  Identity & Security  from the navigation menu at the top-left corner of the
   dashboard.
2. Select  Users  in the  Identity  header by going
   to Identity → Domain → Select Domain → User Management Tab.

   Note: If you are leveraging the
    Identity Domain  module, select  Domains  in the
   Identity header, and then select  Default domain  and  Users
    .
3. Select the user named "CloudabilityDataCollector\_User".
4. Select  API keys  →  Add API Key 

   ![](../../../../03-media/cloudability-premium/images/OCI-api-key.png)
5. Select  Generate API Key Pair  .

   ![](../../../../03-media/cloudability-premium/images/OCI-generate-api-key.png)
6. Select  Download Private Key  . You will need to paste it later in Cloudability UI.
7. Select  Download Public Key  .
8. Select  Add  and the fingerprint will be generated.
9. Select  View Configuration  file.

   ![OCI terraform view configuration screenshot](../../../../03-media/cloudability-premium/images/generating__api_oci_3.jpg)

Step 2 - In Cloudability - Add information in Cloudability UI 

1. In Cloudability , navigate to  Settings  >
    Vendor Credentials  >  Add Datasource  >
    OCI  . The  Add OCI Account  panel opens.

   Or

   In Cloudability , navigate to  Settings  >  Vendor
   Credentials  > OCI. Select  Add a Credential  . The
    Add a Credential  panel opens.

   Paste the information in the configuration file as below:
   - Home Region  : This is displayed next to  region 
     in the  Configuration File
   - User ID  : This is displayed next to  user  in
     the  Configuration File  .
   - Group ID  : This information was saved during the previous step. You can
     find this OCID by navigating to  Identity & Security  > 
     Groups  > '  CloudabilityDataCollector\_Group  '.
   - Namespace  : This is your OCI namespace, please fill in the namespace
     configured.
   - Fingerprint  : This is displayed directly in the  
     Configuration File  .
   - Passphrase  : This can be left blank.
   - Private Key  : This information was saved during the previous step .

     Note: Make sure to paste the  Private Key  in its entirety in Cloudability ,
     including "-----BEGIN PRIVATE KEY----” and “-----END PRIVATE KEY----".
2. Select  Save  .
3. Select  Verify Credential  .

   Note: Make sure to select  Save
    before selecting  Verify Credential  to avoid any error
   messages.

If the information is correctly verified, a green check mark appears under
 Billing Reports. A green check mark will appear under the 
Advanced Features  as well but only for the root tenancy.

After completion of this process, within a few hours,

- Cloudability will start showing your Billing data and OCI tags within Cloudability.
- Pricing data would also be pulled in
- Cloudability will also display the OCI child tenancies.

As a next step you will need to credential the OCI child tenancies..

Once you see your OCI data, you can proceed to update your tags and business mappings - you can
learn more about this in the  [Apptio Community Post](https://community.apptio.com/blogs/soline-plichta/2023/09/14/cloudability-for-oci-cost-management-faq "(Opens in a new tab or window)")  .

Step 3 - In Cloudability - Adding Credentials for your child tenancies

Once your credentials are verified, your child tenancies will be automatically discovered by Cloudability and displayed in the UI. Hover over the 3 dots on the
right side of your child tenancy and select the “pencil” button.

![OCI terraform add credentails for child screenshot](../../../../03-media/cloudability-premium/images/oracle-cloud-adding-credentials-child-tenancies.jpg)

Then, you can start credentialing your child tenancies, following the same process described
above for parent tenancies.

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

It will take up to 48 hours to get your
utilization data in Cloudability and start receiving rightsizing recommendations.

Permission List

You can find below the list of permissions displayed in OCI credential details. Some of them are
applicable only to the Parent Account/ Tenancy, and not to the Child Account/ Tenancy
(“oci.get.costReports”, “oci.list.tenancies”, and “oci.list.rateCards”).

| Permission | Description | Applicable to Parent Account/ Tenancy | Applicable to the Child Account/Tenancy |
| --- | --- | --- | --- |
| oci.get.costReports | Permission to fetch cost report | Yes | No |
| oci.list.tenancies | Permission to list child tenancy from parent | Yes | No |
| oci.get.metrics | Permission to get metrics | Yes | Yes |
| oci.list.rateCards | Permission to list rate cards | Yes | No |
| oci.list.assignedSubscriptions | Permission to list assigned subscription | Yes | Yes |
| oci.list.computeShapes | Permission to list compute shapes | Yes | Yes |
| oci.list.computeImages | Permission to list compute images | Yes | Yes |
| oci.list.imageShape.Compatibility | Permission to list image shapes | Yes | Yes |
| oci.get.instanceFamily | Permission to read instance family | Yes | Yes |
| oci.list.policies | Permission to read policy for verification | Yes | Yes |

- **[Federating a User for OCI Credentialing](../admin/oci-credentialing.html)**
