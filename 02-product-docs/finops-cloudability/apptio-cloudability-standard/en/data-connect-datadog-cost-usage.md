---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Connect Datadog - Cost and Usage Data"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Datadog - Utilization Data"
  - "Connect Datadog - Cost and Usage Data"
source_path: "SSVCLNQ/admin/connect-datadog-cost-usage_data.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connect Datadog - Cost and Usage Data

Summary of the Integration

Datadog allows us to go back and pull cost data for the past 15 months. If the invoice is finalized, then you will see costs attributed to the first of the month. If the invoice has not been finalized, you will see daily costs associated to the products and services you have purchased. This means that generally, you will see daily data for the current month and the last month, until the date that the invoice has been finalized.

The high-level line items per month for AWS

The line items with detailed Datadog costs and “AWS Marketplace” listed as “Seller”

You will need to set up filters or views to hide your Marketplace costs. Marketplace costs are excluded from billing.

Before you start

Before you begin, ensure the following:

- You are a Cloudability administrator.
- You have admin permissions in the Datadog console. We recommend an Admin to create a new user and downgrading that new user from Admin User to Read-Only user for the purposes of this integration. If you are an existing Datadog Administrator setting up this integration, we encourage you to create a new login through creation of a new user, using a different email address (different than the one used for your admin role). Downgrade this user to a Read-Only user.

Steps for integration

We recommend an Admin to create a new user and downgrading that new user from Admin User to Read-Only user for the purposes of this integration.

If you are an existing Datadog Administrator setting up this integration, we encourage you to create a new login through creation of a new user, using a different email address (different than the one used for your admin role). Downgrade this user to a Read-Only user.

Create new keys in Datadog

1. Invite a new member as an Admin User for the integration. See Datadog’s User Roles and Permission for more information.
1. Log in as the newly created Admin User.
1. Navigate to Integrations > APIs > New API key .
1. Create a new API key.
1. Go to the New application key section and create a new application key.

1. In Cloudability , navigate to Settings > Vendor Credentials .
1. Select the Datadog tab.
1. Select Yes, I'm ready to confirm you have your Datadog keys.
1. Copy and paste the new API key and application key into the relevant field.
1. Input your API limit in Rate Limit . to 300, which is the default rate limit. Note: Tags are not yet supported for Datadog In case you need IP whitelisting, the following IP ranges will give access to Cloudability : 185.115.88.0/22 103.195.128.0/22
