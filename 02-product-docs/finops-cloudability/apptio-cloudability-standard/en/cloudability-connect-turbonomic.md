---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Connect Turbonomic and Cloudability"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Turbonomic and Cloudability"
source_path: "SSVCLNQ/admin/connect-turbonomic.html"
images:
  - "03-media/apptio-cloudability-standard/turbonomics_usermanagement.jpg"
  - "03-media/apptio-cloudability-standard/turbonomics_usermanagement2.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connect Turbonomic and Cloudability

This integration enables Apptio Cloudability customers to leverage Turbonomic insights within Cloudability.

Before you start

You need to have a local user in Turbonomics. In case you don’t have a local user, you are required to create one.

Integration Steps

1. Click to navigate to the Settings Page. From there, you can perform a variety of Turbonomic configuration tasks.
1. Select User Management . This page lists all the user accounts that you currently have configured for Turbonomic .
1. Click on a new local user account.
1. Enter the username and password for the new user, and specify the role.
1. Select a role for the local user from the list below. Advisor- Users with this role can view all Turobnomic charts and data, and run plans. However, users cannot use Place to reserve workloads, create policies, or execute any recommended actions. Automator - Users with this role can use all Turobnomic features (including Plan, Park, and Place), but cannot configure Turbonomic installation or create policies. Deployer- Users with this role can view all Turobnomic charts and data, use Place to reserve workloads, and create placement policies and templates. However, users cannot run plans or execute any recommended actions. Observer- Users with this role can view the environment, including the Home Page and Dashboards. Users can also use Search to set a scope to the session. For scope, only VM groups and Resource Groups are supported. Note the username and password of the newly created local user. Specify the Authorization – Scope (optional). The scope limits what the user can monitor in your environment.

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > Turbonomic . The Add Turbonomic Account panel opens. Or In Cloudability , navigate to Settings > Vendor Credentials > Turbonomic . Select Add a Credential . The Add a Credential panel opens.

1. Select Add a Credential . Enter the Turbonomic credentials Turbonomic IP/URL (with https), Username , and Password .
1. Click Save .
1. Click Verify Credential . Note: A green tick mark indicates that the verification is successful. If not, a red cross will be displayed. After the credentials are validated, you can change, delete, or refresh the credentials. To modify a credential, select Edit . To delete a credential, select Delete . To validate a credential, select Refresh .
