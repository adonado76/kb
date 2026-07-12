---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Connect MongoDB"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect MongoDB"
source_path: "SSVCLNQ/admin/connect-mongodb.html"
images:
  - "03-media/apptio-cloudability-standard/MongoDB-Organization.jpeg"
  - "03-media/apptio-cloudability-standard/MongoDB-Permissions.jpeg"
  - "03-media/apptio-cloudability-standard/MongoDB-API.jpeg"
  - "03-media/apptio-cloudability-standard/MongoDB-CLDY.jpeg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connect MongoDB

Overview

This guide walks you through the process of connecting your MongoDB to IBM Cloudability. Once connected, you’ll gain access to the MongoDB Cost and usage data within Cloudability.

Prerequisites

- You should be a Cloudability administrator.
- You should have admin permissions in the MongoDB Atlas console.

- The high-level line item for AWS
- The line items with detailed MongoDB costs, with "AWS Marketplace" listed as Seller.

If you want to hide your marketplace costs, set up a filter.

Marketplace costs are excluded from billing.

MongoDB Account Credentialing process involves a few steps which will require you to take actions in both MongoDB console and Cloudability at various phases.

During this process Cloudability will use your MongoDB OrganizationID to connect with your account and fetch the Cost and usage data.

Step 1 – MongoDB Console

Get your Organization ID

1. Go to the MongoDB Atlas console.
1. Click on the user profile and then on Organizations.
1. Click on the Organization name
1. Click the gear icon next to the Organization settings.
1. Copy the your Organization ID and save it for use later.

Create an Organization API Key

1. Go the Access Manager page in the MongoDB Atlas console.
1. Click on applications and select the API tab
1. Click Create API Key .
1. Enter the API Key information. In the Description box, enter a description (e.g., Cloudability Access). In the Organization Permissions menu, select the Organization Billing Viewer role.
1. Click Next .
1. Copy the public and private keys

Step 2 – Cloudability

1. Open Cloudability in a new tab or window.
1. In Cloudability, go to Settings > Vendor Credentials .
1. In the Ingress section, choose the MongoDB tile. The Add MongoDB Account panel opens.
1. Read the information presented and choose the Next button when you are ready to proceed.
1. Paste the copied Organization ID into the Organization ID field.
1. Paste the Public Key and Private Key into their respective fields.
1. From the Subscription Model field, choose whether your organization uses a Marketplace or buys Direct from MongoDB.
1. Click on the Save button.
1. Click on Verify Credentials .

By default, MongoDB restricts API access using the IP Access List for the Atlas Administration API. If this is not disabled for your organization, use the following IP ranges to give MongoDB access to Cloudability:

- 185.115.88.0/22
- 103.195.128.0/22
- 129.41.0.0/22

For more details on Whitelisting IPs please contact IBM Support teams.

Frequently Asked Questions

- Which version on MongoDB is supported in Cloudability? MongoDB Atlas
- When should I use Marketplace vs subscription? If you bought MongoDB from a Marketplace like AWS or Azure use this option If you bought MongoDB Direct from MongoDB then select Direct
