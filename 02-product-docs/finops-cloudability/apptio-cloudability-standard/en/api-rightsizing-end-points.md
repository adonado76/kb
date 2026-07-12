---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Rightsizing End Points"
breadcrumb:
  - "Cloudability API"
  - "Rightsizing End Points"
source_path: "SSVCLNQ/api-v3/rightsizing_end_points.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Rightsizing End Points

Summary

The Rightsizing API provides rightsizing recommendations for resources from supported services. For each of these resources, the API returns multiple optimization recommendations as well as descriptive information such as the current instance size, cost, idle percentage, and recommended actions. The maximum number of resources that can be returned at one time by an API call is 50,000.

End Points

These end points are read-only and are used for obtaining a list of rightsizing recommendations for your cloud resources, for these supported services:

Amazon Web Services

- EC2: /rightsizing/aws/recommendations/ec2
- EC2 ASG: /rightsizing/aws/recommendations/ec2-asg
- EBS: /rightsizing/aws/recommendations/ebs
- S3: /rightsizing/aws/recommendations/s3
- RDS: /rightsizing/aws/recommendations/rds
- Redshift: /rightsizing/aws/underutilized/redshift
- Lambda: /rightsizing/aws/recommendations/lambda
- Elastic IP: /rightsizing/aws/recommendations/elastic-ip

Microsoft Azure

- Compute (VMs) : /rightsizing/azure/recommendations/compute
- Managed Disk : /rightsizing/azure/recommendations/disk
- SQL Database : /rightsizing/azure/recommendations/sql
- Blob Storage : /rightsizing/azure/recommendations/blob-storage

Google Cloud Platform

- GCE: /rightsizing/gcp/recommendations/compute
- GCE MIG: /rightsizing/gcp/recommendations/compute-mig
- GDP: /rightsizing/gcp/recommendations/disk
- GCS: /rightsizing/gcp/recommendations/gcs

Containers

- Workloads: /rightsizing/containers/recommendations/workloads

```
"meta": {
    "totalCount": 4783,
    "aggregates": [
      {
        "basis": "On-Demand",
        "cost": 337029.28,
        "idleSavings": 930.84,
        "rightsizeSavings": 106857.60,
        "optimizedSavings": 229240.84
      }
    ]
  }
```

The following end points are used to snooze and un-snooze rightsizing recommendations for your cloud resources, where “{service}” should be substituted with the path of the service’s end point:

Snooze/Un-Snooze Recommendations

- Snooze: /rightsizing/{vendor}/recommendations/{service}/snooze
- Un-Snooze: /rightsizing/{vendor}/recommendations/{service}/unsnooze

For more information on using the API to snooze/un-snooze recommendations, please visit the “Snooze/Un-Snooze Recs” section on this page.

Request Parameters

| Argument | Description |
| --- | --- |
| basis (required) | The cost basis used. on-demand Values are or effective Default = on-demand Note: The effective cost basis is available for EC2 and RDS services |
| duration (required) | The look back period in days, used for calculating the recommendations. Valid values are : ten-day and thirty-day Default = ten-day Note: only thirty-day is available for S3 |
| filters | Filter the resources based on an attribute of your choice. Example: filters=recommendations.action==Rightsize . To base on attribute within recommendation itself prefix with 'recommendations.'. Multiple filters can be chained together with commas. Example: filters=recommendations.savings>20,recommendations.risk==0 Read more for more details on filtering. |
| limit (required) | Used together with offset to provide pagination . Example: limit=10 . default = 50 |
| maxRecsPerResource | Set a maximum number of recommendations to be delivered with each resource. Example: maxRecsPerResource=10 default = 1 |
| offset | Used together with limit to provide pagination . Example: offset=0 default = 0 |
| product | Product Name, Example ec2, ebs, s3 |
| sort | Sort the resources based on an attribute of your choice. Read more about sorting. Example: sort=-name (sort by name descending) Default: sort=-recommendations.savings ( sort resources with highest savings potential descending) |
| source | Source system for utilization data Examples: datadog , cloudwatch |
| vendorAccountIds | Filter to a list of vendor accounts. Separate accounts using commas. Example: vendorAccountIds=999988887777,111122223333 |
| viewId | The number of the View . If blank, the view will be your default view. |
| options | String value representing which recommendations to return based on if the resource is snoozed. Valid values are ONLY_SNOOZED which will return recommendations for only snoozed resources, or INCLUDE_SNOOZED which will return recommendations for both snoozed and un-snoozed resources. Omitting “option” will return only un-snoozed resources. (default) |

The Resource Object

Current Resource Summary

The result object contains a list of all matching resources. This is the summary data included with each:

service (string) - Name of Recommendation Service (ec2-recs, eb2,rec, etc)

name (string) - Name of the resource. Originates from the Name tag

resourceIdentifier (string) - The unique identifier provided by the vendor for the resource

vendorAccountId (string) - The unique identifier for the account the resource exists within

tagMappings (array) - list of tag key and value pairs of tag mappings

tag (string) - native/provider tag name

tagName (string) - name/key for tag mapping

vendorTagValue (string) - value for this tag

availabilityZone (string) - The availability zone the resource resides in

provider (string) - The source provider, for example, NATIVE

region (string) - The region the resource resides in

os (string) - The operating system of the resource

nodeType (string) - For EC2 this is the instance type of the resource

unitPrice (number) - The per unit rate

effectiveHourly (number) - The hourly rate charged for the resource based on effective rates. DEPRECATED. Instead will show as unitPrice when costBasis=effective .

totalSpend (number) - The entire cost for the resource over the last 10 or 30 days

iopsMax (number) - max IOPS count during period

throughputMax (number) - max throughput MB/S during period

idle (number) - represents the percentage of time the resource has been idle

localCapacity (number) - local EC2 instance storage in GB. Types without associated storage will have a value of -1

localDrives (number) - number of local drives attached to the instance. Types without associated storage will have a value of -1

cpuCapacity (number) - count of CPU cores for current instance

memoryCapacity (number) - memory capacity for current instance in GB

networkCapacity (number) - network capacity for current instance in GB

lastSeen (datetime) - date resource was last seen

tenancy (string) - deprecated

hoursRunning (number) - hours running within period

cpuMax (number) - max CPU percentage during period

memoryMax (number) - max Memory percentage during period

defaultSameFamily (boolean) - use same instance family

defaultCurrentGen (boolean) - use current generations

defaultMemoryFit (boolean) - use same memory specification

instanceTypeAsg (string) - list of the instance types contained in the auto scaling group

utilMemoryMax (number) - max memory percentage of the Lambda during period

utilDurationMax (number) - max running time of the Lambda during period

billedMilliseconds (number) – total running time of the Lambda during period

sourceConfiguredMemory (number) – the configured memory of the Lambda

sourceProcessorArchitectureFamily (number) – the processor architecture family for the Lambda

Recommendation List

For each resource listed there will be a recommendations attribute which is an associated list of recommendation objects. These are the attributes of each recommendation:

recommendations (array) - A list of recommendations for the resource. Described below

action (string) - what action to take: rightsize, terminate, autoscale

preferenceOrder (number) - deprecated

defaultsOrder (number) - deprecated

nodeType (string) - the target instance type

localCapacity (number) - local EC2 instance storage in GB for target resource

localDrives (number) - number of local drives attached to target instance

cpuCapacity (number) - count of CPU cores for target instance

memoryCapacity (number) - memory capacity for target instance in GB

networkCapacity (number) - network capacity of target instance

previousGenTarget (boolean) - Is target instance a previous generation type?

currentGen (boolean) - Is target instance a current generation type?

sameMemory (boolean) - use same memory size as source instance

sameFamily (boolean) - Is the target instance type within the same family

unitPrice (number) - The per unit rate

cpuRatio (number) - ratio of CPU cores (target/original)

memoryRatio (number) - ratio of memory capacity (target/original)

diskXPutCapacity (number) - ratio of memory capacity (target/original)

networkRatio (number) - ratio of network throughput capacity (target/original)

cpuRisk (number) - risk related to CPU - value between 0 and 5 TBC. 0 being zero risk

memoryRisk (number) - risk related to memory - value between 0 and 5 TBC

diskRisk (number) - local disk throughput risk - value between 0 and 5 TBC

networkRisk (number) - risk related to network throughput - value between 0 and 5 TBC

risk (number) - value of 0,1,2,3,4 or 5. 0 being no risk. 5 being highest risk

targetConfiguredMemory (number) – the target configured memory of the Lambda

savingsPct (number) - Savings as a percentage by moving to target type

savings (number) - Savings over the last 10 or 30 days if you had used the target type

inDefaults - deprecated

memoryFit deprecated

persistentStorageAdded TBC - we added EBS costs for say c3 to c4

snoozed (boolean) – is the recommendation snoozed?

Example Object

```
"result": [
    {
      "service": "ec2-recs",
      "name": "My EC2 Instance",
      "resourceIdentifier": "i-5b234a4fae415b77f",
      "vendorAccountId": "458273444843",
      "tagsMappings: [
        {
          "tagName": "tag_user_Environment",
          "vendorTagValue": "production"
        },
        {
          "tagName": "tag_user_Name",
          "vendorTagValue": "My EC2 Instance"
        }
      ],
      "availabilityZone": "ap-southeast-2b",
      "provider": "NATIVE"
      "region": "ap-southeast-2",
      "os": "Linux",
      "nodeType": "i3.8xlarge",
      "unitPrice": 1.81,
      "totalSpend": 434.11,
      "idle": 0,
      "localCapacity": 7600,
      "localDrives": 4,
      "cpuCapacity": 32,
      "memoryCapacity": 244,
      "networkCapacity": 10000,
      "lastSeen": "2019-10-31T23:00:00Z",
      "tenancy" : "default",
      "hoursRunning": 240,
      "cpuMax": 6,
      "memoryMax": 6,
      "recommendations": [
        {
          "action": "Rightsize",
          "preferenceOrder": 1,
          "defaultsOrder": 1,
          "nodeType": "x1e.xlarge",
          "localCapacity": 120,
          "localDrives": 1,
          "cpuCapacity": 4,
          "memoryCapacity": 122,
          "previousGenTarget": false,
          "currentGen": true,
          "sameMemory": false,
          "sameFamily": false,
          "unitPrice": 0.83,
          "cpuRatio": 0.13,
          "memoryRatio": 0.5,
          "diskXPutCapacity": 100,
          "networkRatio": 1,
          "cpuRisk": 0,
          "memoryRisk": 0,
          "diskRisk": 0,
          "networkRisk": 0,
          "risk": 0,
          "savingsPct": 54,
          "savings": 233.95,
          "inDefaults": true,
          "memoryFit": false,
          "persistentStorageAdded": false,
          "snoozed": false
        }
      ],
      "defaultSameFamily": false,
      "defaultCurrentGen": true,
      "defaultMemoryFit": false
    }
  ]
```

Some Important Attributes

There are a few attributes worth a special mention

- risk : This is the graded risk for an individual recommendation. risk can take a value of 0,1,2,3,4 or 5. 0 implies that we expect the recommendation to have sufficient headroom for your resource without any clipping. 1 through 5 indicate increasing risk that performance could be affected. Note that there is a total risk score as well as individual ones for CPU, Network, Memory and Disk.
- rank : rank is based on a grouping system of risk and savings. The highest ranking recommendation will come from the cohort with lowest risk. From that cohort it will pick the one with the highest savings. The next in line ranking wise will come from the cohort with second lowest risk, and again highest savings. Rank is established as such by cycling through these risk cohorts until all recommendations as ranked. See special notes at bottom of page for extra ranking options.

Examples

Full List of 10-day Dataset EC2 Recommendations

```


curl "https://api.cloudability.com/v3/rightsizing/aws/recommendations/ec2?limit=5&maxRecsPerResource=1&offset=0&duration=ten-day" -u api-token:

```

Full List of 30-day Dataset EBS Recommendations

```


curl "https://api.cloudability.com/v3/rightsizing/aws/recommendations/ebs?limit=5&maxRecsPerResource=1&offset=0&duration=thirty-day" -u apikey:


```

Give Me Just the Default Recommendation per Resource

```


curl "https://api.cloudability.com/v3/rightsizing/aws/recommendations/ec2?rank=default&maxRecsPerResource=1&sort=-recommendations.savings" -u apikey:


```

Give Me All the Recommendations for a Particular Resource/Instance Id

```



curl "https://api.cloudability.com/v3/rightsizing/aws/recommendations/ec2?filters=resourceIdentifier==i-ae3f332111" -u apikey:


```

Give Me Recommendations Just for Specific Accounts

```




curl "https://api.cloudability.com/v3/rightsizing/aws/recommendations/ec2?limit=5&offset=0&vendorAccountIds=999988887777&maxRecsPerResource=1&basis=on-demand&duration=ten-day" -u apikey:


```

Filter My Recommendations Based on Tags

```



curl "https://api.cloudability.com/v3/rightsizing/aws/recommendations/ec2?filters=<tag_key>==<tag_value>" -u apikey:


```

Special Notes

To add another layer to this ranking system you can add rank=default as a query parameter. This will prioritize 2 extra attributes, memoryFit and currentGen before going through the risk/savings routine. currentGen for example would make sure that m4s (a current generation) would get recommended ahead of m1s (previous generation). Recommendations can be memoryFit through two different means 1) Cloudability has received the memory data and identified a fit or 2) Cloudability hasn't received the memory data so memoryFit will only include instance types which have matching memory or higher.

Snooze/Un-Snooze Recs

The following end points are used to snooze and un-snooze rightsizing recommendations for your cloud resources, where “{vendor}” should be substituted with the path of the cloud vendor’s end point and “{service}” should be substituted with the path of the service’s end point.

- Snooze: /rightsizing/{vendor}/recommendations/{service}/snooze

This either adds or updates snooze entries with the supplied expiration, as well as flips the snooze value for the resource recommendation to true.

The following values are specific to snooze/un-snooze:

- expiresOn (date) – The snooze Expiration Date in yyyy-mm-dd format, or the value "never" to set an indefinite snooze.
- resources (array) - A map of Account IDs to a list of Resource IDs for which recommendations will be snoozed.

Example: Snooze individual EC2 resources

```
curl -X POST https://api.cloudability.com/v3/rightsizing/AWS/recommendations/EC2/snooze \\
	 -H 'Content-Type: application/json' \\
	 -u '[auth_token]:' \\
	 -d @- 
{
	"expiresOn": "2024-11-24",
       "resources": { 
       "123456789": ["resource_12345", "resource_123456"],
       "111112222": ["resource_6789"]
}
}		
EOF	
```

Example: Snooze resources matching a filter

```
curl -X POST https://api.cloudability.com/v3/rightsizing/AWS/recommendations/EC2/snooze \\
	 -H 'Content-Type: application/json' \\
	 -u '[auth_token]:' \\
	 -d @- 
{
	"expiresOn": "never",
       "vendorAccountIds": [123456789, 111112222],
       "filters": [
       "region=ap-southeast-2",
       "tag_user_Environment=staging"
]
}		
```

• Un-Snooze: /rightsizing/{vendor}/recommendations/{service}/unsnooze.

Essentially, the same format as the snooze endpoint, but without an expiration. Removes any expiration, as well as flips the snooze value for resource recommendation to false.

Example: Un-snooze individual resources

```
curl -X POST https://api.cloudability.com/v3/rightsizing/AWS/recommendations/EC2/unsnooze \\
	 -H 'Content-Type: application/json' \\
	 -u '[auth_token]:' \\
	 -d @- 
{
	"resources": {
          "123456789": ["resource_12345", "resource_123456"],
          "111112222": ["resource_6789"]
       }
}
```

Example: Un-snooze resources matching a filter

```
curl -X POST https://api.cloudability.com/v3/rightsizing/AWS/recommendations/EC2/snooze \\
	 -H 'Content-Type: application/json' \\
	 -u '[auth_token]:' \\
	 -d @- 
{
       "vendorAccountIds": [123456789, 111112222],
       "filters": [
       "region=ap-southeast-2",
       "tag_user_Environment=staging"
]
}		
```
