---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "MongoDB End Points"
breadcrumb:
  - "Cloudability API"
  - "MongoDB End Points"
source_path: "SSVCLNQ/api-v3/mongodb_public_api.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# MongoDB End Points

Summary

Following are the list of public APIs provided by Kissinger service specific to MongoDb.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/mongodb/accounts for RESTful CRUD interactions

end point : /v3/vendors/mongodb/accounts?include=permissions&viewId=0

end point : /v3/vendors/mongodb/accounts/<account_id>?include=permissions&viewId=0

end point : /v3/vendors/mongodb/accounts/<account_id>?viewId=0

end point : /v3/vendors/mongodb/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0

end point : /v3/vendors/mongodb/accounts/<account_id>/archive?viewId=0

end point : /v3/vendors/mongodb/permissions/accounts/<account_id>

Parameters

- type(string) : "mongodb_user",
- vendorAccountId(string) : account id,
- publicKey(string) : public key,
- privateKey(string) : Private key,
- subscriptionModel(string) - “Direct” | “Marketplace”
- dependentCsp(string) - “AWS” | “AZURE” | “GCP”, should be passed only when subscriptionModel is set to “Marketplace”

End Points

```
curl 'https://api.cloudability.com/v3/vendors/mongodb/accounts?viewId=0' \\ 
   -u ‘[auth_token]:’ 
```

```
{ 
"result": [ 
{ 
"id": "111e11111e111111aa1111a1", 
"vendorAccountName": "111e11111e111111aa1111a1", 
"vendorAccountId": "111e11111e111111aa1111a1", 
"vendorKey": "mongodb", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2026-02-07T06:14:10Z" 
}, 
"authorization": { 
"type": "mongodb_user", 
"permissions": [ 
"mongodb.list.organization", 
"mongodb.get.invoices" 
], 
"subscriptionModel": "Marketplace", 
"dependentCsp": "AWS" 
}, 
"createdAt": "2024-07-18T06:15:53Z", 
"consumerOrgId": "", 
"byodVendor": "ABSENT" 
}, 
{ 
"id": "222222f222b2ed2ccf2222aa", 
"vendorAccountName": "222222f222b2ed2ccf2222aa", 
"vendorAccountId": "222222f222b2ed2ccf2222aa", 
"vendorKey": "mongodb", 
"meta": {}, 
"parentAccountId": "111e11111e111111aa1111a1", 
"consumerOrgId": "" 
} 
] 
} 
```

Create Master Payer Account - This API is used for creating a new Master Payer account.

POST /v3/vendors/mongodb/accounts?viewId=0

Example Request

```
curl -X POST 'https://api.cloudability.com/v3/vendors/mongodb/accounts?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
 "type": "mongodb_user", 
 "vendorAccountId": "org-id", 
 "publicKey": "public-key", 
 "privateKey": "private-api-key", 
 "subscriptionModel": "Marketplace", 
 "dependentCsp": "AZURE" 
}              
```

Upon successful creation the API will return the credentials object.

Update Master Payer account

PUT /v3/vendors/mongodb/accounts/<account_id>?include=permissions&viewId=0

Example Request

```
curl -X PUT 'https://api.cloudability.com/v3/vendors/mongodb/accounts/<account_id>?viewId=0\\ 
-H 'Content-Type: application/json' \\ 
-u ‘[auth_token]:’ \\ 
-d @- << EOF 
{ 
"type": "mongodb_user", 
"vendorAccountId": "org-id", 
"publicKey": "new", 
"privateKey": "new", 
"subscriptionModel": "Marketplace", 
"dependentCsp": "AZURE" 
} 
```

Upon successful update the API will return the credentials object

Retrieve Account

GET /v3/vendors/mongodb/accounts/:<account_id>?viewId=0

Example Request

```
curl 
'https://api.cloudability.com/v3/vendors/mongodb/accounts/<account_id>’\\ 
-u ‘[auth_token]:’ 
```

Upon successful get, the API will return the credentials object

Delete Credential for Account

DELETE /v3/vendors/mongodb/accounts/<account_id>?viewId=0

```
Curl -X DELETE 
'https://api.cloudability.com/v3/vendors/mongodb/accounts/<account_id>?viewId=0\\ 
-u ‘[auth_token]:’ 
```

Verify Credential for Account

POST v3/vendors/mongodb/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0

Example Request

```
curl --X POST 
'https://api.cloudability.com/v3/vendors/mongodb/accounts/<account_id>/verification?include=permissions,associatedAccounts&viewId=0’\\ 
-u ‘[auth_token]:’ 
```

Upon successful verification the API will return the credentials object

Archive Account

POST /v3/vendors/mongodb/accounts/<account_id>/archive?viewId=0

```
curl --X POST 
'https://api.cloudability.com/v3/vendors/mongodb/accounts/<account_id>archive?viewId=0’\\ 
-u ‘[auth_token]:’ 
```

Get Permissions for Account

GET /v3/vendors/mongodb/permissions/accounts/<account_id>

Example Request

```
curl --X GET 
'https://api.cloudability.com/v3/vendors/mongodb/permissions/accounts/<account_id>’ 
\\ 
-u ‘[auth_token]:’
```
