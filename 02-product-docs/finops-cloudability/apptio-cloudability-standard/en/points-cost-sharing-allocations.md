---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cost Sharing Allocations"
breadcrumb:
  - "Cloudability API"
  - "Cost Sharing End Points"
  - "Cost Sharing Allocations"
source_path: "SSVCLNQ/api-v3/allocations-cost-sharing.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cost Sharing Allocations

Summary

The Allocations API serves as the foundation for cost sharing, managing the core allocation entities and their relationships with business dimensions. This API lets you create, manage, and remove cost allocation frameworks.

Key features

The key features for Allocations API include the following:

- Create new allocation structures for business dimensions
- Update existing allocations with new business dimension mappings
- Retrieve single or multiple allocation configurations
- Delete allocation structures with cascading rule cleanup
- Support for up to 25 business dimensions

Cost sharing Allocations API perform the following:

- Maintain creation and updates timestamps
- Support owner attribution for tracking
- Include ordering capabilities for organization
- Maintain referential integrity with associated rules

End Points

POST /v3/cost-sharing/allocation

This API is used for creating a new allocations.

Query Arguments for the Request Body

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The Allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 that’s not already used in any Allocation |

Example Request

```
curl --request POST \
	 --url 'https://api.cloudability.com/v3/cost-sharing/allocation' \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'content-type: application/json' \
	 --header 'x-cldy-user-id: ${USER_ID}' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
	 --data '{
			  "businessDimensionIndex": 20
		     }'
```

Example Response

```
{
 "result": {
	     "allocationId": "bf219659-2a20-4814-bda3-11c04b76d711",
	     "businessDimensionIndex": 20,
	     "createdAt": "2025-01-27T08:12:27.231Z",
            "updatedAt": "2025-01-27T08:12:27.231Z",
	     "order": 25
	    }
}
```

PUT /v3/cost-sharing/allocation

This API is used for updating an existing allocation.

Query Arguments for the Request Body

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationId | ID of the existing allocation that needs to be updated | REQUIRED | An existing, valid Allocation ID |
| businessDimensionIndex | The Allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 that’s not already used in any Allocation |

Example Request

```
curl --request PUT \
	 --url https://api.cloudability.com/v3/cost-sharing/allocation \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'content-type: application/json' \
	 --header 'x-cldy-user-id: ${USER_ID}' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
	 --data '{
			  "allocationId": "bf219659-2a20-4814-bda3-11c04b76d711",
			   "businessDimensionIndex": 14
				}'
```

Example Response

```
{
 "result": {
 "allocationId": "bf219659-2a20-4814-bda3-11c04b76d711",
 "businessDimensionIndex": 14,
 "createdAt": "2025-01-27T08:12:27.000Z",
 "updatedAt": "2025-01-27T08:17:25.292Z",
 "order": 0
}
}
```

GET /v3/cost-sharing/allocation

This API is used for retrieving all existing allocation.

Example Request

```
curl --request GET \
      --url https://api.cloudability.com/v3/cost-sharing/allocation \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}''
```

Example Response

```
{
 "result": [
	    {
	     "allocationId": "18b0cab7-46f8-4526-b328-1cab27ec2c28",
	     "businessDimensionIndex": 1,
	     "createdAt": "2024-08-27T06:52:40.000Z",
	     "owner": "Sai Krishna",
	     "updatedAt": "2025-01-13T20:31:39.000Z",
	     "order": 1
	    },
	    {
	     "allocationId": "da1c9f96-4e20-4d40-a17c-43149e304ee0",
	     "businessDimensionIndex": 4,
	     "createdAt": "2024-12-06T17:52:52.000Z",
	     "owner": "Shivesh Singh",
	     "updatedAt": "2024-12-06T17:52:52.000Z",
	     "order": 2
	     },
	     {
	      "allocationId": "bf2b6626-6b98-4e6a-a8e2-0e5b231a5b4c",
	      "businessDimensionIndex": 14,
	      "createdAt": "2024-12-06T19:43:31.000Z",
	      "owner": "Komal Dhuri",
	      "updatedAt": "2024-12-06T19:43:31.000Z",
	      "order": 3
	      }
	     ]
}
```

GET /v3/cost-sharing/allocation/${allocationId}

This API is used for retrieving a specific allocation by its Allocation ID.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationId | ID of the existing allocation that needs to be retrieved | REQUIRED | An existing, valid Allocation ID |

Example Request

```
curl --request GET \
	 --url https://api.cloudability.com/v3/cost-sharing/allocation/18b0cab7-46f8-4526-b328-1cab27ec2c28 \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
```

Example Response

```
{
 "result": {
	     "allocationId": "0e5d398b-07e2-4969-854a-f01abe9e35ca",
	     "businessDimensionIndex": 14,
	     "createdAt": "2024-08-27T06:52:40.000Z",
	     "updatedAt": "2025-01-13T20:31:39.000Z",
	     "rules": []
           }
}
```

Another example of allocation having some rules is as follows:

Example Request

```
curl --request GET \
     --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6 \
     --header 'authorization: ${JWT_TOKEN}' \
     --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
```

Example Response

```
{
 "result": {
 "allocationId": "d806a527-1554-49f3-9c8f-a5deae0e37b6",
 "businessDimensionIndex": 17,
 "createdAt": "2024-07-29T09:38:56.000Z",
 "owner": "Shilpesh Solanki",
 "updatedAt": "2024-10-15T02:08:09.000Z",
 "rules": [
         {
	   "ruleId": "db674ad7-9935-4971-9412-8e9eca60a54d",
	   "source": [
	      {
		"name": "datalink",
		"weight": 0
	      }
	      ],
	    "destination": [
	       {
		 "name": "databricks",
		 "weight": 0.25
		},
		{
		 "name": "datalake",
		 "weight": 0.75
		}
		],
		 "allocationMethod": "proportional_fixed_weighting",
		 "telemetryMetricIndex": 0
		},
		{
		 "ruleId": "4ba8fa54-b1eb-49ff-a5d5-37be5502de66",
		 "source": [
			   {
			    "name": "aql",
			    "weight": 0
			   }
		           ],
			   "destination": [
			  {
			  "name": "cdc",
			  "weight": 0.5
			  },
			  {
			   "name": "ccm",
			   "weight": 0.5
			   }
			   ],
			   "allocationMethod": "even_split",
			   "telemetryMetricIndex": 0
			   },
		           {
			     "ruleId": "5fdda893-f3b7-449a-b389-d8ad3218ec85",
			     "source": [
			     {
			      "name": "benchmarking",
			      "weight": 0
			     }
			     ],
			     "destination": [
			      {
				"name": "vedas",
				"weight": 0
			       },
			       {
				"name": "cdc",
				"weight": 0
				}
				],
				"allocationMethod": "telemetry_consumption",
				"telemetryIdentifier": "custom",
				"telemetryMetricIndex": 2
				},
				{
				"ruleId": "fa9cffcf-40c0-4979-9061-4cac7b048401",
				"source": [
				{
				"name": "akp",
				"weight": 0
				},
				{
				"name": "aviatrix",
				"weight": 0
				}
				],
				"destination": [
				{
				"name": "targetprocess",
				"weight": 0
				},
				{
				"name": "counterstrike",
				"weight": 0
				},
				{
				"name": "datadog",
				"weight": 0
				}
				],
				"allocationMethod": "proportional_metric",
				"telemetryMetricIndex": 0
				}
				]
				}
}
```

DELETE /v3/cost-sharing/allocation

This API is used for deleting one or more allocations by specifying their IDs.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationIds | List of one or more Allocation IDs of the existing allocation(s) that need to be deleted | REQUIRED | One or more existing, valid Allocation IDs |

Example Request

```
curl --request DELETE \
	 --url https://api.cloudability.com/v3/cost-sharing/allocation \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'content-type: application/json' \
	 --header 'x-cldy-user-id: ${USER_ID}' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
	 --data '{
		   "allocationIds": [
		   "0e5d398b-07e2-4969-854a-f01abe9e35ca",
		   "0b40db49-d796-46e2-b69f-b3778fe419b4"
				]
	         }'
```

Example Response

```
{
 "result": {
	     "message": "Deletion successful. 2 allocation records deleted. 0 rules deleted"
	    }
}
```
