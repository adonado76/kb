---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Vendor Credentials End Points (IBM)"
breadcrumb:
  - "Cloudability API"
  - "Vendor Credentials End Points (IBM)"
source_path: "SSVCLNQ/api-v3/vendor_credentials_end_points_ibm.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Vendor Credentials End Points (IBM)

Summary

This end point is used to manage credentials within Cloudability that support the integration and ingestion of data from public cloud vendors. This includes tasks such as initial setup, listing out current credentials and deleting deprecated credentials. This end point does not support filtering and sorting.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/ibm/accounts for RESTful CRUD interactions

end point : /v3/vendors/ibm/accounts?viewId=0

end point : /v3/vendors/ibm/accounts/<account_id>?include=permissions&viewId=0

end point : /v3/vendors/ibm/accounts/<account_id>

end point : /v3/vendors/ibm/accounts/<account_id>?viewId=0

end point : / v3/vendors/ibm/accounts/<account_id>/verification? include=permissions,associatedAccounts&viewId=0

end point : /v3/vendors/ibm/accounts/<account_id>/terraform-template

end point : /v3/vendors/ibm/accounts/<account_id>/archive?viewId=0

end point : /v3/vendors/ibm/permissions/accounts/<account_id>

end point : /v3/vendors/ibm/accounts?include=permissions&viewId=0

Parameters

- vendorAccountID (string) - account id of IBM cloud
- region (string) - region of the account
- enterpriseID (string) - enterprise id of the IBM account
- IbmCostReportSpec:
- costReportName - manifest file name costPrefix - path of the manifest file bucketName (string) - name of the bucket present in the IBM account bucketRegion - region of bucket present in IBM account storageInstantName - instance name of storage

To ensure the API returns all accounts with these credential requests, add viewId=0 as a URL parameter. This will ensure any default view on your user account isn't applied.

List Accounts

Example Request

```
curl 'https://api.cloudability.com/v3/vendors/ibm/accounts?viewId=0' \\ 
   -u ‘[auth_token]:’ 
```

Example Request

```

{ 
"result": [ 
{ 
"id": "1111aaa11aaa1a1a111111111a11aa11", 
"vendorAccountName": "Master account", 
"vendorAccountId": "1111aaa11aaa1a1a111111111a11aa11", 
"vendorKey": "ibm", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2026-02-04T11:14:11Z" 
}, 
"authorization": { 
"type": "ibm_role", 
"permissions": [ 
"ibm.list.accounts", 
"ibm.get.objects" 
], 
"bucketName": "apptio-cloud-integration-billing-data", 
"costAndUsageReport": { 
"name": "manifest", 
"prefix": "IBMCloud-Billing-Reports" 
}, 
"region": "us-east", 
"storageInstanceName": "Cloud Object Storage-apptio", 
"bucketRegion": "us-east", 
"enterpriseId": "3333aaa33aaa3a3a233333333a33aa22" 
}, 
"createdAt": "2025-12-13T09:09:48Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
}, 
{ 
"id": "2222aaa22aaa2a2a222222222a22aa22", 
"vendorAccountName": "Child account", 
"vendorAccountId": "2222aaa22aaa2a2a222222222a22aa22", 
"vendorKey": "ibm", 
"meta": {}, 
"parentAccountId": "1111aaa11aaa1a1a111111111a11aa11", 
"consumerOrgId": "" 
} 
] 
} 
```

Create Master Payer

```
POST /v3/vendors/ibm/accounts?viewId=0
```

Example Request

```
curl -X POST 'https://api.cloudability.com/v3/vendors/ibm/accounts?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 

{ 
   "vendorAccountId": "1234567", 
   "region": "us-east", 
   "enterpriseId": "6dd1xxxx109xxxx1be976xxxxd6d62df", 
   "ibmCostReportSpec": { 
   	"bucketName": "daily-cost-exports-enterprise", 
   	"bucketRegion": "us-east", 
       "storageInstanceName": "Cloud Object Storage-InEnterpriseAccount", 
       "costReportName": "manifest", 
       "costPrefix": "IBMCloud-Billing-Reports" 
}, 
      "type": "ibm_role" 
} 
```

Upon successful creation the API will return the credentials object.

Update Master Payer

PUT /v3/vendors/ibm/accounts/<account_id>?include=permissions&viewId=0

Example Request

```
curl -X PUT 'https://api.cloudability.com/v3/vendors/ibm/accounts/<account_id>?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 

{ 
   "vendorAccountId": "1234567", 
   "region": "us-east", 
   "enterpriseId": "6dd1xxxx109xxxx1be976xxxxd6d62df", 
   "ibmCostReportSpec": { 
   	"bucketName": "daily-cost-exports-enterprise", 
   	"bucketRegion": "us-east", 
       "storageInstanceName": "Cloud Object Storage-InEnterpriseAccount", 
       "costReportName": "manifest", 
       "costPrefix": "IBMCloud-Billing-Reports" 
}, 
      "type": "ibm_role" 
}  
```

Retrieve Account

```
GET /v3/vendors/ibm/accounts/<account_id>?viewId=0
```

Example Request

```
curl 
'https://api.cloudability.com/v3/vendors/ibm/accounts/<account_id>’\\ 
-u ‘[auth_token]:’ 
```

Delete Credential for Account

```
DELETE /v3/vendors/ibm/accounts/<account_id>?viewId=0
```

Example Request

```
curl 
'https://api.cloudability.com/v3/vendors/ibm/accounts/<account_id>?viewId=0\\ 
-u ‘[auth_token]:’  
```

Verify Credential for Account

```
POST v3/vendors/ibm/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0
```

Example Request

```
curl --X POST
'https://api.cloudability.com/v3/vendors/ibm/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0’\\
-u ‘[auth_token]:’
```

Get Terraform Template for Account

```
GET /v3/vendors/ibm/accounts/<account_id>/terraform-template
```

Example Request

```
 curl
'https://api.cloudability.com/v3/vendors/ibm/<account_id>/terraform-template’\\
-u ‘[auth_token]:’ 
```

Archive Account

```
POST /v3/vendors/ibm/accounts/<account_id>/archive?viewId=0
```

Example Request

```
 curl --X POST
'https://api.cloudability.com/v3/vendors/ibm/accounts/<account_id>archive?viewId=0’\\
-u ‘[auth_token]:’
```

Get Permissions for Account

```
GET /v3/vendors/ibm/permissions/accounts/<account_id>
```

Example Request

```
 curl --X GET
'https://api.cloudability.com/v3/vendors/ibm/permissions/accounts/<account_id>’
\\
-u ‘[auth_token]:’ 	
```
