---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Supplementary Credentialing Help for Commitment Functionality"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Configure Optimization Functionality"
source_path: "product/supplementary_credentialing_help_for_commitment_functionality.html"
images:
  - "images/details.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Supplementary Credentialing Help for Commitment Functionality

Note: Note: Commitment management functionality only supports vendor and account-based views. When
selecting a view whose logic is based on business mappings and tags beyond vendor and account, the
page will result in error. This behavior is due to the following reasons: - Performance metrics
often cannot be deterministically be calculated across various business metrics and tags. If we were
to show these screens without this data, the portfolio page would lack most data of interest. - It
is best practice that commitments are managed centrally. When sharing is turned on, or when the
commitment type is only ever at the payer account level, determining performance at lower level
business mapping/tags becomes impossible in exchange for the organization being better off. - Tag
mappings and business mappings contain rules that restrict a user to only a portion of an account.
To protect the privacy of customers, we only allow users with appropriate permissions to view the
commitments pages, as commitments deal with entire accounts. This is a limitation with data and how
it interacts with view filtering.

Note:

You must have administrator rights in Cloudability to view or enable credentials. If you don't
have administrator rights, contact your organization’s primary Cloudability administrator for
assistance.

## Credentialing Commitment Management for AWS

**Generate recommendations for AWS EC2**

The Cloudability product suite enables optimizing the usage of AWS EC2 Convertible Reserved
Instances (CRIs) including cost monitoring, reporting, and recommendations including CRI exchange
recommendations. The following information is about enabling and utilizing convertible reserved
instance exchange recommendations.

**Verify permissions**

Before you get started, you'll want to make sure that you have the appropriate
**ec2:GetReservedInstancesExchangeQuote** permission enabled. This permission is required for
Cloudability to generate convertible exchange recommendations for either partial or all upfront
CRIs.

To check the status of the required permission:

1. Navigate to **Settings > Vendor Credentials** .
2. Within the **AWS** tab, select ![image details icon](../../../../03-media/cloudability-premium/images/details.jpg) to view the permissions of any relevant
   accounts.

   Accounts that do not have the necessary permissions enabled are identified by anything
   other than a green checkmark next to the **ec2:GetReservedInstancesExchangeQuote** line item.

   If the required permission is not enabled, you can enable it by regenerating a Cloud Formation template and applying it to the
   applicable accounts. For more information, see [Cloudability Manage AWS credentials](../admin/manage-aws-credentials.html).

   Note: After the CloudFormation template is applied and verified by the
   Cloudability Platform, it will take approximately 1 hour before recommendations appear.

Viewing the Owned Savings Plan Inventory

Getting started

Before you begin, you will want to ensure that the necessary permissions have been enabled,
which provide access to Savings Plan functionality.

Credentialing must be viewed and performed by a user with admin rights for your Cloudability
account. If you do not have admin access or you are not sure if you have admin rights, check with
your organization’s primary Cloudability administrator.

To check the status of the necessary credentials:

1. Navigate to Settings > Vendor Credentials .

   In the primary accounts
   view for the AWS and Azure tabs, any master payer or linked account that owns Savings (or you are
   intending to use to purchase Savings) has a green box with a white check status indicator under 
   Advanced Features
2. For an account with any status indicators other than the green box with a white checkmark,
   select ![status icon ](../../../../03-media/cloudability-premium/images/details.jpg) to
   inspect the individual credentials. x
3. In the  Credential Details  window, if the  savings
   plans:DescribeSavingsPlans  permission in the  Reservations  tab
   shows a red  x  , it needs to be updated (by regenerating and applying
   CloudFormation templates) before you can see an inventory of your Savings Plans.

## Credentialing Commitment Management for Azure

**Validate your account access**

Commitment Recommendations generates Azure resource-based commitment recommendations by accessing
the Azure Cloud API. Since Azure Cloud limits API access to enterprise accounts, you must ensure:

- Your account is covered by an Enterprise Agreement
- You have access to the Azure Enterprise Portal

If you don't have an enterprise account, access to the Azure Enterprise Portal, or if you aren't
sure, contact your Azure account representative for assistance.

**Enable your Azure credentials**

1. To check the status of your Azure credentials, navigate to **Settings > Vendor Credentials**.
2. Select the **AZURE** tab.
3. Ensure **Billing Reports** and **Advanced Features** are enabled for the master
   (enrollment) account. You should see two green check boxes on the row for the master account.

Note:

- While it's best to have **Billing Reports** and **Advanced Features** enabled for both
  master (enrollment) and linked (subscription) accounts, you only need to enable these permissions
  for the master account to use the Commitment Recommendations for Azure.

- While it's best to have **Billing Reports** and **Advanced Features** enabled for both
  master (enrollment) and linked (subscription) accounts, you only need to enable these permissions
  for the master account to use the Commitment Recommendations for Azure.

**Parent topic:** [Configure Optimization Functionality](../product/configure_optimization_functionality.html)
