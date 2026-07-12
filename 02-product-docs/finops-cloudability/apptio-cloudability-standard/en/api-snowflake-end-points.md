---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Snowflake End Points"
breadcrumb:
  - "Cloudability API"
  - "Snowflake End Points"
source_path: "SSVCLNQ/api-v3/snowflake_public_api.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Snowflake End Points

Summary

These end points are used to manage credentials within Cloudability that support the integration and ingestion of Snowflake data.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/snowflake/accounts for RESTful CRUD interactions

end point : /v3/vendors/snowflake/accounts?include=permissions&viewId=0

end point : /v3/vendors/snowflake/accounts/<account_id>?include=permissions&viewId=0

end point : /v3/vendors/snowflake/accounts/<account_id>?viewId=0

end point : /v3/vendors/snowflake/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0

end point : /v3/vendors/snowflake/accounts/<account_id>/terraform-template

end point : /v3/vendors/snowflake/accounts/<account_id>/archive?viewId=0

end point : /v3/vendors/snowflake/permissions/accounts/<account_id>

Parameters

- vendorAccountID (string) - account id of snowflake
- type (string) - “snowflake_user”
- accountName (string) - account name
- warehouseName (string) - snowflake warehouse name
- databaseName (string) - database name
- userName (string) - snowflake user name
- orgName (string) - org name
- subscriptionModel (string) - “Direct” | “Marketplace”
- dependentCsp (string) - “AWS” | “AZURE” | “GCP”, should be passed only when subscriptionModel is set to “Marketplace”

List Accounts

Example Request

```
curl 'https://api.cloudability.com/v3/vendors/snowflake/accounts?viewId=0' \\ 
   -u ‘[auth_token]:’ 
```

```
{ 
"result": [ 
{ 
"id": "account-id-1", 
"vendorAccountName": "account-name", 
"vendorAccountId": "account-id-1", 
"vendorKey": "snowflake", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2026-02-07T05:14:13Z" 
}, 
"authorization": { 
"type": "snowflake_user", 
"permissions": [ 
"snowflake.get.costReports", 
"snowflake.get.warehouse.cost", 
"snowflake.list.accounts" 
], 
"subscriptionModel": "Marketplace", 
"dependentCsp": "AWS", 
"orgName": "Org_Name", 
"accountName": "AAA11111", 
"warehouseName": "CLDY_CANVAS_WNAME", 
"databaseName": "CLDY_CANVAS_DB_NAME", 
"userName": "CLDY_CANVAS_USER_NAME" 
}, 
"createdAt": "2025-12-10T09:39:08Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
}, 
{ 
"id": "BA11111", 
"vendorAccountName": "CPROD_IN", 
"vendorAccountId": "BA11111", 
"vendorKey": "snowflake", 
"meta": {}, 
"parentAccountId": "account-id-1", 
"consumerOrgId": "" 
} 
] 
}  
```

Create Master Payer account

POST /v3/vendors/snowflake/accounts?viewId=0

This API is used for creating a new Snowflake credential

Example Request

```
curl -X POST 'https://api.cloudability.com/v3/vendors/snowflake/accounts?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
"type": "snowflake_user", 
"accountName": "Account_Name", 
"warehouseName": "Warehous_Name", 
"databaseName": "DB_Name", 
"userName": "User_Name", 
"orgName": "Org_Name", 
"subscriptionModel": "Marketplace", 
"dependentCsp": "AZURE" 
}        
```

Upon successful creation the API will return the credentials object.

Update Master Payer account

PUT /v3/vendors/snowflake/accounts/<account_id>?include=permissions&viewId=0

```
curl -X PUT 'https://api.cloudability.com/v3/vendors/snowflake/accounts/<account_id>?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
"type": "snowflake_user", 
"accountName": "AAA11111", 
"warehouseName": "CLDY_CANVAS_WNAME", 
"databaseName": "CLDY_CANVAS_DB_NAME", 
"userName": "CLDY_CANVAS_USER_NAME", 
"orgName": "ORG_NAME", 
"subscriptionModel": "Marketplace", 
"dependentCsp": "AWS" 
} 
```

Retrieve Account

GET /v3/vendors/snowflake/accounts/<account_id>?viewId=0

Example Request

```
curl 
'https://api.cloudability.com/v3/vendors/snowflake/accounts/<account_id>’\\ 
-u ‘[auth_token]:’
```

Delete Credential for Account

DELETE /v3/vendors/snowflake/accounts/<account_id>?viewId=0

Example Request

```
Curl -X DELETE 
'https://api.cloudability.com/v3/vendors/snowflake/accounts/<account_id>?viewId=0\\ 
-u ‘[auth_token]:’ 
```

Verify Credential for Account

POST v3/vendors/snowflake/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0

```
curl --X POST 
'https://api.cloudability.com/v3/vendors/snowflake/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0’\\ 
-u ‘[auth_token]:’ 
```

Get setup script for Account

GET /v3/vendors/snowflake/accounts/<account_id>/setup-scripts

Example Request

```
curl 
'https://api.cloudability.com/v3/vendors/snowflake/accounts/<account-id>/setup-scripts?viewId=0 
-u ‘[auth_token]:’ 
```

Archive Account

POST /v3/vendors/snowflake/accounts/<account_id>/archive?viewId=0

Example Request

```
curl --X POST 
'https://api.cloudability.com/v3/vendors/snowflake/accounts/<account_id>archive?viewId=0’\\ 
-u ‘[auth_token]:’ 
```

Get Permissions for Account

GET /v3/vendors/snowflake/permissions/accounts/<account_id>\

Example Request

```
curl --X GET 
'https://api.cloudability.com/v3/vendors/snowflake/permissions/accounts/<account_id>’ 
\\ 
-u ‘[auth_token]:’ 
```
