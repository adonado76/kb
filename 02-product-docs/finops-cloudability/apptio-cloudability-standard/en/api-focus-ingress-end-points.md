---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "FOCUS Ingress End Points"
breadcrumb:
  - "Cloudability API"
  - "FOCUS Ingress End Points"
source_path: "SSVCLNQ/api-v3/focus_public_api.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# FOCUS Ingress End Points

Summary

Following are the list of public APIs provided specific to Custom Data.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/byod/accounts for RESTful CRUD interactions

end point : /v3/vendors/byod/accounts?include=permissions&viewId=0

end point : /v3/vendors/byod/accounts/<account_id>?include=permissions&viewId=0

end point : /v3/vendors/byod/accounts/<account_id>?viewId=0

end point : /v3/vendors/byod/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0

end point : /v3/vendors/byod/accounts/<account_id>/archive?viewId=0

end point : /v3/vendors/byod/permissions/accounts/<account_id>

Parameters

- type (string) - "aws_byod_role” | “azure_byod” | “gcp_byod_role”,
- vendorKey (string) - “byod”
- byodVendor (string) - Name of FOCUS data vendor
- vendorAccountId (string) - account id,
- projectId (string) - GCP project ID
- tenantId (string) - UUID – Azure tenant ID,
- roleName (string) - “CloudabilityCustomDataRole “ - AWS role name
- externalId (string) - AWS external id
- subscriptionGuid (string) - UUID – Azure subscription ID,
- resourceGroupName (string) - Azure resource group name, storageAccountName(string): Azure storage account name,
- rootDir (string) - root directory path,
- subDirs (string) - sub directory path if any,
- manifestPrefix (string) - <this-value>-Manifest.json

End Points

POST v3/vendors/byod/accounts

This API is used for creating a new Databricks credential

Example Request for AWS

```
{
"vendorAccountId": "11111166421",
"type": "aws_byod_role",
"byodVendor": "GitHub",
"byodCostReportSpec": {
"rootDir": "byodbucket",
"subDirs": "subFolder",
"manifestPrefix": "cost-and-usage"
}
}
```

Example Response for AWS

```

"result": {
"id": "byod_11111166421_GitHub",
"vendorAccountName": "byod_11111166421_GitHub",
"vendorAccountId": "byod_11111166421_GitHub",
"vendorKey": "byod",
"verification": {
"state": "unverified"
},
"authorization": {
"type": "aws_byod_role",
"roleName": "CloudabilityBYODRole",
"externalId": "aa625912-a33b-4e64-85a4-81349d8d6ea1",
"rootDir": "byodbucket",
"subDirs": "subFolder",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-13T12:37:43+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}


```

Example Request for Azure

```
{
"vendorAccountId": "1111010",
"type": "azure_byod",
"byodVendor": "GitHub",
"tenantId": "aa2a724a-8aaa-4a66-813a-a6a9aa4a3021",
"byodAzureCostReportSpec": {
"subscriptionGuid": "a4a2aaa5-2384-4090-8a3a-7a01a6a417a1",
"resourceGroupName": "billingexportresourcegroup",
"storageAccountName": "billingexportstorageacct",
"rootDir": "focuspricesheetcontainer",
"subDirs": "focuspricesheetdir",
"manifestPrefix": "FocusTest"
}
```

Example Response for Azure

```
{
"result": {
"id": "byod_1111010_GitHub",
"vendorAccountName": "byod_1111010_GitHub",
"vendorAccountId": "byod_1111010_GitHub",
"vendorKey": "byod",
"verification": {
"state": "unverified"
},
"authorization": {
"type": "azure_byod",
"tenantId": "aa2a724a-8aaa-4a66-813a-a6a9aa4a3021",
"subscriptionGuid": "a4a2aaa5-2384-4090-8a3a-7a01a6a417a1",
"resourceGroupName": "billingexportresourcegroup",
"storageAccountName": "billingexportstorageacct",
"tenancyId": "aa2a724a-8baa-4a66-813a-a6a9aa4a3021",
"rootDir": "focuspricesheetcontainer",
"subDirs": "focuspricesheetdir",
"manifestPrefix": "FocusTest"
},
"createdAt": "2024-06-13T12:22:02+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}




```

Example Request for GCP

```
{
"vendorAccountId": "01A4AA-A4A7A3-AAAAAA",
"type": "gcp_byod_role",
"byodVendor": "GitHub",
"projectId": "project",
"byodCostReportSpec": {
"rootDir": "gcs_bucket",
"subDirs": "my/sub/dirs",
"manifestPrefix": "cost-and-usage"
}
}
```

Example Response for GCP

```

"result": {
"result": {
"id": "byod_01A4AA-A4A7A3-AAAAAA_GitHub",
"vendorAccountName": "byod_01A4AA-A4A7A3-AAAAAA_GitHub",
"vendorAccountId": "byod_01A4AA-A4A7A3-AAAAAA_GitHub",
"vendorKey": "byod",
"verification": {
"state": "unverified"
},
"authorization": {
"type": "gcp_byod_role",
"rootDir": "gcs_bucket",
"subDirs": "my/sub/dirs",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-13T12:29:45+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}
```

PUT v3/vendors/byod/accounts/<accountId>

This API is used for updating the credential with the given ID

Example Request for AWS

```
{
"vendorAccountId": "byod_111111111111_zoomnew",
"type": "aws_byod_role",
"byodVendor": "zoomnew",
"byodCostReportSpec": {
"rootDir": "byodbucket",
"subDirs": "subFolder1",
"manifestPrefix": "cost-and-usage"
}
}
```

Example Response for AWS

```
{
"result": {
"id": "byod_111111111111_zoomnew",
"vendorAccountName": "byod_111111111111_zoomnew",
"vendorAccountId": "byod_111111111111_zoomnew",
"vendorKey": "byod",
"verification": {
"state": "unverified"
},
"authorization": {
"type": "aws_byod_role",
"roleName": "CloudabilityBYODRole",
"externalId": "f1cf6025-a2e5-4252-b3bd-0580b384c1fa",
"rootDir": "byodbucket",
"subDirs": "subFolder1",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-17T14:54:27+05:30",
"consumerOrgId": "",
"byodVendor": "zoomnew"
}
}
```

GET /v3/vendors/byod/accounts/<accountID>

This API is used for returning byod credentials for the given account.

Example Response for AWS

```
{
"result": {
"id": "byod_111111111111_GitHub",
"vendorAccountName": "byod_111111111111_GitHub",
"vendorAccountId": "byod_111111111111_GitHub",
"vendorKey": "byod",
"verification": {
"state": "unverified"
},
"authorization": {
"type": "aws_byod_role",
"roleName": "CloudabilityBYODRole",
"externalId": "8e68ee11-8685-414b-982c-32871d62b322",
"rootDir": "s3byodbucket",
"subDirs": "subFolders",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-12T11:27:55+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}
```

Example Response for Azure

```
{
"result": {
"id": "byod_1111111_GitHub",
"vendorAccountName": "byod_1111111_GitHub",
"vendorAccountId": "byod_1111111_GitHub",
"vendorKey": "byod",
"verification": {
"state": "verified",
"lastVerificationAttemptedAt": "2024-06-17T09:19:53+05:30"
},
"authorization": {
"type": "azure_byod",
"tenantId": "cf2c724d-8bfd-4b66-813d-e6f9df4f3022",
"tenancyId": "cf2c724d-8bfd-4b66-813d-e6f9df4f3022"
},
"createdAt": "2024-06-13T12:01:46+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}
```

Example Response for GCP

```
{
"result": {
"id": "byod_01A091-A83A6A-1A55AA_GitHub",
"vendorAccountName": "byod_01A091-A83A6A-1A55AA_GitHub",
"vendorAccountId": "byod_01A091-A83A6A-1A55AA_GitHub",
"vendorKey": "byod",
"verification": {
"state": "verified",
"lastVerificationAttemptedAt": "2024-06-17T09:13:14+05:30"
},
"authorization": {
"type": "gcp_byod_role",
"rootDir": "staging-rightsizing-test",
"subDirs": "byod_data",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-13T12:52:44+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}
```

GET v3/vendors/byod/accounts

This API is used for returning all byod credentials for given org.

Example Response

```
{
"result": [
{
"id": "byod_111111111111_GitHub",
"vendorAccountName": "byod_111111111111_GitHub",
"vendorAccountId": "byod_111111111111_GitHub",
"vendorKey": "byod",
"verification": {
"state": "verified",
"lastVerificationAttemptedAt": "2024-06-11T17:44:01+05:30"
},
"authorization": {
"type": "aws_byod_role",
"roleName": "CloudabilityByodRole",
"externalId": "11111111-2222-3333-4444-555555555555",
"region": "us-west-2",
"rootDir": "s3byodbucket",
"subDirs": "subFolder",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-11T17:42:31+05:30",
"consumerOrgId": "",

"byodVendor": "GitHub"
},
{
"id": "byod_111111111111_GitHub",
"vendorAccountName": "byod_111111111111_GitHub",
"vendorAccountId": "byod_111111111111_GitHub",
"vendorKey": "byod",
"verification": {
"state": "unverified"
},
"authorization": {
"type": "aws_byod_role",
"roleName": "CloudabilityBYODRole",
"externalId": "8e68ee11-8685-414b-982c-32871d62b322",
"rootDir": "s3byodbucket",
"subDirs": "subFolder",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-12T11:27:55+05:30",
"consumerOrgId": "",

"byodVendor": "GitHub"
}
]
}
```

DELETE v3/vendors/byod/accounts/:accountId

This API is used for deleting the credential with the given ID.

Example Response

```
{
"result": {
"message": "Successfully deleted",
"vendorKey": "byod",
"vendorAccountId": "111111111111"
}
}
```

DELETE v3/vendors/byod/accounts/:accountId

This API is used for deleting the credential with the given ID.

Example Response

```
{
"result": {
"message": "Successfully deleted",
"vendorKey": "byod",
"vendorAccountId": "111111111111"
}
}
```

POST v3/vendors/byod/accounts/:accountId/verification

This API is used for verifying the credential with the given ID.

Example Response for AWS

```
{
"result": {
"id": "byod_111111111111_GitHub",
"vendorAccountName": "byod_111111111111_GitHub",
"vendorAccountId": "byod_111111111111_GitHub",
"vendorKey": "byod",
"verification": {
"state": "verified",
"lastVerificationAttemptedAt": "2024-06-17T09:08:58+05:30"
},
"authorization": {
"type": "aws_byod_role",
"roleName": "CloudabilityByodRole",
"externalId": "11111111-2222-3333-4444-555555555555",
"region": "us-west-2",
"rootDir": "s3byodbucket",
"subDirs": "subFolder",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-11T17:42:31+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}


```

Example Response for Azure

```
{
"result": {
"id": "byod_1111111_GitHub",
"vendorAccountName": "byod_1111111_GitHub",
"vendorAccountId": "byod_1111111_GitHub",
"vendorKey": "byod",
"verification": {
"state": "verified",
"lastVerificationAttemptedAt": "2024-06-17T09:19:53+05:30"
},
"authorization": {
"type": "azure_byod",
"tenantId": "aa2a724a-8aaa-4a66-813a-a6a9aa4a3022",
"tenancyId": "aa2a724a-8aaa-4a66-813a-a6a9aa4a3022"
},
"createdAt": "2024-06-13T12:01:46+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}


```

Example Response for GCP

```
{
"result": {
"id": "byod_01A091-A83A6A-1A55AA_GitHub",
"vendorAccountName": "byod_01A091-A83A6A-1A55AA_GitHub",
"vendorAccountId": "byod_01A091-A83A6A-1A55AA_GitHub",
"vendorKey": "byod",
"verification": {
"state": "verified",
"lastVerificationAttemptedAt": "2024-06-17T09:13:14+05:30"
},
"authorization": {
"type": "gcp_byod_role",
"rootDir": "staging-rightsizing-test",
"subDirs": "byod_data",
"manifestPrefix": "cost-and-usage"
},
"createdAt": "2024-06-13T12:52:44+05:30",
"consumerOrgId": "",
"byodVendor": "GitHub"
}
}
```

POST v3/vendors/databricks/accounts/:accountId/archive

This API is used for archiving the credential with the given ID.

Example Response for AWS

```
{
"result": {
"id": "byod_999999999933_GitHub",
"vendorAccountName": "byod_999999999933_GitHub",
"vendorAccountId": "byod_999999999933_GitHub",
"vendorKey": "byod",
"verification": {
"state": "archived"
},
"meta": {},
"consumerOrgId": ""
}
}
```
