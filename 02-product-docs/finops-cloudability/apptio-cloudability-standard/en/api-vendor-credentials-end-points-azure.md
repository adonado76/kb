---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Vendor Credentials End Points (Azure)"
breadcrumb:
  - "Cloudability API"
  - "Vendor Credentials End Points (Azure)"
source_path: "SSVCLNQ/api-v3/azure-vendor-credential-end-points.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Vendor Credentials End Points (Azure)

Summary

These end points are used to manage Azure integration within Cloudability which supports creation, updation, and deletion of Azure credentials.

This end point does not support filtering and sorting.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

Public Enrollment Account (EA)

end point : /v3/vendors/azure/accounts for RESTful CRUD interactions

end point : /v3/vendors/azure/accounts/[account_id]?viewId=0

end point : /v3/vendors/azure/accounts/[account_id]/setup-scripts

end point : /v3/vendors/azure/accounts/[account_id]/verification

end point : /v3/vendors/azure/accounts/[account_id] /archive

Public Microsoft Customer Agreement (MCA)

end point : /v3/vendors/azure/accounts for RESTful CRUD interactions

end point : /v3/vendors/azure/accounts/[account_id] ?viewId=0

end point : /v3/vendors/azure/accounts/[account_id]/setup-scripts

end point : /v3/vendors/azure/accounts/[account_id]/verification

end point : /v3/vendors/azure/accounts/[account_id] /archive

The Credential Object

vendorAccountName (string) - Azure vendor Account Name

vendorAccountId (string) - Azure vendor Account ID of customers

vendorKey (string) - states the vendor type (Azure).

verification : contains state of the account

state (string) - it specifies whether the account is in verified/unverified/error state

authorization : contains the below details:

type (string) - the provider type (azure_enrollment/azure_mca/azure_subscription)

enrollmentId (string) - the enrollement account Id(only present in Azure Enrollment Accounts)

tenantId (string) - unique identifier assigned to each Azure Active Directory (AAD) instance

subscriptionGuid (string) - is a unique identifier assigned to each Azure subscription

resourceGroupName (string) - is a unique name assigned to a logical container for Azure resources

storageAccountName (string) - is the unique name assigned to an Azure Storage account

containerName (string) - refers to the unique name assigned to a container within an Azure Storage account

directoryName (string) - refers to a folder or directory within a storage account

exportNameCost (string) - cost export file name

exportNameAmortized (string) - amortized export file name

tenancyId (string) - refers to the tenantId which is a globally unique identifier assigned to each Azure Active Directory (AAD)

turboExecutionEnabled (boolean) - default to false - only required for Cloudability premium

createdAt (string) - the timestamp at which the account is credentialized

additionalData( object) -

accountAlias(string) – Alias name for a billing account for MSP

AzureTenantId(string) –– tenant id of the uncredentialled account for MSP

consumerOrgId (string) - if the account belongs to msp_consumer, this is the orgId of MSP_CONSUMER (optional, needs to be provided only if it belongs to MSP).

Public EA/MCA API

List Accounts

```
curl 'https://api.cloudability.com/v3/vendors/azure/accounts?viewId=0' \\ 
 -u ‘[auth_token]:’ 
```

```
{ 
"result": [ 
{ 
"id": "11112222", 
"vendorAccountName": "11112222", 
"vendorAccountId": "11112222", 
"vendorKey": "azure", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2025-12-16T12:32:32Z" 
}, 
"authorization": { 
"type": "azure_enrollment", 
"permissions": ["Cost Export Report", "Amortized Export Report"], 
"enrollmentId": "11112222", 
"tenantId": "11a1a111-1111-1111-1111-11aa11111aff", 
"subscriptionGuid": "ecf11fd1-dc11-11b1-1af1-db11a1a1becf", 
"resourceGroupName": "costexport", 
"storageAccountName": "cloudabilityactualcost", 
"containerName": "apptiocostmgmtcontainer", 
"directoryName": "apptiocostmgmtdirectory", 
"exportNameCost": "cloudabilityactualcost", 
"exportNameAmortized": "cloudabilityamortizedcost", 
"tenancyId": "11a1a111-1111-1111-1111-11aa11111aff" 
}, 
"meta": {}, 
"additionalData": {}, 
"createdAt": "2021-03-09T16:05:37Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
}, 
```

Create Azure EA credential

```
curl –location --request POST 'https://api.cloudability.com/v3/vendors/azure/accounts' \ 
--header 'Content-Type: application/json' \ 
--data '{ 
"vendorAccountId": "11111111", 
"type": "azure_enrollment", 
"tenantId": "11f1a111-1111-1111-1111-11cf11111bff", 
"consumerOrgId": "", 
"costReportSpec": { 
"subscriptionGuid": "ecf11fd1-dc11-11b1-1af1-db11a1a1becf", 
"resourceGroupName": "test", 
"storageAccountName": "test-acc", 
"containerName": "test-cont", 
"directoryName": "test-dir", 
"exportNameCost": "test-cost", 
"exportNameAmortized": "test-amortized" 
}'
```

```
{
"result": { 
"id": "11111111", 
"vendorAccountName": "11111111", 
"vendorAccountId": "11111111", 
"vendorKey": "azure", 
"verification": { 
"state": "unverified" 
}, 
"authorization": { 
"type": "azure_enrollment", 
"enrollmentId": "11111111", 
"tenantId": "11f1a111-1111-1111-1111-11cf11111bff", 
"subscriptionGuid": "ecf11fd1-dc11-11b1-1af1-db11a1a1becf", 
"resourceGroupName": "test", 
"storageAccountName": "test-acc", 
"containerName": "test-cont", 
"directoryName": "test-dir", 
"exportNameCost": "test-cost", 
"exportNameAmortized": "test-amortized", 
"tenancyId": "11f1a111-1111-1111-1111-11cf11111bff" 
}, 
"meta": {}, 
"createdAt": "2023-12-28T11:02:42Z", 
"consumerOrgId": "" 
} 
} 
```

```
curl –location --request POST 'https://api.cloudability.com/v3/vendors/azure/accounts' \ 
--header 'Content-Type: application/json' \ 
--data ' { 
"vendorAccountId": "1111a1a1-1111-1a11-aa11-a111a111111a:1111aa11-a1aa-1aa1-1111-1111a11a1aa1_2024-05-08", 
"type": "azure_mca", 
"tenantId": "11111111-11a1-11aa-1111-111a111a1a11", 
"consumerOrgId": "", 
"costReportSpec": { 
"subscriptionGuid": "22111111-11a1-11aa-1111-111a111a1a22", 
"resourceGroupName": "test_resource", 
"storageAccountName": "test_account", 
"containerName": "test_container", 
"directoryName": "test_dir", 
"exportNameCost": "test_cost", 
"exportNameAmortized": "test_amort" 
} 
}' 
```

```
{ 
"result": { 
"id": "1111a1a1-1111-1a11-aa11-a111a111111a:1111aa11-a1aa-1aa1-1111-1111a11a1aa1_2024-05-08", 
"vendorAccountName": "1111a1a1-1111-1a11-aa11-a111a111111a:1111aa11-a1aa-1aa1-1111-1111a11a1aa1_2024-05-08", 
"vendorAccountId": "1111a1a1-1111-1a11-aa11-a111a111111a:1111aa11-a1aa-1aa1-1111-1111a11a1aa1_2024-05-08", 
"vendorKey": "azure", 
"verification": { 
"state": "unverified" 
}, 
"authorization": { 
"type": "azure_mca", 
"tenantId": "11111111-11a1-11aa-1111-111a111a1a11", 
"subscriptionGuid": "22111111-11a1-11aa-1111-111a111a1a22", 
"resourceGroupName": "test_resource", 
"storageAccountName": "test_account", 
"containerName": "test_container", 
"directoryName": "test_dir", 
"exportNameCost": "test_cost", 
"exportNameAmortized": "test_amort", 
"tenancyId": "11111111-11a1-11aa-1111-111a111a1a11" 
}, 
"additionalData": {}, 
"createdAt": "2025-12-17T08:25:45Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
} 
}
```

```
curl –location --request POST 'https://api.cloudability.com/v3/vendors/azure/accounts' \ 
--header 'Content-Type: application/json' \ 
--data '{ 
"vendorAccountId": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"type": "azure_mpa", 
"tenantId": "11111111-11a1-11aa-1111-111a111a1a11", 
"consumerOrgId": "111111", 
"costReportSpec": { 
"subscriptionGuid": "11111111-11a1-11aa-1111-111a111a1a22", 
"resourceGroupName": "tes_resource", 
"storageAccountName": "test_storage", 
"containerName": "test_container", 
"directoryName": "test_dir", 
"exportNameCost": "test_cost", 
"exportNameAmortized": "test_amortized" 
} 
}'
```

```
{ 
"result": { 
"id": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"vendorAccountName": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"vendorAccountId": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"vendorKey": "azure", 
"verification": { 
"state": "unverified" 
}, 
"authorization": { 
"type": "azure_mpa", 
"tenantId": "11111111-11a1-11aa-1111-111a111a1a11", 
"subscriptionGuid": "11111111-11a1-11aa-1111-111a111a1a22", 
"resourceGroupName": "tes_resource", 
"storageAccountName": "test_storage", 
"containerName": "test_container", 
"directoryName": "test_dir", 
"exportNameCost": "test_cost", 
"exportNameAmortized": "test_amortized", 
"tenancyId": "11111111-11a1-11aa-1111-111a111a1a11" 
}, 
"additionalData": {}, 
"createdAt": "2025-12-17T08:32:10Z", 
"consumerOrgId": "113924", 
"byodVendor": "ABSENT" 
} 
}
```

```
curl --location --request PUT 'https://api.cloudability.com/v3/vendors/azure/accounts/<master-account-id>/auth-locations?viewId=0' \ 
--header 'Content-Type: application/json' \ 
--data ' { 
"vendorAccountIds": [ 
"11aaaa1a-11a1-1111-11a1-111a1a1aa111", 
"22aaaa2a-22a2-2222-22a2-222a2a2aa222", 
"33aaaa3a-33a3-3333-33a3-333a3a3aa333" 
], 
"turboExecutionEnabled": false 
}' 
```

```
{ 
"result": [ 
{ 
"vendorAccountId": "11aaaa1a-11a1-1111-11a1-111a1a1aa111", 
"tenantId": "11a1a111-1111-1111-1111-42aa11114aaa", 
"authUrl": "https://login.microsoftonline.com/11a1a111-1111-1111-1111-42aa11114aaa/oauth2/authorize?client_id=5bb55bbb-5555-55b5-55bb-55b5bb5bbb5b&response_type=code&response_mode=query&redirect_uri=https%3A%2F%2Fapi.cloudability.com%2Fcallback%2Factive-directory-auth%2Fconfig%2F&resource=https%3A%2F%2Fmanagement.azure.com%2F&state=8888888c-8cc8-88c8-cccc-ccc88ccc888a" 
}, 
{ 
"vendorAccountId": "22aaaa2a-22a2-2222-22a2-222a2a2aa222", 
"tenantId": "22a2a222-1111-1111-1111-42aa11114aaa", 
"authUrl": "https://login.microsoftonline.com/22a2a222-1111-1111-1111-42aa11114aaa/oauth2/authorize?client_id=6bb66bbb-6666-66b6-66bb-66b6bb6bbb6b&response_type=code&response_mode=query&redirect_uri=https%3A%2F%2Fapi.cloudability.com%2Fcallback%2Factive-directory-auth%2Fconfig%2F&resource=https%3A%2F%2Fmanagement.azure.com%2F&state=9999999c-9cc9-99c9-cccc-ccc99ccc999a" 
}, 
{ 
"vendorAccountId": "33aaaa3a-33a3-3333-33a3-333a3a3aa333", 
"tenantId": "33a3a333-3333-1111-1111-42aa11114aaa", 
"authUrl": "https://login.microsoftonline.com/33a3a333-3333-1111-1111-42aa11114aaa/oauth2/authorize?client_id=7bb77bbb-7777-77b7-77bb-77b7bb7bbb7b&response_type=code&response_mode=query&redirect_uri=https%3A%2F%2Fapi.cloudability.com%2Fcallback%2Factive-directory-auth%2Fconfig%2F&resource=https%3A%2F%2Fmanagement.azure.com%2F&state=4c-4cc4-4c4-cccc-ccc4ccc4a" 
} 
] 
}
```

```
curl --location --request PUT 'https://api.cloudability.com/v3/vendors/azure/accounts/11111111' \ 
--header 'Content-Type: application/json' \ 
--data '{ 
"vendorAccountId": "11111111", 
"type": "azure_enrollment", 
"tenantId": "11f1a111-1111-1111-1111-11cf11111bff", 
"consumerOrgId": "", 
"costReportSpec": { 
"subscriptionGuid": "ecf11fd1-dc11-11b1-1af1-db11a1a1becf", 
"resourceGroupName": "costexportName", 
"storageAccountName": "cloudabilityactualcost", 
"containerName": "apptiocostmgmtcontainer", 
"directoryName": "apptiocostmgmtdirectory", 
"exportNameCost": "NA", 
"exportNameAmortized": "NA" 
}'
```

```
{ 
"result": { 
"id": "11111111", 
"vendorAccountName": "11111111", 
"vendorAccountId": "11111111", 
"vendorKey": "azure", 
"verification": { 
"state": "unverified" 
}, 
"authorization": { 
"type": "azure_enrollment", 
"enrollmentId": "11111111", 
"tenantId": "11f1a111-1111-1111-1111-11cf11111bff", 
"subscriptionGuid": "ecf11fd1-dc11-11b1-1af1-db11a1a1becf", 
"resourceGroupName": "costexportName", 
"storageAccountName": "cloudabilityactualcost", 
"containerName": "apptiocostmgmtcontainer", 
"directoryName": "apptiocostmgmtdirectory", 
"exportNameCost": "NA", 
"exportNameAmortized": "NA", 
"tenancyId": "11f1a111-1111-1111-1111-11cf11111bff" 
}, 
"meta": {}, 
"createdAt": "2021-03-09T16:05:37Z", 
"consumerOrgId": "" 
} 
}
```

```
curl --location --request PUT 'https://api.cloudability.com/v3/vendors/azure/accounts/1111a1a1-1111-4d11-aa11-a111a111111a:1111aa11-b1aa-1aa1-2222-3333f44e2aa1_2019-05-01?viewId=0' \ 
--header 'Content-Type: application/json' \ 
--data '{ 
"vendorAccountId": "1111a1a1-1111-4d11-aa11-a111a111111a:1111aa11-b1aa-1aa1-2222-3333f44e2aa1_2019-05-01", 
"type": "azure_mca", 
"tenantId": "a2a22aaa-22aa-222a-aa22-2a2aa2aaa2a2", 
"consumerOrgId": "", 
"costReportSpec": { 
"subscriptionGuid": "a2a22aaa-22aa-222a-aa22-2a2aa2aaa2a2", 
"resourceGroupName": "test", 
"storageAccountName": "test", 
"containerName": "test", 
"directoryName": "test", 
"exportNameCost": "test", 
"exportNameAmortized": "test1" 
} 
}'
```

```
{ 
"result": { 
"id": "1111a1a1-1111-4d11-aa11-a111a111111a:1111aa11-b1aa-1aa1-2222-3333f44e2aa1_2019-05-01", 
"vendorAccountName": "1111a1a1-1111-4d11-aa11-a111a111111a:1111aa11-b1aa-1aa1-2222-3333f44e2aa1_2019-05-01", 
"vendorAccountId": "1111a1a1-1111-4d11-aa11-a111a111111a:1111aa11-b1aa-1aa1-2222-3333f44e2aa1_2019-05-01", 
"vendorKey": "azure", 
"verification": { 
"state": "unverified" 
}, 
"authorization": { 
"type": "azure_mca", 
"tenantId": "a2a22aaa-22aa-222a-aa22-2a2aa2aaa2a2", 
"subscriptionGuid": "a2a22aaa-22aa-222a-aa22-2a2aa2aaa2a2", 
"resourceGroupName": "test", 
"storageAccountName": "test", 
"containerName": "test", 
"directoryName": "test", 
"exportNameCost": "test", 
"exportNameAmortized": "test1", 
"tenancyId": "a2a22aaa-22aa-222a-aa22-2a2aa2aaa2a2" 
}, 
"additionalData": {}, 
"createdAt": "2025-02-27T10:51:38Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
} 
}
```

```
curl --location --request PUT 'https://api.cloudability.com/v3/vendors/azure/accounts/a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30?viewId=0' \ 
--header 'Content-Type: application/json' \ 
--data '{ 
"vendorAccountId": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"type": "azure_mpa", 
"tenantId": "11111111-11a1-11aa-1111-111a111a1a11", 
"consumerOrgId": "111111", 
"costReportSpec": { 
"subscriptionGuid": "11111111-11a1-11aa-1111-111a111a1a22", 
"resourceGroupName": "tes_resource", 
"storageAccountName": "test_storage", 
"containerName": "test_container", 
"directoryName": "test_dir", 
"exportNameCost": "test_cost", 
"exportNameAmortized": "test_amortized" 
} 
}' 
```

```
{ 
"result": { 
"id": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"vendorAccountName": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"vendorAccountId": "a1a11111-111a-1111-11a1-a1111a1a1111:aa1111aa-aaa1-1aa1-111a-a1aa1a111a1a_2024-09-30", 
"vendorKey": "azure", 
"verification": { 
"state": "unverified" 
}, 
"authorization": { 
"type": "azure_mpa", 
"tenantId": "11111111-11a1-11aa-1111-111a111a1a11", 
"subscriptionGuid": "11111111-11a1-11aa-1111-111a111a1a22", 
"resourceGroupName": "tes_resource", 
"storageAccountName": "test_storage", 
"containerName": "test_container", 
"directoryName": "test_dir", 
"exportNameCost": "test_cost", 
"exportNameAmortized": "test_amortized", 
"tenancyId": "11111111-11a1-11aa-1111-111a111a1a11" 
}, 
"additionalData": {}, 
"createdAt": "2025-12-17T08:32:10Z", 
"consumerOrgId": "113924", 
"byodVendor": "ABSENT" 
} 
} 
```

```
curl 'https://api.cloudability.com/v3/vendors/azure/accounts/<account-id>/setup-scripts?viewId=0' \\ 
 -u ‘[auth_token]:’ 
```

```
{ 
"result": { 
"scripts": "script content........" 
} 
}
```

```
curl -X POST 'https://api.cloudability.com/v3/vendors/azure/accounts/<account-id>/verification?viewId=0' \\ 
 -u ‘[auth_token]:’
```

```
{ 
"result": { 
"id": "11111111", 
"vendorAccountName": "11111111", 
"vendorAccountId": "11111111", 
"vendorKey": "azure", 
"verification": { 
"state": "error", 
"message": "Azure EA account cannot be verified because of below reasons:\n1. AZURE_ENROLLMENT_READER(billing:EnrollmentReader) role has not been assigned to Cloudability's Service Principal\n2. Azure EA API access key is Absent/Invalid/Expired\n3. All the Blob Storage related parameters are not provided/Invalid\nOne of the above mentioned reasons should be addressed.", 
"lastVerificationAttemptedAt": "2025-12-17T09:48:07Z" 
}, 
"authorization": { 
"type": "azure_enrollment", 
"enrollmentId": "11111111", 
"tenantId": "11a1a111-1111-1111-1111-11aa11111a11", 
"subscriptionGuid": "aaa111aa1-aa11-11a1-1aa1-aa11a1a1aaaa", 
"resourceGroupName": "costexport", 
"storageAccountName": "test", 
"containerName": "test", 
"directoryName": "test", 
"exportNameCost": "test", 
"exportNameAmortized": "test", 
"tenancyId": "11a1a111-1111-1111-1111-11aa11111a11" 
}, 
"additionalData": {}, 
"createdAt": "2024-01-31T12:20:03Z", 
"consumerOrgId": "" 
} 
}
```

```
curl -X POST 'https://api-s.cloudability.com/v3/vendors/azure/accounts/<account-id>/archive?viewId=0' \\ 
 -u ‘[auth_token]:’
```

```
{ 
"result": { 
"id": "11111111", 
"vendorAccountName": "11111111", 
"vendorAccountId": "11111111", 
"vendorKey": "azure", 
"verification": { 
"state": "archived" 
}, 
"meta": {}, 
"consumerOrgId": "" 
} 
}
```

```
curl -X DELETE 'https://api.cloudability.com/v3/vendors/azure/accounts/[account-id]?viewId=0' \\ 
 -u ‘[auth_token]:’ 
```

```
{ 
"result": { 
"message": "Successfully deleted", 
"vendorKey": "azure", 
"vendorAccountId": "11111111" 
} 
}
```
