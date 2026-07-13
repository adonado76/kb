---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "apptio-benchmarking"
title: "User Roles & Permissions"
breadcrumb:
  - "Getting Started"
  - "User Roles & Permissions"
source_path: "SSIU957/it-benchmarking/user-roles.html"
images: []
capability_ids: []
last_updated: "2026-07-12"
summary: ""
---
# User Roles & Permissions

User roles and permissions control who can see and work with Benchmarking. A Role is a collection of permissions that is assigned to a user, and no one can access an IBM Apptio product without at least one Role on their account, which is managed in Access Administration. In Access Administration, authorized Admins create and manage user registrations, assign or remove Roles, and control which Roles can access each product endpoint, which endpoints are open to any eligible Role, and which endpoints are hidden entirely. For details on how to assign roles, manage user accounts, and access to IBM Apptio products, see the documentation for Access Administration .

- Admin Full access to all features in Benchmarking (including Interactive Benchmarking and Costing). Includes administrative access to Access Administration and ability to create custom roles.

Custom Roles

You can create custom roles in Access Administration. Custom roles allow you to tailor access to meet your organization’s specific needs.

| Permission Name | Description |
| --- | --- |
| AccessInteractiveBenchmarkingTestTools | Can access tools for testing Interactive Benchmarking |
| ConfigureInteractiveBenchmarking | Can configure interactive benchmarking profiles, Costing data sources, currency, and selections. |
| DeleteInteractiveBenchmarkingDataAndProfiles | Can permanently delete or override Interactive Benchmarking data and/or customer profiles. |
| RetrieveInteractiveBenchmarkingCostData | Can retrieve actual cost data from Cost Transparency applications. |
| UseInteractiveBenchmarkingServiceAccount | Can connect to Cost Transparency applications using the Interactive benchmarking service account, infosvcs@apptio.com . |
| ViewInteractiveBenchmarksAndCostData | Can view dashboards displaying interactive benchmarks and cost data. |
