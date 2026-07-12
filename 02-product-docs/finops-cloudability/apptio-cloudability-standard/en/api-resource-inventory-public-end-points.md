---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Resource Inventory – Public API End Points"
breadcrumb:
  - "Cloudability API"
  - "Resource Inventory – Public API End Points"
source_path: "SSVCLNQ/api-v3/resource-inventory-public-api-endpoints.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Resource Inventory – Public API End Points

Resource Inventory has the below public API endpoints:

Resource inventory report run API: The resource inventory run endpoint is used to dynamically run resource inventory reports and return detailed information about your organization’s resource details.

Resource Inventory API End Points

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/run - ‘[auth_token]:'

```

Request Parameters

| Argument | Description |
| --- | --- |
| service(required) | Services for the run report such as EC2,EBS,S3,Compute |
| vendor(required) | vendor for the run report such as AWS,AZURE,GCP |
| startDate (required) | The start date for the report. Format: YYYY-MM-DD |
| endDate (required) | The end date for the report. Format: YYYY-MM-DD |
| dimensions | Comma delimited list of dimensions to include in report. Example: dimensions=vendor,region |
| is_kpi | flag to identify whether to return either all the kpi or resources report. If omitted it is defaulted to 'false'. |
| metrics | Comma delimited list of metrics to include in report. Example: metrics = unblended_cost,adjusted_amortized_cost |
| limit | maximum number of records to return.If limit =0 or not provide it will show maximum 64000 records. |
| offset | Position to start for the results. Example: offset = 1 |
| filters | filter to apply on the measures for the report |
| viewId | If omitted, the user's default view will be applied |

Start date and end date difference should not be more than 31 days. Start date should not be more than three months before the current date.

Sample Request:

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/run?service=ec2&vendor=aws&startDate=2024-10-01&endDate=2024-10-05&limit=1&offset=0'"

```

Run API Sample Response

```
[ 
				{ 
				"KIP": null, 
				"columnHeaders":  {
				"keys":  [
				"vendor_account_name", 
				"region", 
				"resource_identifier",
			 	   "product_name",	
				"item_description",
				"state",
				"snapshot",
			"launch_date",
				"tagged_resource",
				"unblended_cost",
				"public_on_demand_cost",
				"adjusted_amortized_cost",
				"ec2_cpu_utilization_avg",
				"ec2_network_in_avg",
				"ec2_network_out_avg"
				]
				},
				"filters": [],
				"count": 1,
				"pagination": {},
				"dates": {
				"start": "2024-10-01",
				"end": "2024-10-05"
				},
				"month": "",
				"rows": [
				[
				"xyz Engineering",
				"xyz region",
				"sample resource id",
				"sample product name",
				"$1234 per Hour",
				"Not Available",
				"false",
				"Not Available",
				"true", 
				"1234.00",
				"1234.00", 
				"1234.00",
				"0.0",
				"0.0",
				"0.0"
				]
				]
				}
		
```

Resource inventory measures API: To retrieve the list of measures. Measures includes dimensions,metrics ,business dimensions, account groups, tags that can be used in reports.

Resource Inventory API End Points

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/measures - ‘[auth_token]:'
```

Request Parameters:

| Argument | Description |
| --- | --- |
| service(required) | Services for the run report such as EC2,EBS,S3,Compute |
| vendor(required) | vendor for the run report such as AWS,AZURE |

Sample Request:

```

				{ 
				"dimensions": [
				{
				"readable_name": "sampe dimension Name",
				"api_name": "xzy_abc"
				}
				],
				"metrics": [
				{
				"readable_name": "sample metric name",
				"api_name": "abc_xyz"
				}
				],
				"tags": [
				{
				"name": "sample tag name",
				"label": "sample tag label"
				}
				],
				"business_dimensions": [
				{
				"name": "sample business dimension name",
				"label": "sample business dimension label"
				}
				]
			}
```

List of Sample Reports

Below are a few sample reports that can help you with the usage of the resource inventory reports API:

Run report with relative dates in json:

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/run?service=ec2&vendor=aws&startDate=2024-10-01&endDate=2024-10-05&limit=5&offset=0'

```

Run and export report in csv:

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/run?service=ec2&vendor=aws&startDate=2024-10-01&endDate=2024-10-05&limit=5&offset=0' --header 'Accept: text/csv'
```

This output can be redirected to a csv file.

is_kpi should always be 'false' or omitted in case of report export in csv.

Run report with only kpi:

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/run?service=ec2&vendor=aws&startDate=2024-10-01&endDate=2024-10-05&limit=5&offset=0&is_kpi=true'

```

Measures API:

```
'curl 'https://api.cloudability.com/v3/reporting/resourceinventory/measures?service=ec2&vendor=aws'

```
