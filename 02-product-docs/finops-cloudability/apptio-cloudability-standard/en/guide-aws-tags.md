---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "AWS Tags"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connecting with AWS - Customer Integration Guide"
  - "AWS Tags"
source_path: "SSVCLNQ/admin/support-for-aws-tags.html"
images:
  - "03-media/apptio-cloudability-standard/Tag1.png"
  - "03-media/apptio-cloudability-standard/tag2.png"
  - "03-media/apptio-cloudability-standard/tag3.png"
  - "03-media/apptio-cloudability-standard/tag4.png"
  - "03-media/apptio-cloudability-standard/tag5.png"
  - "03-media/apptio-cloudability-standard/tag6.png"
  - "03-media/apptio-cloudability-standard/tag7.png"
  - "03-media/apptio-cloudability-standard/tag8.png"
  - "03-media/apptio-cloudability-standard/tag9.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# AWS Tags

Cloudability supports the below tags for AWS:

- Resource level tags These are part of the AWS CUR files and no extra permissions are required within Cloudability for enabling these
- Account level tags To get account level tags from AWS Organizations, Cloudability needs an additional permission named organizations:ListTagsForResource These are displayed in the below format in Cloudability cldy:aws:accountLevelTag:<tag key> Note: If a customer switches from legacy CUR to CUR 2.0, then they have to reconfigure their Tags and Labels within Cloudability. Account level tags are currently not available in Cloudability Gov. Difference between AWS Legacy CUR and CUR 2.0 tags Legacy CUR tags format aws tags = aws:<tagkey> e.g. aws:autoscaling:groupname user tags = <tagkey> e.g. application CUR 2.0 tags format aws tags= aws_<tag key will be separate with _> =e.g. aws_autoscaling_group_name user tags = user_<tagkey> e.g. user_application

In order to enable the resource level tags , please ensure you have enabled the below:

In the AWS Console - Enable cost allocation tags

- From the Billing & Cost Management Dashboard , navigate to Cost Allocation Tags .
- Select the tags that you want to include
- Note – Please be mindful of camel case, example if you have “Name” or “name” as a tag key – both needs to be activated so they are written to CUR.
- Select Activate .

In Order to enable account level tags from AWS Organizations, Cloudability needs an additional permission named organizations:ListTagsForResource

If you are an existing AWS customer in Cloudability, you can enable this feature using two options:

Option 1 - Re-credential your AWS master payer account(s) for which you want to enable AWS account level tags

1. Go to IAM Dashboard in AWS and click on Roles .
1. Search for the role that you assigned to Cloudability. If you have not renamed the role, it should show up as CloudabilityRole . Click on this role.
1. Under Permission policies , click on CloudabilityManagementAccountPolicy
1. Click Edit .
1. Switch to Visual view on the top right. Expand Organizations .
1. Check the permission ListTagsForResource .
1. Select Next .
1. Under Review & save, click Save Changes .
1. Verify that the permission shows a green tick under the Cost tab in the permissions pane (displayed on click of eye icon for the respective master account) in Cloudability, as below:
