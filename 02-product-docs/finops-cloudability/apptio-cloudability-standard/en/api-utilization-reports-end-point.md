---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Utilization Reports End Point"
breadcrumb:
  - "Cloudability API"
  - "Utilization Reports End Point"
source_path: "SSVCLNQ/api-v3/utilization_reports_end_point.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Utilization Reports End Point

The utilization reports endpoints are used to analyze utilization patterns for AWS EC2 instances. Utilization Analytics uses data from AWS Cloudwatch which presents instance-level details such as Average CPU utilization (percent), Bandwidth, and Disk I/O. Utilization analytics are great for visualizing overall elasticity and whether your instances require rightsizing or need to be turned off.

Cost metrics that are made available in Utilization Analytics are calculated in Cloudability using on-demand rates and cover only the compute portion of your bill (i.e., the billable instance hours but not bandwidth, storage, and etc.). As such, they should be used for trending only, not financial reporting. Note that the metric is referred to as Cost (Estimated).

Note that in order for Utilization Analytics to access utilization data, advanced credentialing needs to be in place on respective member accounts which will put in place proper IAM permissions.

Flexible filtering, sorting, and measure (dimensions and metrics) selection is available to craft results to meet specific reporting needs. As a recommended guideline, there is a max of 15 dimensions and 10 metrics that can be added to an API call. By default, results are returned in JSON. To get results in CSV format make sure to set the Accept header with a value of text/csv. Note that pagination is implemented when results exceed 10,000 rows, as described below. Example report calls are provided towards the bottom of this document.

Utilization Report End Point

- /reporting/reports/util for listing current utilization reports
- /reporting/util/run for executing utilization reports
- /reporting/util/measures for listing available utilization reporting measures
- /reporting/util/filters for listing available comparison operators used in filters
- /reporting/util/enqueue for enqueuing util reports
- /reporting/reports/:id/state for checking the state of enqueued reports
- /reporting/reports/:id/results for retrieving finished enqueued reports

The Utilization Report Object

- results (array) - list of utilization row objects, each row comprised of reported dimensions and metrics
- meta (object) - object containing meta information about the report that was run dates (object) - start and end date strings marking the date range of the report filters (array) - list of filters applied to report with detailed information metrics (array) - list of metrics returned in report with detailed information dimensions (array) - list of dimensions returned in report with detailed information aggregates (array) - list of aggregated metrics with detailed information for report offset (number) - Position where to start for the results. Default is 0 limit (number) - Maximum number of utilization rows that can be returned total_results (number) - Total utilization rows returned for executed report

Example Utilization Report Object (Review Example)

```
{
  "results": [
    {
      "instance_identifier": "i-1237aa0e1587577f5",
      "max_cpu_utilization": "0.91925"
    },
    {
      "instance_identifier": "i-0007aa0e1587572c7",
      "max_cpu_utilization": "0.179183"
    }
  ],
  "meta": {
    "dates": {
      "start": "2022-08-30T00:00:00Z",
      "end": "2022-08-30T00:00:00Z"
    },
    "filters": [],
    "metrics": [
      {
        "name": "max_cpu_utilization",
        "label": "CPU Utilization (Max)",
        "description": "The maximum percentage of CPU Utilization...
        "data_type": "percentage",
        "type": "metric",
        "group": {
          "ID": 9,
          "Key": "compute",
          "Name": "Compute"
        },
        "sub_group": {
          "ID": 12,
          "Key": "processing",
          "Name": "Processing"
        }
      }
    ],
    "dimensions": [
      {
        "name": "instance_identifier",
        "label": "Instance ID",
        "description": "The ID associated with a particular AWS instance.",
        "data_type": "string",
        "type": "dimension",
        "group": {
          "ID": 9,
          "Key": "compute",
          "Name": "Compute"
        },
        "sub_group": {
          "ID": 1,
          "Key": "common",
          "Name": "Common"
        }
      }
    ],
    "aggregates": [
      {
        "name": "max_cpu_utilization",
        "label": "CPU Utilization (Max)",
        "description": "The maximum percentage of CPU Utilization...",
        "data_type": "percentage",
        "type": "metric",
        "value": "0.91925"
      }
    ]
  },
  "offset": 0,
  "limit": 2,
  "total_results": 2
}
```

List Current Utilization Reports

Retrieve a list of utilization reports either owned by or shared with the user or org.

```
curl 'https://api.cloudability.com/v3/reporting/reports/util' -u '[auth_token]:'
```

Example Response

```
[
 {
  "id": 1,
  "author": {
  "id": 12345,
  "safe_name": "Test User"
  },
  "category": "Utilization",
  "custom": true,
  "description": "The number of instances running during each hour of the day over the last 7 days.",
  "dimensions": [
  {
  "name": "date",
  "label": "Date",
  "description": "The calendar date (e.g. YYYY-MM-DD).",
  "data_type": "date",
  "type": "dimension",
  "group": {
  "id": 9,
  "key": "compute",
  "name": "Compute"
  },
  "sub_group": {
  "id": 2,
  "key": "time",
  "name": "Time"
  }
   },
  {
  "name": "hour",
  "label": "Hour",
  "description": "The numeric hour of the day (e.g. 1pm => 13).",
  "data_type": "integer",
  "type": "dimension",
  "group": {
  "id": 9,
  "key": "compute",
  "name": "Compute"
  },
  "sub_group": {
  "id": 2,
  "key": "time",
  "name": "Time"
  }
   }
  ],
 "end_date": "23:59:59",
 "filters": [
 {
  "comparator": "==",
  "measure": {
  "name": "date",
  "label": "Date",
  "description": "The calendar date (e.g. YYYY-MM-DD).",
  "data_type": "date",
  "type": "dimension",
  "group": {
  "id": 9,
  "key": "compute",
  "name": "Compute"
  },
  "sub_group": {
  "id": 2,
  "key": "time",
  "name": "Time"
  }
   },
  "value": "2019-06-24"
  }
   ],
  "metrics": [
 {
  "name": "running_instances",
  "label": "Unique Instance Count",
  "description": "The total number of unique instances in a running state during a given time period.",
  "data_type": "integer",
  "type": "metric",
  "group": {
  "id": 9,
  "key": "compute",
  "name": "Compute"
  },
  "sub_group": {
  "id": 8,
  "key": "usage",
  "name": "Usage"
  }
   }
    ],
  "order": "asc",
  "owned_by_user": false,
  "shared_with_organization": false,
  "permission": {
  "actions": [
  "read"
  ]
   },
 "report_dimension_links": [],
 "secondary_end_date": null,
 "secondary_start_date": null,
 "shared": true,
 "shares": [],
 "sort_by": "date",
 "star": false,
 "start_date": "7 days ago at 00:00:00",
 "subscriptions": [],
 "title": "Elasticity - Running Instances per Hour"
  },
    ]
```

Getting list of available measures

Retrieve a list of measures recognized by the server. Measures includes both dimensions and metrics that can be used in reports. Simply perform a GET at the measures endpoint.

```
curl ‘https://api.cloudability.com/v3/reporting/util/measures’ -u ‘[auth_token]:’
```

Example Response

```
[
  {
    "name": "avg_cpu_utilization",
    "label": "CPU Utilization (Avg)",
    "description": "The average percentage of CPU Utilization...",
    "type": "metric",
    "group": {
      "id": 9,
      "key": "compute",
      "name": "Compute"
    },
    "sub_group": {
      "id": 12,
      "key": "processing",
      "name": "Processing"
    }
  },
  {
    "name": "utilization_hours",
    "label": "Utilization Hours",
    "description": "The total number of usage hours on an instance ...",
    "data_type": "integer",
    "type": "metric",
    "group": {
      "id": 9,
      "key": "compute",
      "name": "Compute"
    },
    "sub_group": {
      "id": 8,
      "key": "usage",
      "name": "Usage"
    }
  },
]
```

Getting list of available filter operators

Retrieve a list of recognized filter operators for requesting data

```
curl ‘https://api.cloudability.com/v3/reporting/util/filters’ -u ‘[auth_token]:’
```

Example Response

```
[
  "<=",   # less than or equals
  "[]=",  # in*
  ">="    # greater than or equals
  "<",    # less than
  "=@",   # contains
  "^=",   # matches
  "===",  # strictly equals*
  "==",   # equals
  "!=@",  # does not contain
  "!=",   # not equals
  "!==",  # strictly not equals*
  ">",    # greater than
  "!^=",  # does not match
  "!$=",  #does not end with
  "[]!=", # not in*
  "$=",   #end with
]	
```

* Note that these operators are available via the API only

Run a utilization report

Request Parameters

| Argument | Description |
| --- | --- |
| start_date (required) | The start date for the utilization report. Format: YYYY-MM-DD |
| end_date (required) | The end date for the utilization report. Format: YYYY-MM-DD |
| dimensions (required) | Comma delimited list of dimensions to include in report. Example: dimensions=date,instance_size |
| metrics (required) | Comma delimited list of metrics to include in report. Example: metrics=running_instances,utilization_hours |
| filters | Filter to apply to report. Filters can be based on dimensions or metrics. Note: the filters query parameter is for a single filter only. Use multiple query parameters for multiple filters. Example: filters=instance_size=@10xlarge Important: the comparison operator should generally be URL encoded (as above) to avoid problems with special characters |
| sort | Comma delimited list of measures, each appended with ASC or DESC to indicate order (order is required). Example: sort=avg_cpu_utilizationASC,regionDESC |
| limit | The maximum number of rows to return. Example: limit=50 |
| offset | Position to start for the results. Example: offset=100 |
| chart | Format the row data for chart purposes (based around dates). Example: chart=1 |
| view_id | If omitted, the user's default view will be applied. Unrestricted users can set view_id=0 to remove view. |

Note: Relative/dynamic date strings supported by the v3 cost reporting endpoint:

| Relative/ Dynamic date strings |
| --- |
| “7 days ago at 00:00:00” |
| “8 days ago at 00:00:00" |
| “10 days ago at 00:00:00” |
| “14 days ago at 00:00:00" |
| “30 days ago at 00:00:00” |
| “31 days ago at 00:00:00" |
| “60 days ago at 00:00:00” |
| “90 days ago at 00:00:00" |
| “beginning of last day” |
| “beginning of last week” |
| “beginning of last month”, “0 of last month” |
| “beginning of last quarter” |
| “beginning of last half” |
| “beginning of last year” |
| “beginning of day”, “beginning of this day” |
| “beginning of week”, “beginning of this week” |
| “beginning of month”, “beginning of this month”, “1st” |
| “beginning of period”, “beginning of this period” |
| “beginning of quarter”, “beginning of this quarter” |
| “beginning of half”, “beginning of this half” |
| “beginning of year”, “beginning of this year” |
| “beginning of next day” |
| “beginning of next week” |
| “beginning of next month” |
| “beginning of next quarter” |
| “beginning of next half” |
| “beginning of next year” |
| “today at 00:00:00” |
| “00:00:00" |
| “23:59:59” |
| “yesterday at 00:00:00" |
| “yesterday at 23:59:59” |
| “end of last day” |
| “end of last week” |
| “end of last month” |
| “end of last quarter” |
| “end of last half” |
| “end of last year” |
| “end of last week to date” |
| “end of last month to date” |
| “end of last quarter to date” |
| “end of last year to date” |
| “end of day”, “end of this day” |
| “end of week”, “end of this week” |
| “end of month”, “end of this month” |
| “end of quarter”, “end of this quarter” |
| “end of half”, “end of this half” |
| “end of year”, “end of this year” |
| “end of next day” |
| “end of next week” |
| “end of next month” |
| “end of next quarter” |
| “end of next half” |
| “end of next year” |

Handling Pagination

To support API performance pagination is implemented when the number of rows in a returned report exceeds 10,000. This typically occurs when users add several dimensions to a report that have high cardinality, such as resource_identifier. The total_results having a value of 10,000 and presence of a pagination object indicates pagination has occurred.

Example pagination object:

```
"pagination": {
  "next": "38bc18d0",
  "previous": "1d93c71e"
```

To navigate backwards and forwards between the pages of a report add a token query parameter to the end of the report URL with the applicable token value (e.g., token=38bc18d0).

Note : You can increase the auto-pagination to 64,000 rows by setting limit=0 in the request parameters

Run a typical utilization report – long-term utilization trends

```
curl ‘https://api.cloudability.com/v3/reporting/util/run?start_date=2022-01-01&end_date=2022-06-30&dimensions=date&metrics=total_bandwidth,avg_cpu_utilization&sort=dateASC&view_id=0’ -u ‘[auth_token]:’"
```

Example Response (subset of results shown)

```
{
  "results": [
    {
      "avg_cpu_utilization": "0.84463",
      "estimated_cost": "393.12",
      "instance_identifier": "i-0a70f28b01f652f14",
      "instance_name": "common-operations-ondemand-r5-large-green-Node",
      "instance_size": "r5.large",
      "total_bandwidth": "2019199735862",
      "utilization_hours": "24",
      "vendor_account_name": "My Account Name"
    },
    {
      "avg_cpu_utilization": "0.830585",
      "estimated_cost": "1071.2",
      "instance_identifier": "i-0278b62c3679c7286",
      "instance_name": "production-operations-spot-16cpu-64gb-green-Node",
      "instance_size": "m5ad.4xlarge",
      "total_bandwidth": "864959230667",
      "utilization_hours": "9",
      "vendor_account_name": "My Account Name"
    }
  ],
  "meta": {
    "dates": {
      "start": "2022-08-30T00:00:00Z",
      "end": "2022-08-30T00:00:00Z"
    },
    "filters": [],
    "metrics": [
      {
        "name": "avg_cpu_utilization",
        "label": "CPU Utilization (Avg)",
        "description": "The average percentage of CPU Utilization...",
        "data_type": "percentage",
        "type": "metric",
        "group": {
          "ID": 9,
          "Key": "compute",
          "Name": "Compute"
        },
        "sub_group": {
          "ID": 12,
          "Key": "processing",
          "Name": "Processing"
        }
      }
    ],
    "dimensions": [
      {
        "name": "instance_identifier",
        "label": "Instance ID",
        "description": "The ID associated with a particular AWS instance.",
        "data_type": "string",
        "type": "dimension",
        "group": {
          "ID": 9,
          "Key": "compute",
          "Name": "Compute"
        },
        "sub_group": {
          "ID": 1,
          "Key": "common",
          "Name": "Common"
        }
      }
    ],
    "aggregates": [
      {
        "name": "avg_cpu_utilization",
        "label": "CPU Utilization (Avg)",
        "description": "The average percentage of CPU Utilization. For EC2, this is the average percentage of allocated EC2 compute units in use for an instance.",
        "data_type": "percentage",
        "type": "metric",
        "value": "0.840516"
      }
    ]
  },
  "offset": 0,
  "pagination": {
    "next": "02f296f8"
  },
  "limit": 2,
  "total_results": 2
}
```

Generate a Report of Utilization Data and Retrieve the Results Later

This option is great for reports that take longer to return (because of high cardinality or timespan), triggering the report generation and then retrieving the results later. The end point to the asynchronous reporting flow takes the same parameters as the synchronous utilization reporting, but instead of waiting and returning the contents of the report, will instead return a request token. The current state of processing is retrieved by requesting the state resource for the given token. When the state is given as "finished", the contents of the report can be retrieved by requesting the results resource for the token. An example of the complete data flow follows the description of the results resource.

```
curl ‘https://api.cloudability.com/v3/reporting/util/enqueue?start_date=2022-01-01&end_date=2022-06-30&dimensions=date&metrics=total_bandwidth,avg_cpu_utilization&sort=dateASC&view_id=0’ -u ‘[auth_token]:’
```

```
curl ‘https://api.cloudability.com/v3/reporting/util/enqueue?start_date=2022-01-01&end_date=2022-06-30&dimensions=date&metrics=total_bandwidth,avg_cpu_utilization&sort=dateASC&view_id=0&useDimensionNames=true' -u ‘[auth_token]:’
```

Example Response

```
{"id":31272850}
```

Query the State of an Asynchronous Report

Valid states of an asynchronous report include: enqueued, running, errored and finished. The state can be queried with the following API call (replace :id with your report ID, as returned from the enqueue call)

```
curl https://api.cloudability.com/v3/reporting/reports/:id/state -u ‘[auth_token]:’
```

Example Response

```
{"status":"running"}
```

Retrieve a Report Previously Generated by Enqueue

Reports that have a state of finished can be retrieved. This returns a standard utilization report object

```
curl ‘https://api.cloudability.com/v3/reporting/reports/:id/results’-u ‘[auth_token]:’]"
```

Important note about pagination: Enqueued reports implement pagination in a similar manner to synchronous utilization reports. The only difference is that pages are sized at 30,000 rows instead of 10,000. This means enqueued reports won’t trigger pagination until the row count exceeds 30,000 rows.

List of sample reports

Below are a few sample reports that can help you with usage of the utilization reports API.

Utilization report with relative dates

```
curl ‘https://api.cloudability.com/v3/reporting/util/run?start_date=0+of+last+month&end_date=end+of+last+month&dimensions=date&metrics=total_bandwidth,avg_cpu_utilization&sort=dateASC&view_id=0’ -u ‘[auth_token]:’
```

Instance type usage trends, returned via CSV

```
 curl -H ‘Accept: text/csv’ ‘https://api.cloudability.com/v3/reporting/util/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=instance_size&metrics=utilization_hours,running_instances&sort=utilization_hoursDESC’ -u ‘[auth_token]:’

```

Underutilized compute optimized instances (report with multiple dimensions and filters)

```
curl 'https://api.cloudability.com/v3/reporting/util/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=instance_size&metrics=utilization_hours%2Crunning_instances&sort=utilization_hoursDESC' -u '[auth_token]:'
```

Typical utilization report (days since launch report)

```

curl ‘https://api.cloudability.com/v3/reporting/util/run?dimensions=launch_date&end_date=2022-08-30&filters=product_name%3D%3DAmazon%20Elastic%20Compute%20Cloud&limit=2&metrics=avg_cpu_utilization&relativePeriods=custom&sort=launch_dateDESC&start_date=2022-08-22&viewId=0’ -u ‘[auth_token]:’
```
