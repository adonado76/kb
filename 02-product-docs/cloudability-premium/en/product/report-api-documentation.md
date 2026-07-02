---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Report API Documentation"
breadcrumb:
  - "Cloudability Premium"
  - "Cloudability API"
  - "Containers End Points"
source_path: "product/report-api-documentation.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Report API Documentation

Summary

The report endpoint is intended to replace many functions that were previously split across a
variety of containers APIs and is intended to provide a more singular view of the data powering the
containers insights feature.

This endpoint allows for analysis of data by specification of specific metrics to be aggregated
which can be combined with groups and filters to gather cost.

Endpoint

`/v3/containers/report`

Query Parameters:

| Parameter | Required | Description | Default | Allowed |
| --- | --- | --- | --- | --- |
| viewId | No | Cloudability view identifier that can be passed to enable filtering by account identifiers | Organization default view identifier | 0 (all if permitted), any configured numeric value |

Request Body

The report request body is a json object comprised of a the following key attributes:

| Parameter | Required | Type | Example | Supported Values |
| --- | --- | --- | --- | --- |
| start | Yes | date | 2024-06-01 | Any date after 2022-01-01 |
| end | Yes | date | 2024-06-02 | Any date after 2022-01-01, must be greater than or equal to start date |
| costType | Yes | string | adjusted | See: Supported Cost Types |
| metrics | Yes | list of strings | ["total\_cost", "total\_cost\_efficiency"] | See: Supported Metric Values |
| limit | Yes | integer | 10 | 1-1000 |
| widgetType | Type | string | top | See: Supported Widget Types |
| count | No | list of strings | ["cluster"] | See: Supported Group, Count and Filter Values |
| group | No | list of strings | ["cluster"] | See: Supported Group, Count and Filter Values |
| filters | No | list of strings | ["cluster=={cluster\_uuid}"] | See: Supported Group, Count and Filter Values |
| sort | No | list of configurations | [{"sortMetric":"total\_cost","sortOrder":" desc"}] | See: Supported Sort Configurations |
| paginationToken | No | string | � | See: Pagination |

Supported Cost Types

| Sort Type | Relation to Containers UI |
| --- | --- |
| adjusted | Cash |
| total\_adjusted\_amortized | Adjusted Amortized |

Supported Metric Values

| Metric | Standard Cost Metric | Standard Usage Metric | Notes |
| --- | --- | --- | --- |
| cpu/reserved | Yes | Yes | Evaluated based upon the maximum of requested and utilized resources |
| memory/reserved | Yes | Yes | Evaluated based upon the maximum of requested and utilized resources |
| network/rx | Yes | Yes | Fairshare values will always equal Allocated values |
| network/tx | Yes | Yes | Fairshare values will always equal Allocated values |
| filesystem/usage | Yes | Yes | � |
| persistent\_volume/usage | Yes | Yes | Usage is determined based off of the requested size of the PV, and is 1:1 with a PVC |
| gpu/reserved | Yes | Yes | Fairshare values will always equal Allocated values |
| miscellaneous | Yes | No | This is a cost-only metric |

Request-able fields

| Field Name | Field Type | Supported Metrics | Meaning |
| --- | --- | --- | --- |
| total\_cost\_fairshare | Aggregated | N/A | Total fairshare cost across all metric types, this represents the aggregated underlying costs of all resources contributing to the query |
| total\_cost\_allocated | Aggregated | N/A | Total allocated cost across all metric types, this represents the utilized cost of all resources contributed to the query |
| total\_cost\_idle | Aggregated | N/A | Total idle cost across all metric types, calculated via total\_cost\_fairshare - total\_cost\_allocated |
| total\_cost\_efficiency | Aggregated | N/A | Total cost efficiency across all metric types, calculated via total\_cost\_allocated / total\_cost\_fairshare |
| usage\_cost\_efficiency | Aggregated | N/A | Usage cost efficiency across all metric types, calculated via a ratio of usage cost / total\_cost\_allocated |
| {metric} /usage\_cost\_allocated | Per Metric | cpu, memory | Usage cost per metric |
| {metric} /usage\_cost\_efficiency | Per Metric | cpu, memory | Usage cost efficiency per metric, calculated via a ratio of usage cost / total\_cost\_allocated |
| {metric}/request | Per Metric | cpu, memory, gpu | Amount of resources requested |
| {metric}/usage | Per Metric | cpu, memory, gpu | Amount of resources utilized |
| {metric}/limit | Per Metric | cpu, memory, gpu | Limit on resources, 0 in this case indicates no limit has been set |
| {metric}\_cost\_fairshare | Per Metric | Standard cost metrics | Fairshare cost representation of the metric usage |
| {metric}\_cost\_allocated | Per Metric | Standard cost metrics | Allocated cost representation of the metric usage |
| {metric}\_cost\_idle | Per Metric | Standard cost metrics | Fairshare - Allocated cost representation of the metric |
| {metric}\_cost\_efficiency | Per Metric | Standard cost metrics | Allocated/Fairshare cost value |
| {metric} \_utilization\_fairshare | Per Metric | Standard cost metrics | Fairshare utilization value |
| {metric} \_utilization\_allocated | Per Metric | Standard cost metrics | Allocated utilization value |
| {metric}\_utilization\_idle | Per Metric | Standard cost metrics | Fairshare - Allocated utilization |
| {metric} \_utilization\_efficiency | Per Metric | Standard cost metrics | Allocated/Fairshare utilization value |

Supported Widget Types

| Widget Type | Relation to Containers UI | Meaning | Requirements | Restrictions |
| --- | --- | --- | --- | --- |
| top | Table Data | This is the most common representation of containers data which returns aggregated data over the specified time period | � | Group must not contain a time period |
| kpi | KPI Widgets | This provides a singular value back | � | Single result only  Group is not available Pagination is not available |
| bar | Bar Charts | This provides a set of top/bottom values without respect for generating continuous series of data across the time period | A time group must be set (ex: day) | Pagination is not available |
| line | Line Charts | This returns the top/bottom continuous series of data across the time period | A time group must be set (ex: day) | Pagination is not available |

Supported Group, Count and Filter Values

Groups, Counts, and Filters share a overlapping set of accessible data, which can be utilized in
the following ways:

Groups

Groups return results aggregated by unique values in that field.

For example, grouping by cluster would return a result set that is isolated by cluster.

Counts

Counts return a result section that identifies the number of unique entries for that aspect.

For example, a count of namespaces would return the total number of namespaces within the
selection.

Filters

Filters allow a user to constrain the result set to only a subset of results.

For example, supplying a filter of workload\_type==deployment would only return results for
workloads identified as being owned by a deployment.

| Value | Meaning | Example Returned Values | Supports Filter | Supports Group | Supports Count |
| --- | --- | --- | --- | --- | --- |
| cluster | Cluster unique identifier, a full set of these with name mappings can be retrieved from the clusters endpoint | XXXXXXX-XXXX-XXXX-XXXXXXXXXXXXXXXX | Yes | Yes | Yes |
| day | Allows for grouping data by day, must be used with a supported widgetType (bar/line) | 2024-06-01 | No | No | No |
| workload\_type | Highest level owner type of the workload | deployment, cronjob, statefulset, etc | Yes | Yes | Yes |
| workload\_name | Highest level owner name of the workload | my-service-name | Yes | Yes | Yes |
| namespace | Namespace where workloads are present | my-namespace-name | Yes | Yes | Yes |
| container | Container name that is running on the cluster | my-container-name | Yes | Yes | Yes |
| pod | Pod name that is running on the cluster | my-pod-name | Yes | Yes | Yes |
| node | Node name that is assigned | ip-1.2.3.4.region.compute.internal | Yes | Yes | Yes |
| node\_id | Provider node identifier | aws:///region/i-1234 | Yes | Yes | Yes |
| instance\_family | Instance family of the underlying node | t2 | Yes | Yes | Yes |
| instance\_category | Instance category of the underlying node | General Purpose | Yes | Yes | Yes |
| instance\_type | Instance type of the underlying node | t2.micro | Yes | Yes | Yes |
| savings\_plan | Savings plan type applied to the underlying node | ComputeSavingsPlan | Yes | Yes | Yes |
| lease\_type | Lease method of the underlying node | On-Demand | Yes | Yes | Yes |
| reserved\_instance | If the underlying node is running as part of a reserved instance commitment | Y, N | Yes | Yes | Yes |
| cpu\_allocatable | CPU units (in microcore), available on the underlying node | 48000000 | Yes | Yes | Yes |
| memory\_allocatable | Memory (in bytes) available on the underlying node | 1000000000 | Yes | Yes | Yes |
| gpu\_allocatable | GPU units (in microgpu), available on the underlying node | 1000000 | Yes | Yes | Yes |
| region | Region in which the underlying node is running | us-west-2 | Yes | Yes | Yes |
| zone | Availability zone in which the underlying node is running | us-west-2a | Yes | Yes | Yes |
| node\_group | Node group (if detectable), that the underlying node is part of | my-node-group | Yes | Yes | Yes |
| vendor | Cloud provider that the cluster is running on | aws, azure, etc | Yes | No | No |
| cluster\_type | Cluster type that is running | eks, gke, openshift, etc | Yes | No | No |

Using Filters

Filters can be configured by supplying the:

- Filtered Attribute 
  - Any value denoted as filterable in the above list

- Operator 
  - ==

    - Equals (case sensitive)
  - []=

    - One of (case sensitive)

- Filtered Value 
  - Any value that the user wants to filter upon

Examples:

- namespace==kube-system 
  - Will filter down results to only show data for kube-system

- workload\_type[]=cronjob,job 
  - Will filter down results to only show data for cronjobs or jobs

Supported Sort Configurations

If not set, the sort feature defaults to sorting by the first specified metric column in
descending order. This is setup to ensure pagination is always possible.

Sort values should be passed in the order that the caller wishes them to take place, and can be
specified for any requested metric value.

The example below would sort rows by efficiency in descending order, then by total\_cost in
descending order.

```
[
  {
    "sortMetric": "total_cost_efficiency",
    "sortOrder": "desc"
   },
   {
     "sortMetric": "total_cost",
     "sortOrder": "desc"
   }
 ]
```

Pagination

| Field | Type | Description |
| --- | --- | --- |
| result.pagination.hasNext | boolean | Indicates whether there is a following page |
| result.pagination.nextToken | string | Provides a string value that may be passed back to the API to get the next set of results |

If the above data for pagination indicates that another page is available for consumption, then
the value in "nextToken" can be passed back into the api via the "paginationToken" parameter.

Note:

The request must not be changed in any other regard, and doing so may cause errors or
inconsistent results to be returned.

US Example (API endpoint): https://api.cloudability.com/v3/containers/report

Example Requests

```
curl --location 'https://api.cloudability.com/v3/containers/report' \
--header 'apptio-opentoken: {token}' \
--header 'apptio-environmentid: {env_id}' \
--header 'Content-Type: application/json' \
--data '{
    "start": "2024-06-10",
    "end": "2024-06-10",
    "costType": "adjusted",
    "metrics": [
	"total_cost"
    ],
    "group": [
	"namespace"
    ],
    "count": [
	"workload_name"
    ],
	"filters": [
		"cluster==XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX"
	],
    "sort": [
	{
	     "sortMetric": "total_cost",
	     "sortOrder": "desc"
	}
    ],
    "widgetType": "top",
    "limit": 1
}'
```

Example response, including the pagination token that can be passed back into the api.

```
{
    "result": {
	"data": [
	   {
		"count": [
		    {
			"key": "workload_name",
			"value": "20"
		    }
		],
		"dimensions": {
		    "namespace": "my-namespace"
		},
		"metrics": {
		    "total_cost": {
			"unit": "currency",
			"values": [
				100.00
			]
		    }
		}
	    }
	 ],
	"pagination": {
	    "hasNext": true,
	    "nextToken": "veryLongPaginationToken"
	}
   }
}
```

This response body is broken into the following section:

| Field | Type | Meaning |
| --- | --- | --- |
| result.data | []object | This is the primary response body that contains a series of elements identified by the requested group values |
| result.data[N].count | []map [string] string | This represents a set of objects containing the requested unique count of values |
| result.data[N].dimensions | map[string] string | This represents the uniquely grouped attributes determined by the grouped attributes |
| result.data[N].metrics | map[string] object | This represents the aggregated metric values. When grouping by time, each time unit will be represented by an index in the "values" array |
| result.data[N].metrics. {metric}.unit | string | The specific unit for that metric type, possible values are: currency, bytes, microcpu, microgpu, efficiency |
| result.data[N].metrics. {metric}.values | []float64 | A set of values representing the utilized resources over the time period. When grouping by day for example, each entry in the array represents a single day |

**Parent topic:** [Containers End Points](../api-v3/containers_endpoints.html)
