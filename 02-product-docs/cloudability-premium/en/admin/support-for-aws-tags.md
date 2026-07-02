---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "AWS Tags"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connecting with AWS - Customer Integration Guide"
source_path: "admin/support-for-aws-tags.html"
images:
  - "images/Tag1.png"
  - "images/tag2.png"
  - "images/tag3.png"
  - "images/tag4.png"
  - "images/tag5.png"
  - "images/tag6.png"
  - "images/tag7.png"
  - "images/tag8.png"
  - "images/tag9.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS Tags

Cloudability supports the below tags for AWS:

- **Resource level tags**
  - These are part of the AWS CUR files and no extra permissions are required within Cloudability
    for enabling these
- **Account level tags**
  - To get account level tags from AWS Organizations, Cloudability needs an additional permission
    named
    - organizations:ListTagsForResource
  - These are displayed in the below format in Cloudability
    - cldy:aws:accountLevelTag:<tag key>

      Note: If a customer switches from legacy CUR to CUR 2.0,
      then they have to reconfigure their Tags and Labels within Cloudability.

      Account level tags
      are currently not available in Cloudability Gov.Difference between AWS Legacy CUR and CUR 2.0 tags
  - Legacy CUR tags format
    - aws tags = aws:<tagkey> e.g. aws:autoscaling:groupname
    - user tags = <tagkey> e.g. application
  - CUR 2.0 tags format
    - aws tags= aws\_<tag key will be separate with \_> =e.g. aws\_autoscaling\_group\_name
    - user tags = user\_<tagkey> e.g. user\_application

In order to enable the **resource level tags**, please ensure you have enabled the below:

In the AWS Console - Enable cost allocation tags

- From the **Billing & Cost Management Dashboard**, navigate to [**Cost
  Allocation Tags**.](https://console.aws.amazon.com/billing/home#/tags "(Opens in a new tab or window)")
- Select the tags that you want to include
- Note – Please be mindful of camel case, example if you have “Name” or “name” as a tag key – both
  needs to be activated so they are written to CUR.
- Select **Activate**.

In Order to enable **account level tags** from AWS Organizations, Cloudability needs an
additional permission named ***organizations:ListTagsForResource***

**If you are an existing AWS customer in Cloudability, you can enable this feature using two
options:**

**Option 1** - Re-credential your AWS master payer account(s) for which you want to enable AWS
account level tags

**Option 2** - If you don't want to re-credential, you can grant the above mentioned
permission to Cloudability IAM role that is added in your AWS account using the steps below:

1. Go to **IAM Dashboard** in AWS and click on **Roles**.![tag](../../../../03-media/cloudability-premium/images/Tag1.png)
2. Search for the role that you assigned to Cloudability. If you have not renamed the role, it
   should show up as **CloudabilityRole**. Click on this role.![tag](../../../../03-media/cloudability-premium/images/tag2.png)
3. Under **Permission policies**, click on **CloudabilityManagementAccountPolicy**![](../../../../03-media/cloudability-premium/images/tag3.png)
4. Click **Edit**.![tag](../../../../03-media/cloudability-premium/images/tag4.png)
5. Switch to **Visual** view on the top right. Expand **Organizations**.![tag](../../../../03-media/cloudability-premium/images/tag5.png)
6. Check the permission **ListTagsForResource**.

   ![tag](../../../../03-media/cloudability-premium/images/tag6.png)
7. Select **Next**.![tag](../../../../03-media/cloudability-premium/images/tag7.png)
8. Under **Review & save,** click **Save Changes**.

   ![tag](../../../../03-media/cloudability-premium/images/tag8.png)
9. Verify that the permission shows **a green tick under** the **Cost** tab in the
   permissions pane (displayed on click of eye icon for the respective master account) in Cloudability,
   as below:

![tag](../../../../03-media/cloudability-premium/images/tag9.png)

Note: It may take a couple of hours for the permissions to get updated in Cloudability Vendor
Credentialis UI.

**Parent topic:** [Connecting with AWS - Customer Integration Guide](../admin/aws-credentialing-premium-home.html)
