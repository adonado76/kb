---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Connect Datadog - Cost and Usage Data"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connect Datadog - Utilization Data"
source_path: "admin/connect-datadog-cost-usage_data.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connect Datadog - Cost and Usage Data

You can connect your Datadog account to Cloudability to enable the ingestion of cost and usage
data. If you have already credentialed a Datadog account to bring utilization data for our
rightsizing feature, you can edit this existing account to bring cost data as well. Simply select
 cost  under the  reporting  section in the
credentialing page and add the  API Key  and  Application Key
 .

Note: It takes unto 24 hours before your initial cost and usage data appears in
Cloudability. During this time, a message indicates that the process is yet to complete.

Summary of the Integration

Datadog allows us to go back and pull cost data for the past 15 months. If the invoice is
finalized, then you will see costs attributed to the first of the month. If the invoice has not been
finalized, you will see daily costs associated to the products and services you have purchased. This
means that generally, you will see daily data for the current month and the last month, until the
date that the invoice has been finalized.

Our integrations honor least-privileged principles, where we have designed the connectors to
work with the lowest level of permission necessary for us to pull the relevant data into
Cloudability.

Note: If you are purchasing Datadog via a cloud provider marketplace and adding cost
and usage data for Datadog with this integration, you will see costs displayed twice in Cloudability
reporting. As an example, if you purchased Datadog via the AWS Marketplace, you would have:

The
high-level line items per month for AWS

The line items with detailed Datadog costs and “AWS
Marketplace” listed as “Seller”

You will need to set up filters or views to hide your
Marketplace costs. Marketplace costs are excluded from billing.

Before you start

Before you begin, ensure the following:

- You are a Cloudability administrator.
- You have admin permissions in the Datadog console.

  - We recommend an **Admin**to create a new user and downgrading that new user
    from **Admin**User to **Read-Only**user for the purposes of this integration.
  - If you are an existing Datadog Administrator setting up this integration, we encourage you to
    create a new login through creation of a new user, using a different email address (different than
    the one used for your admin role). Downgrade this user to a **Read-Only**user.

Steps for integration

We recommend an  Admin  to create a new user and downgrading that new
user from  Admin  User to  Read-Only  user for the
purposes of this integration.

If you are an existing Datadog Administrator setting up this integration, we encourage you to
create a new login through creation of a new user, using a different email address (different than
the one used for your admin role). Downgrade this user to a  Read-Only  user.

Create new keys in Datadog

In the Datadog console:

1. Invite a new member as an Admin User for the integration.

   See [Datadog’s User Roles and Permission](https://docs.datadoghq.com/account_management/users/ "(Opens in a new tab or window)")  for more information.
2. Log in as the newly created Admin User.
3. Navigate to  Integrations > APIs > New API key  .
4. Create a new API key.
5. Go to the  New application key  section and create a new application key.

Add your Datadog keys to Cloudability 

1. In Cloudability , navigate to  Settings  >  Vendor
   Credentials  .
2. Select the  Datadog  tab.
3. Select  Yes, I'm ready  to confirm you have your Datadog keys.
4. Copy and paste the new API key and application key into the relevant field.
5. Input your API limit in  Rate Limit  . to 300, which is the default rate
   limit.

   Note: Tags are not yet supported for Datadog

   In case you need IP whitelisting, the following IP
   ranges will give access to Cloudability :

   - 185.115.88.0/22
   - 103.195.128.0/22

**Parent topic:** [Connect Datadog - Utilization Data](../admin/connect-datadog-premium.html)
