---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cloudability Workload Planning  API End Points"
breadcrumb:
  - "Cloudability API"
  - "Cloudability Workload Planning  API End Points"
source_path: "SSVCLNQ/api-v3/workload-planning-api-endpoints.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cloudability Workload Planning API End Points

Workload Planning API end points can be used to create, manage your workloads, add resources and update Workload Planning Preferences.

If you wish to see the allowed values when importing multiple resources via JSON file, refer to Uploading multiple resources for a given workload.

Use Cases

1. Creating a workload
1. Uploading multiple resources for a given workload
1. Generating a recommendation and saving a recommendation
1. Exporting workload to csv
1. Duplicating workload
1. Deleting workload

Creating a workload and getting a workload ID

You will need to define your workload preferences and common information as a start.

Once validated, you will get the workload ID that will be required as a parameter for the next APIs.

```
curl -X 'POST' \ 'https://api.cloudability.com/v3/workload' \
-u '<Token Generated>' \
-H 'Content-Type: application/json' \
-d @- << EOF
		
```

```
{
  "name": "test workload",
  "description": "test desc",
  "group": "test_group",
  "csp": [
    {
      "vendor": "OCI",
      "region": "ap-melbourne-1,ap-sydney-1,ca-montreal-1,sa-saopaulo-1,sa-vinhedo-1",
      "leaseType": "ONDEMAND",
      "discountEnabled": false,
      "upliftEnabled": false,
      "discountDesc": "",
      "discountPercent": 0
    },
    {
      "vendor": "GCP",
      "region": "asia-east1,asia-east2,asia-northeast1,asia-northeast2,asia-northeast3",
      "leaseType": "SPOT",
      "commitmentTerm": "3 YEAR",
      "paymentOptions": "NO UPFRONT",
      "discountEnabled": false,
      "upliftEnabled": false,
      "discountDesc": "",
      "discountPercent": 0,
      "sudEnabled": true
    },
    {
      "vendor": "AZURE",
      "region": "asia-pacific-east,asia-pacific-southeast,australia-central,australia-central-2",
      "leaseType": "COMMITTED",
      "computeOffering": "RESERVED_INSTANCES",
      "commitmentTerm": "1 YEAR",
      "paymentOptions": "FULL UPFRONT",
      "discountEnabled": false,
      "upliftEnabled": false,
      "discountDesc": "",
      "discountPercent": 0
    },
    {
      "vendor": "AWS",
      "region": "ap-northeast-1,eu-west-1,us-east-1,us-west-2",
      "leaseType": "ONDEMAND",
      "computeOffering": "EC2",
      "commitmentTerm": "1 YEAR",
      "paymentOptions": "PARTIAL UPFRONT",
      "discountEnabled": false,
      "upliftEnabled": false,
      "discountDesc": "",
      "discountPercent": 0
    }
  ],
  "status": "IN_PROGRESS"
}
```

Response Object

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "description" | No | string |
| "group" | No | ( not used currently ) |
| "vendor" | Yes | string allowed values: "AWS", "Azure", "GCP", "OCI" |
| "region" | Yes | string Please note that you can use the API below to get the list of the available regions: curl-X'GET'\ 'https://api.cloudability.com/v3/workload/static-data' \ -u '<Token Generated>' |
| "leaseType" | Yes | string allowed values for AWS, GCP, AZURE: "COMMITTED", "ONDEMAND", "SPOT" Allowed values for OCI: "ONDEMAND", "CAPACITY_RESERVATION", "SPOT" |
| "computeOffering" | Yes | string allowed values for AWS: "COMPUTE", "EC2", "STANDARD_RI", CONVERTIBLE _RI" allowed values for Azure: "RESERVED_INSTANCES", "COMPUTE" Please note that for Azure, "COMPUTE" is currently used for Savings Plan. This value will be updated soon. |
| "CommitmentTerm" | Yes | string allowed values: "1 YEAR", "3 YEAR" |
| paymentOptions | Yes | String allowed values for AWS: "NO UPFRONT", "ALL UPFRONT", "PARTIAL UPFRONT" allowed values for AZURE: "NO UPFRONT", "ALL UPFRONT" allowed value for GCP: "NO UPFRONT" |
| "subEnabled" | Yes | boolean This field corresponds to Sustained Use Discount for GCP - the true value means that GCP costs will get SUD applied. It is not used for AWS and Azure. |
| "status" | Yes | string allowed values: "IN_PROGRESS,IN_REVIEW,APPROVED,READY_FOR_REVIEW" |
| "preferredCsp" | Yes | string allowed values: Any CSP from the vendor selected This field determines which could provider is your preferred one in case of multi-cloud comparison and it can be updated later. |

Uploading multiple resources for a given workload

We currently support both JSON and XLSX format to upload multiple resources / requirements for your workload.

A. Download an example of file (template) or the list of existing resources

Example Request

```
curl -X 'GET' \
'https://api.cloudability.com/v3/workload/{download-type}/{format}/export/{workload-id}' \
-H 'accept: application/hal+json' \
-u '<Token Generated>'
```

| Key | Required | Description |
| --- | --- | --- |
| Workload-ID | Yes | string - should be in uuid format |
| Download-type | Yes | string allowed values: “template” (if you want a JSON or XLSX file example) or “resources” (if you want to get the list of existing resources in your workload) |
| format | Yes | string allowed values: "json" or "xlsx" |

B. Description of required keys for each service type while adding resources in the JSON or XLSX file

Virtual Machine

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "cpu" | Yes | integer |
| "ram" | Yes | integer - amount of memory (GB) |
| "gpuCount" | No | integer |
| "os":"string", | Yes | string allowed values: "Windows", "Linux", |
| "cspOverride":{ "vendor":"string", "region":"string", "regionType":"string" | No | If don't want to use it, you can have an empty or null value. If you find the list of VM resources using the GET API below. For url param: use the vendor name and the region. curl -X POST 'https://api.cloudability.com/v3/internal/virtual-machine/instance' \ --header 'Authorization: <Token Generated>'' \ --header 'Content-Type: application/json' \ --data '{"vendor":"<vendor>","region":"<region>"}' |
| "localStorage" | No | integer |
| "tenancy" | Yes | string allowed values: "SHARED", "DEDICATED" |
| "networkGb" | Yes | integer |
| "upTime" | Yes | integer |
| "quantity" | Yes | Integer - number of VMs |
| "byol" | Yes | boolean allowed values: "true", "false" |
| "deplyomentOption" | Yes | string allowed values: "SINGLE-AZ", "MULTI-AZ" It is only used for AWS, but the value needs to be provided for |
| " blockStorage " { "name": "string", "storageType": " integer", "storageGb": " integer", "iops": " integer", "throughput": " integer", "snapshotGb": " integer", "quantity": " integer" } } | No | Allowed values for storage type: “SSD” or “HDD” Note: Block storage needs to have a name provided The quantity should be the same as the number of VMs (VM quantity) |
| "cspOverride": { "vendor": "string", "region": "string", "resourceType": "string" | No | If don't want to use it, you can have an empty or null value. You can find the list of instances using the GET API below. For url param: use "block" and the vendor name curl -X 'GET' \ 'https://api.cloudability.com/v3/workload/storage/instance/{vendor}?serviceType=block' \ -u '<Token Generated>' |

Managed Database

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "cpu" | Yes | integer |
| "ram" | Yes | integer |
| "license" | Yes | string allowed values: "MySQL", "PostgreSQL", "SqlServer" |
| "cspOverride": { "vendor": "string", "region": "string", "resourceType": "string | No | If don't want to use it, you can have an empty or null value. You can find the list of database resources using the GET API below. For url param: use the vendor name and the region. curl -X POST 'https://api.cloudability.com/v3/internal/managed-database/instance' \ --header 'Authorization: <Token Generated>'' \ --header 'Content-Type: application/json' \ --data '{"vendor":"<vendor>","region":"<region>"}' |
| "localStorage" | No | integer |
| "tenancy" | Yes | string This field is not used. |
| "networkGb" | No | integer |
| "upTime" | Yes | integer |
| "quantity" | Yes | Integer |
| "byol" | Yes | boolean Default value is "false" |
| "deploymentOption" | Yes | string allowed values: "SINGLE-AZ", "MULTI-AZ" It is only used for AWS, but the value needs to be provided for every vendor. |
| "storageType": " integer", "storageGb": " integer", "iops": " integer", "throughput": " integer", "snapshotGb": " integer", "quantity": " integer", "cspOverride": { "vendor": "", "region": "", "resourceType": "" } } | No | Block storage is optional and the attributes below are only mandatory if you wish to attach block storage to your Database. Allowed values for storage type: “SSD” or “HDD” Note: Block storage needs to have a name provided The quantity should be the same as the number of Managed Database (Managed Database Quantity) “SnapshotGb” corresponds to “Backup Storage” and will be updated soon |

Additional Storage

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "storageType" | Yes | string allowed values: "SSD" or "HDD" |
| "storageGb" | Yes | integer |
| "quantity" | Yes | integer |
| "iops" | No | integer |
| "throughput" | No | integer |
| "snapshotGb" | No | integer |
| "cspOverride": { "vendor": "string", "region": "string" "resourceType": "string" | No | You can find the list of instances using the GET API below. For url param: use "block" and the vendor name. curl -X 'GET' \ 'https://api.cloudability.com/v3/workload/storage/instance/{vendor}?serviceType=block' \ -u '<Token Generated>' |

Object Storage

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "storageGb" | Yes | integer |
| "quantity" | Yes | integer |
| "retrievalGb" | Yes | integer |

Load Balancer

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "bandwidth" | No | integer |
| "processedGb" | Yes | integer |
| "quantity" | Yes | integer |

Other

| Key | Required | Description |
| --- | --- | --- |
| "name" | Yes | string |
| "csp" | Yes | string allowed values: "AWS", "AZURE", "GCP", "OCI" |
| "serviceName" | Yes | string |
| "description" | No | string |
| "cost" | Yes | integer |
| "currency" | Yes | string allowed values: "USD", "GBP", etc |

When importing a JSON or XLSX file, the names of all services need to be present in the file. If no resources/ requirement need to be added for a given service type, it should be present with empty brackets. For example: For load balancer: “loadbalancer”: [].

C. Importing the file to add resources

Example Request

```
curl -X 'POST' \
'https://api.cloudability.com/v3/workload/bulk-upload/{upload-type}{workload-id}' \
-H 'accept: application/json' \
-H 'Content-Type: multipart/form-data' \
-F 'Resource file=@template.json;type=application/json' \
-u '<Token Generated>'
```

| Key | Required | Description |
| --- | --- | --- |
| Workload-ID | Yes | string - should be in uuid format |
| upload-type | Yes | string allowed value "JSON, XLSX" |

D. Getting the resources in error post upload

Example Request

```
curl -X 'GET' \
'https://api.cloudability.com/v3/workload/errors/export/{workload-id}' \
-H 'accept: application/json' \
-u '<Token Generated>'
```

Getting information about the added resources

The GET API below will provide the list of all resources that were recently added, resource ID and additional configuration details.

```
curl -X 'GET' \ 
' https://api.cloudability.com/v3/workload/{workload-id}/resource' \ 
-H 'accept: application/json' \
```

Generating Recommendations

You will need to run a job to generate the recommendation for your resources. The job needs to be executed once per workload, and it would need to be re-run if any requirement is updated later.

Example Request:

```
curl -X 'POST' \ 
'https://api.cloudability.com/v3/workload/job/{workload-ID}' \ 
-u '<Token Generated>' \ 
-d ''
```

Then, you can call the GET API below to check the job status and see if it was successful.

Example Request:

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/job/status/{workload-ID}' \ 
-u '<Token Generated>' \ 
Request URL
```

Visualizing Recommendations

To get the recommendation for your resources, you will need to enter your workload ID and the vendor as parameters.

You will get the resource ID as well as a recommendation ID that will be used for the next step. The GET API below fives you details about all recommendations across all service types for a given CSP.

Example Request (for AWS):

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/{workload-ID}/recommendations/aws' \
-u '<Token Generated>'
```

Saving Recommendations

To save each recommendation, you need to provide the resource ID, the recommendation ID, the CSP name and additional fields in the body using the PUT API call below.

For each requirement and each CSP, one recommendation should be saved. There can be a single PUT API call to save all recommendations at once.

The recommendations need to be part of array body for the PUT API call.

Whenever there is a new recommendation available, this PUT API call below needs to be updated accordingly.

Example Request:

```
curl -X 'PUT' \ 
'https://api.cloudability.com/v3/workload/{workload-ID}/cloud-cost' \
-u '<Token Generated>'
-H 'Content-Type: application/json' \
-d '
```

```
[
  {
    "resourceId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "recommendationId": "3fa85f64-5717-4562-b3fc-2c963f66afa7",
    "serviceType": "compute",
    "csp": "AWS"
    "priceType": "ONDEMAND",
    "price": 200,
    "quantity": 100000,
    "additionalInfo": "string",
    "region": "us-west-2"
}
]
```

|  | Required | Description |
| --- | --- | --- |
| resourceID | Yes | string |
| recommendationID | Yes | string |
| serviceType | Yes | string allowed values: "compute", "database", "block_storage", "blob_storage", "network", "other" |
| csp | Yes | string allowed values: "AWS", "AZURE", "GCP" |
| priceType | Yes | string allowed values: "Committed", "ONDEMAND", "SPOT" |
| quantity | Yes | integer |
| additionalinfo | No | This field is not used. |

Viewing Workload

Example Request (Workload "Summary" Tab):

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/report/summary/{workload-id}?vendor={vendor}' \ 
-u '<Token Generated>'
```

Example Request (Workload "Analysis" Tab):

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/report/analysis/{workload-id}?vendor={vendor}' \ 
-u '<Token Generated>'
```

Exporting Workload Summary to Excel

Example Request

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/report/export/{workload-id}' \
-u '<Token Generated>
```

| Key | Required | Description |
| --- | --- | --- |
| WorkloadID | Yes | string - ID provided in the workload endpoint object response |

Example Request

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/report/export/{workload-id}' \
-u '<Token Generated>'
```

Duplicating workload

Example Request

Perform a GET request at the scorecards end point, specifying a view Id and dimension.

```
curl -X 'POST' \ 'https://api.cloudability.com/v3/workload/duplicate' \
-u '<Token Generated>' \
-H 'Content-Type: application/json' \
-d '{
"id": "string",
"name": "string"
}'
```

| Key | Required | Description |
| --- | --- | --- |
| ID | Yes | string - ID provided in the workload endpoint object response |
| name | Yes | string - name for the workload duplicate |

Deleting Workload

Example Request:

```
curl -X 'DELETE' \ 
'https://api.cloudability.com/v3/workload/{workload-id}' \ 
-u '<Token Generated>'
```

| Key | Required | Description |
| --- | --- | --- |
| WorkloadID | Yes | string - ID provided in the workload endpoint object response |

Getting the List of Workloads

Example Request:

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/internal/workload?offset={}&limit={}&search={}&user-type={}' \ 
-u '<Token Generated>'
```

| Key | Required | Description |
| --- | --- | --- |
| offset | Yes | int |
| limit | Yes | int |
| search | Yes | string |
| user-type | Yes | string allowed values - all, admin, mine, shared |

Updating Workload Planning Preferences

Workload Planning Preferences can only be updated by Cloudability Admin.

A. Current Workload Planning Preferences

Example Request:

```
curl -X 'GET' \ 
'https://api.cloudability.com/v3/workload/admin-preferences' \ 
-u '<Token Generated>'
```

Preference view feature is available to Admin users and the users who have view preferences permissions.

B. Updating Workload Planning Preferences

Example Request

```
curl -X 'PUT' \ 
'https://api.cloudability.com/v3/workload/admin-preferences' \ 
-u '<Token Generated>' \ 
-H 'Content-Type: application/json' \ 
-d '
```

```
'{
    "preferences": [
  { 
    "vendor": "string",
    "allowed": true,
    "onDemandEnabled": true,
    "committedEnabled": true,
    "spotEnabled": true,
    "capacityReservationEnabled": true,
    "commitmentDefaultOptionsDisabled": true,
    "computeOffering": "string",
    "commitmentTerm": "string",
    "paymentOptions": "string",
    "sudEnabled": true,
    "discountUpliftDesc": "string",
    "discountUpliftPercent": 100,
    "unusedCapacity": 100
  }
 ]
 }'
Send feed
```
