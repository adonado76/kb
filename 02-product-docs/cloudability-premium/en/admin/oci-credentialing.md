---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Federating a User for OCI Credentialing"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connect Oracle Cloud"
source_path: "admin/oci-credentialing.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Federating a User for OCI Credentialing

Summary

This page outlines the step-by-step process to handle a federated user in an identity provider
for OCI, specifically focusing on the creation and configuration of users and groups in the Oracle
Identity Cloud Service (“IDCS”).

This process is optional, it is done by deploying a terraform and then replacing the user with a
federated user.

Pre-requisites

To create users and groups in the Oracle Identity Cloud Service federation, you will need the
Identity Domain Administrator role, or be a member of a group that has been granted that role.

Steps

Preparation

Ensure that "  CloudabilityDataCollector\_Group  ", "  CloudabilityDataCollector\_User
 ", and "  CloudabilityCostDataReaderPolicy  " are already created through Terraform.

Deleting Local User

Delete the "  CloudabilityDataCollector\_User  " if it exists.

Creating a Federated User 

1. Navigate to  Identity  ->  Federation  ->  Identity Provider Details 
   ->  Users  .
2. Create a new IDCS user using the following credentials.

   - Username  : CloudabilityDataCollector\_Fed\_User
   - Email  : cldyfeduser@cloudability.com or any valid email
   - First Name  : CloudabilityDataCollector
   - Last Name  : Fed\_User
3. Click  Create  and then  Close  .

Creating a Federated Group 

1. Navigate to  Identity  ->  Federation  ->  Identity Provider Details 
   ->  Group  .
2. Create a new group in IDCS called "  CloudabilityDataCollector\_Fed\_Group  ".
3. Add the federated user "  CloudabilityDataCollector\_Fed\_User  " to the group.

Mapping Local Group to Federated Group

Since federated groups cannot be given access via policy, you need to map a local group to the
federated group.

1. Navigate to  Identity  ->  Federation  ->  Identity Provider Details 
   ->  Group Mappings.
2. Create a new group in IDCS called "  CloudabilityDataCollector\_Fed\_Group  ".
3. Create a mapping between the OCI group "  CloudabilityDataCollector\_Group  " and the
   federated group "  CloudabilityDataCollector\_Fed\_Group  ".

Synchronization of OCI Synched User

Navigate to  Identity  ->  Federation  ->  Identity Provider Details 
->  Users  -> "  CloudabilityDataCollector\_Fed\_User  ".

Click on the OCI Synched User link of the federated user " 
CloudabilityDataCollector\_Fed\_User  ".

Generating API Keys: 

1. Navigate to  API Keys  .
2. Add a new API key.
3. Generate an API key pair.
4. Download the private key and the public key.
5. Add the keys.

Providing details to Cloudability

Provide the required details, including API keys and other relevant information, to Cloudability through the user interface.

**Parent topic:** [Connect Oracle Cloud](../admin/connect-oracle-cloud.html)
