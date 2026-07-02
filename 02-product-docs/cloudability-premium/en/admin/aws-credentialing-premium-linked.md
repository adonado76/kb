---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "AWS Linked Account Credentialing"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connecting with AWS - Customer Integration Guide"
source_path: "admin/aws-credentialing-premium-linked.html"
images:
  - "images/AWS-linked1.png"
  - "images/TurboTarget.png"
  - "images/aws-linkedp.png"
  - "images/clip_image001_-1832790195.png"
  - "images/clip_image001_1499665667.png"
  - "images/clip_image002_-1398377466.png"
  - "images/clip_image002_-1577046812.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS Linked Account Credentialing

Note: To ensure full compatibility and support, please follow the connection steps as described.
Custom configurations are not supported. If you have questions, reach out to **IBM
Support**.

After configuring your management account for data ingestion, Cloudability will display
linked accounts under the management account in a few hours, but they don't contain any AWS API
data.

AWS API data is required to get utilisation and commitments data which enables the
Optimization set of features (eg: Rightsizing) in Cloudability.

To enable access to AWS API
endpoints for each linked account, Cloudability generates CloudFormation templates for you to upload
to AWS. This can be done via Automation (recommended) or manually for every linked
account.

Automated Credentialing of Linked accounts

We recommend
using automation as this process simplifies the credentialing process - especially when you have a
significant number of linked accounts.

Before you begin:

- Familiarize yourself with [AWS Stacksets](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacksets-prereqs-self-managed.html#stacksets-prereqs-accountsetup "(Opens in a new tab or window)").
- Ensure you have the IAM role in your AWS - AWSCloudFormationStackSetAdministrationRole – this
  ensures linked accounts can have the permissions pushed to them.
- Ensure you have checked the “Automated credentialing of Linked Accounts” during the Consolidated
  Account Credentialing process previously.
- Familiarize yourself with [AWS Credentialing using Bulk Actions](aws-credentialing-bulk-actions.html)

In Cloudability - Navigate to the linked account

- Navigate to **Settings > Vendor Credentials > AWS** .
- Click your mouse cursor over on the … of the a linked account **(not management
  account)**.
- Select the pencil icon to open the Edit a Credential panel.
- Add AWS SCP Enabled Region (Optional):
  - In the event you have applied AWS Service Control Policy/policies (SCP) which restrict access in
    some AWS regions, indicate your allowed region; for example us-east-2. If not, this can be left
    blank. This helps Cloudability to make verification calls to the allowed region specified.
  - Currently Cloud ability supports addition of a single SCP region.
- **Choose Advanced Rightsizing Options as Read Only vs **Automate Actions****
  - **Read Only** selection implies that you are allowing both Cloudability cost, Turbonomic cost
    and Turbonomic monitoring permissions to read your environment and not take actions.
  - ****Automate Actions**** selection implies that you are allowing all Cloudability and all
    Turbonomic permissions including the ones for automated actions i.e. Turbonomic execution and
    Turbonomic billing execution.

  If Automated credentialing of AWS linked accounts is selected, then the selection of **Read
  Only** vs ****Automate Actions**** at the linked account follows the selection made at the
  parent level.

  - Select **Save.**
  - Select **Download.**![aws](../../../../03-media/cloudability-premium/images/AWS-linked1.png)

In AWS - Upload the CloudFormation template to the AWS Management
Console

1. In the **AWS Management Console**, working in the linked account you are credentialling, in
   the search bar enter 'CloudFormation' and select it.
2. From the **AWS CloudFormation** page, select **Create StackSet**
3. Under **Specify template**, do the following:
   - Leave default parameters for permissions and prerequisites
   - Select Upload a template file.
   - Select Choose file and upload the template you downloaded from Cloudability.
   - Select **Next** .
4. From the **Specify StackSet details** page, do the following:
   - Enter a **StackSet name** (for example, 'Cloudability').
   - Verify the populated **Parameters**.
   - Select **Next**.
5. Scroll through the **Configure StackSet options** page and check the “I acknowledge that AWS
   Cloudformation might create IAM resources with customized names” and click Next.
6. From the **Review** page, Select **Submit**.

Your new stack initially has a status of **CREATE\_IN\_PROGRESS.** When the status changes
to **CREATE\_COMPLETE,** you can verify your credential in Cloudability. You may need to refresh
the CloudFormation page in the UI to confirm this.

In Cloudability - Verify the
Consolidated Account Credential

This can be done via bulk actions or
manually.

Bulk Verification via UI: [AWS Credentialing using Bulk Actions](aws-credentialing-bulk-actions.html)

Manual Verification via UI:

1. Navigate to **Settings** > **Vendor Credentials** > **AWS**.
2. Click on the … next to the account being credentialed and select Re-Verify.
   - A green tick (![](../../../../03-media/cloudability-premium/images/clip_image001_-1832790195.png)) indicates success where
     as a red exclamation (![](../../../../03-media/cloudability-premium/images/clip_image002_-1398377466.png)) indicated
     errors.

Note: This process will create a new role called as CloudabilityRole\_OU which Cloudability will
use to verify the permissions. We recommend using code/automation and the Cloudability API endpoint,
when you have a significant number of linked accounts.

![aws](../../../../03-media/cloudability-premium/images/aws-linkedp.png)

Manual Credentialing AWS Linked
Accounts

This is only applicable if the previous “Automated credentialing of
Linked accounts” **was left unchecked** during the Consolidated Account Credentialing
process

In Cloudability – Navigate to Linked Account

- Navigate to **Settings > Vendor Credentials > AWS.**
- Click your mouse cursor on the … of a linked account **(not management account)**
- Select the pencil icon to open the Edit a Credential panel.
- Add AWS SCP Enabled Region (Optional):
- In the event you have applied AWS Service Control Policy / policies (SCP) which restrict access
  in some AWS regions, indicate your allowed region; example us-east-2. If not, this can be left
  blank. This helps Cloudability to make verification calls to the allowed region specified.
- **Choose Advanced Rightsizing as Read Only vs **Automate Actions****
  - **A Read Only** selection implies that you are allowing both Cloudability cost, Turbonomic
    cost and Turbonomic monitoring permissions to read your environment and not take actions.
  - ****Automate Actions**** selection implies that you are allowing all Cloudability and all
    Turbonomic permissions including the ones for automated actions i.e. Turbonomic execution and
    Turbonomic billing execution.

If Automated credentialing of AWS linked accounts is selected, then the selection of **Read
Only** vs ****Automate Actions**** at the linked account follows the selection made at the
parent level.

- Select **Save**.
- Select **Download**.

In AWS - Upload the CloudFormation template to the AWS Management
Console

Complete the following steps to Upload the CloudFormation template to the AWS
Management Console as a Stack. This will have to be done in every linked account.

1. In the **AWS Management Console**, working in the linked account you are credentialling, in
   the search bar enter 'CloudFormation'
2. Select it.
3. From the **AWS CloudFormation** page, select **Create Stack (with new resources
   (standard)**
4. Under **Specify template**, do the following:
   - Select **Upload a template file**
   - Select **Choose file** and upload the template you downloaded from Cloudability.
   - Select **Next.**
5. From the **Specify stack details** page, do the following:
   - Enter a **Stack name** (for example, 'Cloudability')
   - Verify the populated **Parameters**.
   - Select **Next**.
6. Scroll through the **Configure stack options** page and check the “I acknowledge that AWS
   Cloudformation might create IAM resources with customized names” and click Next
7. From the **Review** page, Select **Submit**.

In Cloudability – Verify Linked Account
Credential

This can be done via bulk actions or manually.

Bulk Verification via
UI: [AWS Credentialing using Bulk Actions](aws-credentialing-bulk-actions.html)

Manual Verification via
UI:

1. Navigate to Settings > Vendor Credentials and click on the … and select Re-Verify.

- A green tick (![../../resources/cldy_images/clip_image001_-1832790195.png](../../../../03-media/cloudability-premium/images/clip_image001_1499665667.png)) indicates success whereas a red
  exclamation (![../../resources/cldy_images/clip_image002_-821243953.png](../../../../03-media/cloudability-premium/images/clip_image002_-1577046812.png)) indicated errors that need to be
  followed up.
- This process will need to be repeated for every Linked account one by one.

**Credentials Status**

Cloudability Vendor credential screen displays both account
status from:

- Cloudability
- Turbonomic

Once the latest templates are run the account status should be in sync between Cloudability
and Turbonomic. For details on the account status please check account details section.

![](../../../../03-media/cloudability-premium/images/TurboTarget.png)

**Parent topic:** [Connecting with AWS - Customer Integration Guide](../admin/aws-credentialing-premium-home.html)
