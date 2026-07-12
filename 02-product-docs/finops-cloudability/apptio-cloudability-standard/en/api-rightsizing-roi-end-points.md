---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Rightsizing ROI End Points"
breadcrumb:
  - "Cloudability API"
  - "Rightsizing ROI End Points"
source_path: "SSVCLNQ/api-v3/rightsizing-roi-end-points.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Rightsizing ROI End Points

Last Updated: 2025-08-08

Summary

The Rightsizing ROI API provides the rightsizing ROI recommendation data for resources from supported services. Read more about Rightsizing ROI .

End Points

Rightsizing ROI offers two actions at the following endpoint: /rightsizing-roi/actioned ( https://api.cloudability.com/v3/rightsizing-roi/actioned )

Supported Actions:

- GET - retrieve a list of the tracked recommendations in Rightsizing ROI
- DELETE – Delete a desired ticket

GET Request Parameters

| Argument | Description |
| --- | --- |
| filter | Filter the tracked recommendations based on an attribute of your choice. Example: {{filters=vendorService==AWS S3 }} (filter by S3 tracked recommendations only) Example: filters=assignee==John Doe (filter by tracked recommendations assigned to John Doe) |
| limit | Used together with offset. Example: limit=10 (default = 50) |
| offset | Used together with limit. Example: offset=0 (default = 0) |
| sort | Sort the tracked recommendations based on an attribute of your choice. Example: {{sort=+resourceName }} (sort by tracked recommendations name ascending) Default: sort=-potentialSavings (sort tracked recommendations with highest savings potential descending) |
| viewId | The number of the View . If blank, the view will be your default view. |

Response Object

| Key | Description |
| --- | --- |
| actionTaken | The action taken on the resource. This will be null if no action has been taken yet. |
| dateActioned | The date the action was taken on the resource. This will be null if no action has been taken yet. |
| policyId | UUID indicating the Rightsizing Policy from which the tracked recommendation was generated. |
| orgId | Unique integer representing the organization. |
| ymd | Integer representing the year-month-day when an tracked recommendation was generated via an automated Rightsizing Policy run. Example: 20230821. This will be 0 if the recommendation was generated via any other method (i.e. by manual ticket creation from a policy run or individually via Rightsizing page). |
| timeline | The look back period in days, used for calculating the recommendations, either ten-day or thirty-day. |
| provider | The source provider of utilization data from which the recommendations were calculated, for example, NATIVE or DATADOG or NEWRELIC. |
| vendorAccountId | The unique identifier for the account the resource exists within. |
| resourceIdentifier | The unique identifier provided by the vendor for the resource. |
| resourceName | Name of the resource. Originates from the Name tag. |
| vendorService | String designating the vendor and service of the resource type: Example, AWS EC2, Azure Compute. |
| resourceType | The current resource type if no action has been taken yet. The actioned new resource type if an action has been taken. |
| recommendedResourceType | The current top recommended resource type. |
| prevResourceType | The original resource type when the tracked recommendation was created. This will be null if no action has been taken yet. |
| prevRecommendedResourceType | The original top recommended resource type when the tracked recommendation was created. This will be null if no action has been taken yet. |
| integrationType | The type of integration used by the tracked recommendation. |
| action | The recommended action to take: rightsize, terminate, autoscale. |
| potentialSavings | The amount that can potentially be saved by taking this recommendation. Once tracked, this value will become zero, signifying that an action has been taken and there is no further potential savings. |
| realizedSavings | Only when a resource type change has been detected, this value represents the savings over 30-days when switching from the original resource type to the new type we detected. |
| percentSavings | Savings as a percentage by moving to target type. |
| costSavings | Savings over the last 10 or 30 days if you had used the target type. |
| basis | The cost basis used. Values are on-demand or effective Default = on-demand Note: the effective cost basis is available for EC2 and RDS services. |
| projectKey | Project key defined by the integration provider, example: "TEST". |
| issueId | Issue ID defined by non-Native integration provider. Example 1000 for Jira integration type. Field is unused (empty string) for Native integration type. |
| issueKey | Key for the issue: Example: "TEST-123". Used by all integration provider types. |
| assignee | Name of assignee of the tracked recommendation. |
| assigneeId | If the assignee is a User in our database with an email address, then this is the ID for lookup. |
| status | Status of the ticket. For Native integration type, currently allowed values are: To Do, In Progress or Done. For Jira integration type, these are defined by the connection Jira instance. |
| resolution | Resolution state of the ticket. example: "Unresolved", "Won't Do", "Resolved". |
| createdAt | Date created. |
| resolvedAt | Date resolved. |
| lastSeenAt | Timestamp of the last time this resource appeared in the Rightsizing pipeline (used to detect resource termination). |

The meta object indicates the total number of tracked recommendations returned by the given request, as well as the aggregate (sum) of the potentialSavings and realizedSavings across the returned results.

```
"result": [
    {
      "policyId": "",
      "orgId": 123456,
      "ymd": 0,
      "timeline": "thirty-day",
	  "provider": "NATIVE",
	  "vendorAccountId": "1234567890",
	  "resourceIdentifier": "i-1234567890",
	  "resourceName": "test-audit",
	  "vendorService": "AWS EC2",
	  "resourceType": "r5.16xlarge",
	  "recommendedResourceType": "r5.8xlarge",
	  "prevResourceType": "",
	  "prevRecommendedResourceType": "",
	  "integrationType": "NATIVE",
	  "action": "RIGHTSIZE",
	  "potentialSavings": 725.22,
	  "realizedSavings": null,
	  "percentSavings": 64,
	  "costSavings": 725.22,
	  "basis": "on-demand",
	  "projectKey": "TEST",
	  "issueId": "",
	  "issueKey": "TEST-12",
	  "assignee": "Jane Doe",
	  "assigneeId": "129617",
	  "createdAt": "2023-08-14T22:19:19.259+00:00",
	  "lastSeenAt": "2023-07-05T21:00:00.000+00:00"
	},
	{
	  "policyId": "",
	  "orgId": 123456,
	  "ymd": 0,
	  "timeline": "ten-day",
	  "provider": "NATIVE",
	  "vendorAccountId": "0987654321",
	  "resourceIdentifier": "arn:aws:rds:us-west-2:0987654321:db:resource-test-0",
	  "resourceName": "resource-test-0",
	  "vendorService": "AWS RDS",
	  "resourceType": "db.r5.4xlarge",
	  "recommendedResourceType": "db.r5.4xlarge",
	  "prevResourceType": "",
	  "prevRecommendedResourceType": "",
	  "integrationType": "NATIVE",
	  "action": "TERMINATE",
	  "potentialSavings": null,
	  "realizedSavings": 487.2,
	  "percentSavings": 100,
	  "costSavings": null,
	  "basis": "on-demand",
	  "projectKey": "TEST",
	  "issueId": "",
	  "issueKey": "TEST-10",
	  "assignee": "John Doe",
	  "assigneeId": "71880",
	  "status": "Done",
	  "resolution": "Done",
	  "createdAt": "2023-03-29T15:13:11.952+00:00",
	  "resolvedAt": "2023-07-14T19:32:55.074+00:00",
	  "lastSeenAt": "2023-07-05T23:00:00.000+00:00"		
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
          "persistentStorageAdded": false
		}
	],
	"meta": {
		"totalCount": 2,
		"aggregates": [
		    {
				"potentialSavings": 725.22,
				"realizedSavings": 487.2
			}
		]
	}
}

```

DELETE Request parameters

| Argument | Description |
| --- | --- |
| orgId | Unique integer representing the organization. |
| ResourceId | The unique resource identifier that the ticket you want to delete is associated with |

Response Object

| Response | Description |
| --- | --- |
| 204 | Ticket successfully deleted, no content returned. |
| 400 | Bad Request |
| 404 | Item not found |
| 500 | Internal Server Error |
