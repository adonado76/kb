---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cost Sharing Rules"
breadcrumb:
  - "Cloudability API"
  - "Cost Sharing End Points"
  - "Cost Sharing Rules"
source_path: "SSVCLNQ/api-v3/rules-cost-sharing.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cost Sharing Rules

Summary

The Rules API handles the specific cost distribution logic within allocations, defining how costs flow from sources to destinations. This API supports all four allocation methods and their specific requirements.

Supported Allocation Methods

The supported allocation methods are as below with their respective features:

1. Even Split Distribution Equally distributes costs across destinations No weighting requirements Simplest implementation model
1. Proportional (Direct Charges) Distributes based on existing direct charges Dynamically adjusts with usage Supports multiple sources and destinations
1. Fixed Weighting Uses predefined weights for distribution Requires weights to total 100% Supports precise cost control
1. Telemetry/ Consumption Based Uses actual usage metrics Requires telemetry metric index Supports dynamic usage-based allocation

Key Features

The key features of Cost Sharing Rules allocation method are:

- Full CRUD operations for rules
- Batch operations support
- Validation of allocation methods
- Weight verification for fixed weighting
- Source and destination management
- Integration with telemetry systems

End Points

POST /v3/cost-sharing/allocation/${allocationId}/rule

This API is used for deleting one or more allocations by specifying their IDs.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationId | The ID of the existing allocation for which the Rule needs to be created | REQUIRED | An existing, valid Allocation ID |
| allocationMethod | The Allocation method using which the cost will be allocated/ distributed from “source(s)” to “target(s)” | REQUIRED | Allocation ids can be one of the following: Even_Split : Display label on the UI - Even Split Proportional_Metric : Display label on the UI - Proportional (Direct Charges) Proportional_Fixed_Weighting : Display label on the UI: Fixed Weighting Telemetry_Consumption : Display label on the UI - Telemetry / Consumption |
| source | List of one or more “source” nodes whose cost needs to be Reallocated/ Distributed | REQUIRED | NA |
| name (in source node | Name of the source | REQUIRED | Text |
| Weight (in source node) | Weight (Percentage/ Ratio) of the cost allocation |  | Floating point number |
| destination | List of one or more “destination” nodes to which the cost needs to be reallocated/distributed based on the “allocationMethod” specified in the Rule | REQUIRED | NA |
| name (in destination node) | Name of the destination | REQUIRED for the destination node, if present | Floating point number |
| weight (in destination node) | Weight (Percentage/ Ratio) of the cost allocation | REQUIRED for the “destination” node, if present. In case of Allocation Method Proportional_Fixed_Weighting . For this allocation method, the weights must add to 100% |  |

Even Split: Example Request

```
curl --request POST \
	 --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'content-type: application/json' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
	 --data '{
		   "allocationMethod": "even_split",
		   "source": [
		   {
		     "name": "aql",
		     "weight": 0
		   }
		   ],
		    "destination": [
		     {
		      "name": "ccm",
		      "weight": 0
		      },
		      {
		      "name": "cdc",
		      "weight": 0
		      }
		      ]
		      }'
```

Even Split: Example Response

```
{
  "result": {
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
 "weight": 
},
{
 "name": "ccm",
 "weight": 0.5
}
],
 "allocationMethod": "even_split",
 "telemetryMetricIndex": 0
}
}
```

Proportional (Direct Charges): Example Request

```
curl --request POST \
	 --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'content-type: application/json' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
	 --data '{
	          "allocationMethod": "proportional_metric",
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
			  "name": "counterstrike",
			  "weight": 0
			 },
			 {
		          "name": "datadog",
			  "weight": 0
			 },
			 {
			  "name": "targetprocess",
			  "weight": 0
			 }
			 ]
             }'
```

Proportional (Direct Charges): Example Response

```
{
{
  "result": {
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
	  telemetryMetricIndex": 0
       }
       }
```

Fixed Weighting: Example Request

```
curl --request POST \
	 --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule \
	 --header 'authorization: ${JWT_TOKEN}' \
	 --header 'content-type: application/json' \
	 --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
	 --data '{
		   "allocationMethod": "proportional_fixed_weighting",
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
		  ]
		  }'
```

Fixed Weighting: Example Response

```
{
 "result": {
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
 }
 }
```

Telemetry/ Consumption: Example Request

```
curl --request POST \
     --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule \
     --header 'authorization: ${JWT_TOKEN}' \
     --header 'content-type: application/json' \
     --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
     --data '{
		"allocationMethod": "telemetry_consumption",
		"source": [
	{
		"name": "benchmarking",
		"weight": 0
	}
			],
		"destination": [
	{
		"name": "cdc",
		"weight": 0
	},
	{
		"name": "vedas",
		"weight": 0
	}
	                       ],
	        "telemetryMetricIndex": 2,
	        "telemetryIdentifier": "custom"
       }'
			
```

Telemetry/ Consumption: Example Response

```
{
 "result": {
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
  }
  }
```

GET /cost-sharing/allocation/${allocationId}/rule/${ruleId}

This API is used to retrieve the details of an existing Rule.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationId | The ID of the existing allocation | REQUIRED | An existing, valid Allocation ID |
| ruleId | ID of the Rule whose details need to be retrieved | REQUIRED | An existing, valid Rule ID |

Example Request

```
curl --request GET \
      --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule/4ba8fa54-b1eb-49ff-a5d5-37be5502de66 \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
```

Example Response

```
{
 "result": {
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
 "telemetryMetricIndex": -1
 }
 }
	
```

PUT /cost-sharing/allocation/${allocationId}/rule

This API is used to or updating one or more Rules of an allocation.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationId | The ID of the existing allocation | REQUIRED | An existing, valid Allocation ID |
| rules | List of one or more nodes for updating Rules by ID | REQUIRED | List of nodes |
| ruleId | Id of the rule to be updated | REQUIRED | An existing, valid Rule ID |
| allocationMethod | The Allocation method using which the cost will be allocated/ distributed from “source(s)” to “target(s)” | REQUIRED | Allocation ids can be one of the following: Even_Split : Display label on the UI - Even Split Proportional_Metric : Display label on the UI - Proportional (Direct Charges) Proportional_Fixed_Weighting : Display label on the UI: Fixed Weighting Telemetry_Consumption : Display label on the UI - Telemetry / Consumption |
| source | List of one or more “source” nodes whose cost needs to be reallocated/ distributed | REQUIRED | NA |
| name (in source node) | Name of the source | REQUIRED | Text |
| weight (in source node) | Weight (Percentage/ Ratio) of the cost allocation | REQUIRED | Floating point number |
| destination | List of one or more destination nodes to which the cost needs to be reallocated/ distributed based on the allocationMethod specified in the rule | REQUIRED | NA |
| name (in destination node) | Name of the destination | REQUIRED for the destination node, if present | Text |
| weight (in destination node) | Weight (Percentage/ Ratio) of the cost allocation | REQUIRED for the destination node, if present In case of allocation method Proportional_Fixed_Weighting . For this allocation method, the weights must add up to 100% | Floating point number |

Example Request

```
curl --request PUT \
      --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'content-type: application/json' \
      --header 'x-cldy-user-id: ${USER_ID}' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
      --data '{
		"rules": [
		{
		 "allocationMethod": "proportional_fixed_weighting",
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
		 "name": "docstore",
		 "weight": 0.75
		}
		],
		 "ruleId": "db674ad7-9935-4971-9412-8e9eca60a54d"
		}
		]
		}'
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
   "name": "docstore",
   "weight": 0.75
   },
   {
    "name": "databricks",
    "weight": 0.25
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
   ]
    "allocationMethod": "proportional_metric",
    "telemetryMetricIndex": 0
   }
   ]
   }
   }
```

DELETE /cost-sharing/allocation/${allocationId}/rule

This API is used to delete one or more rules of an allocation.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| allocationId | The ID of the existing allocation | REQUIRED | An existing, valid Allocation ID |
| ruleIds | Id of the rule which need to be deleted | REQUIRED | One or more existing, valid Rule Id(s) |

Example Request

```
curl --request DELETE \
     --url https://api.cloudability.com/v3/cost-sharing/allocation/d806a527-1554-49f3-9c8f-a5deae0e37b6/rule \
     --header 'authorization: ${JWT_TOKEN}' \
     --header 'content-type: application/json' \
     --header 'x-cldy-user-id: ${USER_ID}' \
     --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
     --data '{
"ruleIds": [
	     "4ba8fa54-b1eb-49ff-a5d5-37be5502de66",
	     "5fdda893-f3b7-449a-b389-d8ad3218ec85"
	    ]
              }'
```

Example Response

```
{
 "result": {
 "message": "Deletion successful. 2 rule records deleted."
}
}
```
