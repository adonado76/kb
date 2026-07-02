---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Connect Jira Cloud"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
source_path: "admin/connect-jira-cloud.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connect Jira Cloud

This article explains how to set up Jira Cloud in Cloudability.

Before you start

Before you begin, ensure the following:

- Your organization uses Jira Cloud (and not Jira Server).
- You are a Cloudability administrator.
- The administrator for your Jira instance is available during the setup process.
- You have the site name for your Jira instance.

Steps for integration

Jira credentials to Cloudability 

1. In Cloudability , navigate to  Settings  >  Vendor
   Credentials  >  Add Datasource  >  JIRA
    .
2. The  Add JIRA Account  panel opens.
3. Enter the name of Base URL.
4. Select  Save  .

Cloudability to Jira 

1. Log in to your Jira Cloud instance as an admin.
2. Select  Settings > Add-ons  .
3. Select  Find new add-ons  .
4. Search for 'Cloudability'.
5. Select  Install  .
6. Select  Accept & install  . Wait for the installation to complete.

How to confirm success

Check the status under  Settings  >  Vendor Credentials
 .
