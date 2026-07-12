---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Vendor Credentials End Point (OCI)"
breadcrumb:
  - "Cloudability API"
  - "Vendor Credentials End Point (OCI)"
source_path: "SSVCLNQ/api-v3/vendor_credentials_end_point_oci.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Vendor Credentials End Point (OCI)

Summary

This end point is used to manage credentials within Cloudability that support the integration and ingestion of data from public cloud vendors. This includes tasks such as initial setup, listing out current credentials and deleting deprecated credentials.

This end point does not support filtering and sorting.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/oci/accounts for RESTful CRUD interactions

end point : /v3/vendors/oci/accounts?include=permissions&viewId=0

end point : /v3/vendors/oci/accounts/<account_id>?include=permissions&viewId=0

end point : /v3/vendors/oci/accounts/<account_id>/terraform-template

end point : /v3/vendors/oci/accounts/<account_ id>/verification?include=permissions,associatedAccounts&viewId=0

end point : /v3/vendors/oci/accounts/<account_id>/archive?viewId=0

Parameters

- Id (string) - tenancy OCID
- vendorAccountName (string) - tenancy name
- vendorAccountId (string) - tenancy OCID
- vendorKey (string) - oci
- roleName (string) - currently hardcoded to "CloudabilityRole",
- verification (object) - object containing details of verification state: state (string) - examples "unverified", "verified", "error" lastVerificationAttemptedAt (string) - date timestamp, example: "1970-01-01T00:00:00.000Z" message (string) -error message for credentials in error state
- authorization (object) -object contain vendor specific authorization details type (string) - oci_user (this field will never change) tenancyId (string) - tenancy OCID userId (string) - user OCID region - home region name groupId - group OCID namespace - currently hardcoded to “bling” but can be updated
- createdAt - (string) - date timestamp corresponding to Cloudability credential creation time
- ociCostReportSpec namespace bucket compartment privateDetails fingerprint (string) -fingerprint passphrase (string) - optional field secret (string) - private key

List Accounts

Example Request

```
curl 'https://api.cloudability.com/v3/vendors/oci/accounts?viewId=0' \\ 
 -u ‘[auth_token]:’
```

Example Response

```
{ 
"result": [ 
{ 
"id": "ocid1.tenancy.oc1..aaaaaaaa1aaaaaaaaa1aaa1aa1aaaaa1aaaaaaaaaa1aaaaaaaaaa1aaaaaa", 
"vendorAccountName": "testaccount", 
"vendorAccountId": "ocid1.tenancy.oc1..aaaaaaaa1aaaaaaaaa1aaa1aa1aaaaa1aaaaaaaaaa1aaaaaaaaaa1aaaaaa", 
"vendorKey": "oci", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2026-02-04T08:14:11Z" 
}, 
"authorization": { 
"type": "oci_user", 
"permissions": [ 
"oci.list.assignedSubscriptions", 
"oci.list.tenancies", 
"oci.get.instanceFamily", 
"oci.list.imageShape.Compatibility", 
"oci.list.computeShapes", 
"oci.get.costReports", 
"oci.get.metrics", 
"oci.list.computeImages" 
], 
"tenantId": "ocid1.tenancy.oc1..aaaaaaaa1aaaaaaaaa1aaa1aa1aaaaa1aaaaaaaaaa1aaaaaaaaaa1aaaaaa", 
"tenancyId": "ocid1.tenancy.oc1..aaaaaaaa1aaaaaaaaa1aaa1aa1aaaaa1aaaaaaaaaa1aaaaaaaaaa1aaaaaa", 
"userId": "ocid1.user.oc1..aaaaaaaamcxbi4ldug2wgmytoakyjjmhaeb33lb7fflbnfpwxzlbdmzrqyoa", 
"groupId": "ocid1.group.oc1..aaaaaaaafnl54eo33p6kqgxynrvqxcrkvm3hjwzichapgekxtrkjgi2qmn3a", 
"region": "us-chicago-1", 
"namespace": "bling" 
}, 
"createdAt": "2023-07-05T10:24:20Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
}, 
{ 
"id": "ocid1.tenancy.oc1..aaaaaaaa2aaaaaaaaa2aaa2aa2aaaaa2aaaaaaaaaa2aaaaaaaaaa2aaaaaa", 
"vendorAccountName": "testaccountchild1", 
"vendorAccountId": "ocid1.tenancy.oc1..aaaaaaaa2aaaaaaaaa2aaa2aa2aaaaa2aaaaaaaaaa2aaaaaaaaaa2aaaaaa", 
"vendorKey": "oci", 
"verification": { 
"state": "error", 
"message": "No permissions present for this account", 
"lastVerificationAttemptedAt": "2026-02-04T04:52:11Z" 
}, 
"authorization": { 
"type": "oci_user", 
"tenantId": "ocid1.tenancy.oc1..aaaaaaaa2aaaaaaaaa2aaa2aa2aaaaa2aaaaaaaaaa2aaaaaaaaaa2aaaaaa", 
"tenancyId": "ocid1.tenancy.oc1..aaaaaaaa2aaaaaaaaa2aaa2aa2aaaaa2aaaaaaaaaa2aaaaaaaaaa2aaaaaa", 
"userId": "ocid1.user.oc1..aaaaaaaa3aaaaaaaaa2aaa2aa2aaaaa2aaaaaaaaaa3aaaaaaaaaa3aaaaaa", 
"groupId": "ocid1.group.oc1..aaaaaaaa4aaaaaaaaa4aaa4aa4aaaaa4aaaaaaaaaa3aaaaaaaaaa3aaaaaa", 
"region": "us-chicago-1" 
}, 
"createdAt": "2023-07-09T08:30:54Z", 
"parentAccountId": "ocid1.tenancy.oc1..aaaaaaaa1aaaaaaaaa1aaa1aa1aaaaa1aaaaaaaaaa1aaaaaaaaaa1aaaaaa", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
} 
] 
}
```

Create Credential for Root Tenancy

Example Request

```
curl -X POST 'https://api.cloudability.com/v3/vendors/oci/accounts?viewId=0 
\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 

{ 
   "vendorAccountId": "sample tenant OCID", 
   "tenancyId": "sample tenant OCID", 
   "ociCostReportSpec": { 
   "namespace": "bling", 
   "bucket": "sample tenant OCID", 
   "compartment": "sample tenant OCID" 
}, 
      "type": "oci_user" 
} 
```

Update Credential for newly created Tenancy after running the terraform template

Example Request

```
curl -X PUT 'https://api.cloudability.com/v3/vendors/oci/accounts/<tenancy-id>?include=permissions&viewId=0 
\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 

{ 
"vendorAccountId": "sample tenant OCID", 
"tenancyId": "sample tenant OCID", 
"userId": "user-id", 
"region": "region", 
"groupId": "group-id", 
"ociCostReportSpec": { 
"bucket": "bling", 
"namespace": "bling", 
"compartment": "sample tenant OCID" 
}, 
"privateDetails": { 
"fingerprint": " fingerprint-details ", 
"passphrase": " passphrase-details", 
"secret": " secret " 
}, 
"type": "oci_user" 
} 
```

Retrieve a Tenancy

Example Request

```
curl   
'https://api.cloudability.com/v3/vendors/oci/accounts/[vendorAccountId]’\\ 
-u ‘[auth_token]:’ 
```

Delete Credential for a Tenancy

Example Request

```
curl --X DELETE  
'https://api.cloudability.com/v3/vendors/oci/accounts/<account_id>?viewId=0’ 
-u ‘[auth_token]:’ 
```

V erify Credential for a Tenancy

Example Request

```
curl --X POST  
'https://api.cloudability.com/v3/vendors/oci/<account_id>/verification?include=permissions,associatedAccounts&viewId=0’ \\ 
-u ‘[auth_token]:’ 
```

Get Terraform Template for a Tenancy

Example Request

```
curl   
'https://api.cloudability.com/v3/vendors/oci/<account_id>/terraform-template’ \\ 
-u ‘[auth_token]:’ 
```

Archive Tenancy

Example Request

```
curl --X POST  
'https://api.cloudability.com/v3/vendors/oci/<account_id>archive?viewId=0’ \\ 
-u ‘[auth_token]:’ 
```
