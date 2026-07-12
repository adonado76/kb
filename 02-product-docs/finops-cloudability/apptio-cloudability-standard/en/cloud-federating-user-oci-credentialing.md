---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Federating a User for OCI Credentialing"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Oracle Cloud"
  - "Federating a User for OCI Credentialing"
source_path: "SSVCLNQ/admin/oci-credentialing.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Federating a User for OCI Credentialing

Summary

This page outlines the step-by-step process to handle a federated user in an identity provider for OCI, specifically focusing on the creation and configuration of users and groups in the Oracle Identity Cloud Service (“IDCS”).

This process is optional, it is done by deploying a terraform and then replacing the user with a federated user.

Pre-requisites

To create users and groups in the Oracle Identity Cloud Service federation, you will need the Identity Domain Administrator role, or be a member of a group that has been granted that role.

Steps

Preparation

Ensure that " CloudabilityDataCollector_Group ", " CloudabilityDataCollector_User ", and " CloudabilityCostDataReaderPolicy " are already created through Terraform.

Deleting Local User

Delete the " CloudabilityDataCollector_User " if it exists.

1. Navigate to Identity -> Federation -> Identity Provider Details -> Users .
1. Create a new IDCS user using the following credentials. Username : CloudabilityDataCollector_Fed_User Email : cldyfeduser@cloudability.com or any valid email First Name : CloudabilityDataCollector Last Name : Fed_User
1. Click Create and then Close .

1. Navigate to Identity -> Federation -> Identity Provider Details -> Group .
1. Create a new group in IDCS called " CloudabilityDataCollector_Fed_Group ".
1. Add the federated user " CloudabilityDataCollector_Fed_User " to the group.

Mapping Local Group to Federated Group

Since federated groups cannot be given access via policy, you need to map a local group to the federated group.

1. Navigate to Identity -> Federation -> Identity Provider Details -> Group Mappings.
1. Create a new group in IDCS called " CloudabilityDataCollector_Fed_Group ".
1. Create a mapping between the OCI group " CloudabilityDataCollector_Group " and the federated group " CloudabilityDataCollector_Fed_Group ".

Synchronization of OCI Synched User

Navigate to Identity -> Federation -> Identity Provider Details -> Users -> " CloudabilityDataCollector_Fed_User ".

Click on the OCI Synched User link of the federated user " CloudabilityDataCollector_Fed_User ".

1. Navigate to API Keys .
1. Add a new API key.
1. Generate an API key pair.
1. Download the private key and the public key.
1. Add the keys.

Providing details to Cloudability

Provide the required details, including API keys and other relevant information, to Cloudability through the user interface.
