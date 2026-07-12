---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Vendor Credentials End Points (GCP)"
breadcrumb:
  - "Cloudability API"
  - "Vendor Credentials End Points (GCP)"
source_path: "SSVCLNQ/api-v3/gcp-vendor-credential-end-points.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Vendor Credentials End Points (GCP)

Summary

This end point is used to manage GCP within Cloudability that support the creation, updation and deletion of GCP credentials.

This end point does not support filtering and sorting.

With Cloudability being available in multiple regions, all references to api.cloudability.com in this API documentation should be referred to as mentioned in Getting started with Cloudability API V3 .

End Point Particulars

end point : /v3/vendors/gcp/accounts

end point : /v3/vendors/gcp/accounts/[account_id]?viewId=0

end point : /v3/vendors/gcp/accounts/[account_id]/setup-scripts

end point : /v3/vendors/gcp/permissions/accounts/[account_id]

end point : /v3/vendors/gcp/accounts/[account_id]/verification

end point : /v3/vendors/gcp/accounts/[account_id]/archive

The Credential Object

tableFqn (string) - combination of project-id:dataset_id.gcp_billing_export (project-id:dataset_id.gcp_billing_export_v1_11F1AC_1111A1_11CA11)

gcpOrgId (string) - the gcp organizationId (needs to be provided if gcp automation is used)

consumerOrgId (string) - if the account belongs to msp_consumer, this is the orgId of MSP_CONSUMER (optional, needs to be provided only if it belongs to MSP)

rlbdate (string) - resource label billing date (optional- required in case of GCP Detailed Billing)

isResourceLevelBillingRequired (boolean)) - it can have true/false (optional- required in case of GCP Detailed Billing)

vendorAccountName (string) - GCP vendor Account ID of customers

vendorKey (string) - states the vendor type (GCP)

verification (string) -contains state of the account

state (string) -it specifies whether the account is in verified/unverified/error state

authorization (string) - contains the below details:

type (string) - the provider type

tableName (string) - billing export table name

projectId (string) - billing export project Id

datasetId (string) - billing export dataset Id

bucketName (string) - the gcp bucket name (optional- required in case of GCP Detailed Billing/GCS)

permissions (string) - contains all permission present in a given GCP account after verification

createdAt ( string) - the timestamp at which the account is credentialized

script (string) - the script required to setup GCP role in customer's account

```
curl 'https://api.cloudability.com/v3/vendors/gcp/accounts?viewId=0' \\ 
 -u ‘[auth_token]:’ 
```

```
{ 
"result": [ 
{ 
"id": "111A11-11A1AA-1A1111", 
"vendorAccountName": "111A11-11A1AA-1A1111", 
"vendorAccountId": "111A11-11A1AA-1A1111", 
"vendorKey": "gcp", 
"verification": { 
"state": "verified", 
"lastVerificationAttemptedAt": "2025-12-16T05:22:18Z" 
}, 
"authorization": { 
"type": "gcp_role", 
"permissions": [ 
"bigquery.jobs.create", 
"compute.commitments.list", 
"compute.instances.list", 
"bigquery.tables.getData", 
"compute.disks.list", 
"monitoring.timeSeries.list" 
], 
"tableName": "gcp_billing_export_v1_111A11_11A1AA_1A1111", 
"projectId": "final-best-project", 
"datasetId": "Standard_billing", 
"turboExecutionEnabled": false 
}, 
"createdAt": "2023-09-20T16:50:44Z", 
"consumerOrgId": "" 
}, 
] 
}
```

Create GCP credential for Standard Billing account

```
curl --location 'https://api.cloudability.com/v3/vendors/gcp/accounts' \
     --header 'Content-Type: application/json' \
     --data '{
	       "type": "gcp_role",
	       "tableFqn": "samplestandard:sample.gcp_billing_export_v1_11A1DD-D1F1E1-K11111",
	       "gcpOrgId": "",
	       "consumerOrgId": "",
	       "rlbdate": "",
	       "bucketName": "test1",
	       "isResourceLevelBillingRequired": false
				}'
```

```
{
 "result": {
	     "id": "1A1DD-D1F1E1-K11111",
	     "vendorAccountName": "1A1DD-D1F1E1-K11111",
	     "vendorAccountId": "1A1DD-D1F1E1-K11111",
	     "vendorKey": "gcp",
	     "verification": {
	     "state": "unverified"
			     },
	     "authorization": {
				"type": "gcp_role",
				"bucketName": "test1",
				"tableName": "gcp_billing_export_v1_1A1DD-D1F1E1-K11111",
				"projectId": "samplestandard",
				"datasetId": "sample"
				},
				"createdAt": "2023-12-27T11:37:50Z",
				"consumerOrgId": ""
				}
				}
```

```
ccurl --location 'https://api.cloudability.com/v3/vendors/gcp/accounts' \ 
     --header 'Content-Type: application/json' \ 
     --data ' { 
    "type": "gcp_role", 
    "tableFqn": "test12:billing_gcp12.gcp_billing_export_resource_v1_11A111_A11A1A_1A11A1", 
    "gcpOrgId": "", 
    "consumerOrgId": "", 
    "rlbdate": "2024-12", 
    "bucketName": "testBucket", 
    "isResourceLevelBillingRequired": true, 
    "turboExecutionEnabled": false 
}' 
```

Upon successful creation the API will return the credentials object.

```
curl -X POST 'https://api.cloudability.com/v3/vendors/gcp/accounts' \\ 
 -H 'Content-Type: application/json' \\ 
 -u ‘[auth_token]:’ \\ 
 -d @- << EOF 
{ 
"type": "gcp_role", 
"projectId": "final-best-project" 
} 
```

Upon successful creation the API will return the credentials object.

Update the GCP credential with the given ID

```
curl --location 'https://api.cloudability.com/v3/vendors/gcp/accounts/01A4DD-D4F7E3-F19690?viewId=0' \
	 --header 'Content-Type: application/json' \
	 --data '{
		  "vendorAccountId": "01A1DD-D1F1E1-F11111",
		  "type": "gcp_role",
		  "tableFqn": "samplestandard:sample.gcp_billing_export_v1_01A1DD-D1F1E1-F11111",
		  "consumerOrgId": "",
		  "bucketName": "sampleData",
		  "isResourceLevelBillingRequired": false,
		  "rlbdate": "",
		  "gcpOrgId": ""
				}'
```

```
{
 "result": {
 "id": "01A1DD-D1F1E1-F11111",
 "vendorAccountName": "01A1DD-D1F1E1-F11111",
 "vendorAccountId": "01A1DD-D1F1E1-F11111",
 "vendorKey": "gcp",
 "verification": {
		   "state": "unverified"
		  },
 "authorization": {
		    "type": "gcp_role",
		    "bucketName": "sampleData",
		    "tableName": "gcp_billing_export_v1_01A1DD-D1F1E1-F11111",
		    "projectId": "samplestandard",
		    "datasetId": "sample"
		   },
		    "createdAt": "2023-12-20T01:15:23Z",
		    "consumerOrgId": ""
		   }
		   }
```

```
curl 'https://api.cloudability.com/v3/vendors/gcp/accounts/[account-id]/setup-scripts?viewId=0' \\ 
 -u ‘[auth_token]:’
```

```
{
 "result": {
	     "scripts": "gcloud iam roles create CloudabilityRole_Billing \\\n --project \\\n samplestandard \\\n --title \\\n \"Cloudability Billing Role\" \\\n --description \\\n \"Allows Cloudability access to billing account data\" \\\n --permissions \\\n bigquery.jobs.create,bigquery.tables.getData,bigquery.tables.export,storage.buckets.get,storage.buckets.getIamPolicy,storage.multipartUploads.abort,storage.multipartUploads.create,storage.multipartUploads.list,storage.multipartUploads.listParts,storage.objects.create,storage.objects.delete,storage.objects.get,storage.objects.list,storage.objects.update \\\n --stage=GA \ngsutil iam ch serviceAccount:billing-data-service-acct@cloudability-credentials.iam.gserviceaccount.com:projects/samplestandard/roles/CloudabilityRole_Billing gs://sampleData\ngcloud projects add-iam-policy-binding samplestandard \\\n --member serviceAccount:billing-data-service-acct@cloudability-credentials.iam.gserviceaccount.com \\\n --role 'projects/samplestandard/roles/CloudabilityRole_Billing'"
	    }
	    }
}
```

Verifies GCP Credential with a given ID

```
when verification fails

{
 "result": {
 "id": "11A1DD-D1F1E1-K11111",
 "vendorAccountName": "11A1DD-D1F1E1-K11111",
 "vendorAccountId": "11A1DD-D1F1E1-K11111",
 "vendorKey": "gcp",
 "verification": {
 "state": "error",
 "message": "The Cloudability role or service account key does not have IAM role(s) with sufficient permissions assigned to it. Please ensure that the role or service account has the following permissions: [bigquery.jobs.create, bigquery.tables.getData, bigquery.tables.export, storage.buckets.get, storage.buckets.getIamPolicy, storage.multipartUploads.abort, storage.multipartUploads.create, storage.multipartUploads.list, storage.multipartUploads.listParts, storage.objects.create, storage.objects.delete, storage.objects.get, storage.objects.list, storage.objects.update]",
 "lastVerificationAttemptedAt": "2023-12-27T11:42:25Z"
 },
  "authorization": {
  "type": "gcp_role",
  "bucketName": "test1",
  "tableName": "gcp_billing_export_v1_11A1DD-D1F1E1-K11111",
  "projectId": "samplestandard",
  "datasetId": "sample"
},
  "createdAt": "2023-12-27T11:37:50Z",
 "consumerOrgId": ""
}
}





when verification succeeds

{
  "result": {
  "id": "11F1AC-1111A1-11CA11",
  "vendorAccountName": "11F1AC-1111A1-11CA11",
  "vendorAccountId": "11F1AC-1111A1-11CA11",
  "vendorKey": "gcp",
  "verification": {
  "state": "verified",
  "lastVerificationAttemptedAt": "2023-12-27T11:53:25Z"
  },
  "authorization": {
  "type": "gcp_role",
  "permissions": [
  "bigquery.tables.getData",
  "consumerprocurement.orders.get",
  "consumerprocurement.orders.list",
  "bigquery.jobs.create"
                 ],
		   "tableName": "gcp_billing_export_v1_11F1AC-1111A1-11CA11",
		   "projectId": "cldy-billing-data",
		   "datasetId": "cloudability_billing_gcp"
		   },
		   "createdAt": "2020-04-23T16:42:42Z",
		   "consumerOrgId": ""
		   }
}
```

```
curl -X POST 'https://api.cloudability.com/v3/vendors/gcp/accounts/[account-id]/archive?viewId=0' \\ 
    -u ‘[auth_token]:’ 
```

```
{
 "result": {
	     "id": "11A1DD-D1F1E1-K11111",
	     "vendorAccountName": "11A1DD-D1F1E1-K11111",
	     "vendorAccountId": "11A1DD-D1F1E1-K11111",
	     "vendorKey": "gcp",
	     "verification": {
	     "state": "archived"
	    },
	     "meta": {},
	     "consumerOrgId": ""
	    }
}
```

```
curl -X DELETE 'https://api.cloudability.com/v3/vendors/gcp/accounts/[account-id]?viewId=0' \\ 
    -u ‘[auth_token]:’
```

```
{
 "result": {
	     "message": "Successfully deleted",
	     "vendorKey": "gcp",
	     "vendorAccountId": "11A1DD-D1F1E1-K11111"
	     }
}
```
