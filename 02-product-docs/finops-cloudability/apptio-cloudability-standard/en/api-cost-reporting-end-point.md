---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cost Reporting End Point"
breadcrumb:
  - "Cloudability API"
  - "Cost Reporting End Point"
source_path: "SSVCLNQ/api-v3/cost_reporting_endpoints.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cost Reporting End Point

The cost reporting endpoints are used to dynamically run cost reports and return detailed information about your organization’s cloud spend. These reports have the following features:

- Can be generated in JSON (default) or CSV format
- Help you to manage the saved cost reports
- Have flexible filtering and sorting
- Can select dimensions and metrics to customize as per the reporting needs
- Can add up to 15 dimensions and 8 metrics to an API call
- Pagination when the results exceed 10,000 rows

Cost Reporting End Points

- /reporting/reports/cost for listing current cost reports
- /reporting/cost/run for executing cost reports
- /reporting/cost/measures for listing available cost reporting measures
- /reporting/cost/filters for listing available comparison operators used in filters
- /reporting/cost/enqueue for enqueuing cost reports
- /reporting/reports/:id/state for checking the state of enqueued reports
- /reporting/reports/:id/results for retrieving finished enqueued reports

The Cost Report Object

- results (array) - list of cost row objects, each row comprised of reported dimensions and metrics
- meta (object) - object containing meta information about the report that was run dates (object) - start and end date strings marking the date range of the report filters (array) - list of filters applied to report with detailed information metrics (array) - list of metrics returned in report with detailed information dimensions (array) - list of dimensions returned in report with detailed information aggregates (array) - list of aggregated metrics with detailed information for report
- offset (number) - Position where to start for the results. Default is 0
- limit (number) - Maximum number of cost rows that can be returned
- total_results (number) - Total cost rows returned for executed report

Example Cost Report Object

```
{
  "results": [
   {
     "total_adjusted_amortized_cost": "586411.47",
      "vendor": "Amazon"
    },
    {
     "total_adjusted_amortized_cost": "5334044.71",
      "vendor": "Azure"
    }
     ],
      "meta": {
       "dates": {
       "start": "2022-02-01T00:00:00Z",
       "end": "2022-02-28T00:00:00Z"
      },
       "filters": [
  {
   "comparator": "==",
   "value": "usage",
   "measure": {
   "name": "transaction_type",
   "label": "Transaction Type",
   "description": "Break costs into Usage, One-Time Charges...",
   "data_type": "string",
   "type": "dimension",
    "group": {
     "ID": 2,
     "Key": "billing",
     "Name": "Billing"
     },
     "sub_group": {
     "ID": 6,
     "Key": "usage",
     "Name": "Usage"
      }
     }
    }
    ],
     "metrics": [
                    {
 "name": "total_adjusted_amortized_cost",
 "label": "Cost (Adjusted Amortized)",
 "description": "This cost is calculated using the unblended rate,...",
   "data_type": "currency",
   "type": "metric",
   "group": {
   "ID": 2,
    "Key": "billing",
    "Name": "Billing"
    },
    "sub_group": {
    "ID": 3,
    "Key": "costs",
    "Name": "Costs"
    }
   }
   ],
   "dimensions": [
   {
   "name": "vendor",
   "label": "Vendor",
   "description": "Vendor that provided the product",
   "data_type": "string",
   "type": "dimension",
   "group": {
    "ID": 2,
    "Key": "billing",
    "Name": "Billing"
    },
    "sub_group": {
    "ID": 7,
    "Key": "vendor",
    "Name": "Vendor"
    }
    }
   ],
   "aggregates": [
   {
   "name": "total_adjusted_amortized_cost",
   "label": "Cost (Adjusted Amortized)",
   "description": "This cost is calculated using the unblended rate...",
    "data_type": "currency",
    "type": "metric",
    "value": "5920456.18"
     }
    ]
   },
   "offset": 0,
   "limit": 0,
   "total_results": 2
 }
```

List current cost reports

Retrieve a list of cost reports either owned by or shared with the user or org.

```
curl 'https://api.cloudability.com/v3/reporting/reports/cost' -u '[auth_token]:'
```

Example Response

```
[ 
 { 
   "id": 1, 
      "category": "Cost Summary", 
      "custom": false, 
      "description": "A breakdown of last month's costs by vendor.", 
      "dimensions": [ 
	{ 
   "name": "vendor", 
   "label": "Vendor", 
   "description": "The cloud vendor associated with the cost item. Valid values are Amazon, Azure and GCP.", 
   "data_type": "string", 
   "type": "dimension", 
   "group": { 
   "id": 2, 
   "key": "billing", 
   "name": "Billing" 
   }, 
    "sub_group": { 
    "id": 7, 
    "key": "vendor", 
    "name": "Vendor" 
	} 
	} 
      ], 
	"end_date": "end of last month", 
	"filters": [], 
    "metrics": [ 
    { 
     "name": "unblended_cost", 
     "label": "Cost (Total)", 
	 "description": "This is the default cost metric throughout Cloudability. It is a “cash” metric and simply represents the invoiced amount associated with any cost item as reported by the cloud vendor.", 
     "data_type": "currency", 
     "type": "metric", 
     "group": { 
     "id": 2, 
     "key": "billing", 
     "name": "Billing" 
  }, 
  "sub_group": { 
  "id": 3, 
  "key": "costs", 
  "name": "Costs" 
  } 
   }, 
     ], 
 "order": "desc", 
 "owned_by_user": false, 
 "shared_with_organization": true, 
 "permission": { 
 "actions": [ 
 "read" 
 ] 
  }, 
  "report_dimension_links": [], 
  "secondary_end_date": null, 
  "secondary_start_date": null, 
  "shared": false, 
  "shares": [], 
  "sort_by": "unblended_cost", 
  "star": false, 
  "start_date": "0 of last month", 
  "subscriptions": [], 
  "title": "Costs by Vendor Last Month" 
  } 
   ]
```

Getting list of available measures

To retrieve a list of measures recognized by the server, perform a GET at the measures endpoint. The measures include both dimensions and metrics that can be used in reports.

```
curl ‘https://api.cloudability.com/v3/reporting/cost/measures’ -u ‘[auth_token]:’
```

| Argument | Description |
| --- | --- |
| apply_allocations(Optional) | If apply_allocations is true, only the measures supported by cost sharing are listed. Conversely, if it is false, all measures are included in the list. Allowed: true/false |

Example Response

```
[
 {
   "data_type" : "currency",
    "description" : "Total cost including taxes and credits",
     "group" : {
     "key" : "billing",
    "name" : "Billing"
     },
    "label" : "Total Invoiced Costs",
    "name" : "invoiced_cost",
     "sub_group" : {
     "key" : "costs",
     "name" : "Costs"
     },
     "type" : "metric"
    },
     {
 "data_type" : "string",
 "description" : "The account name for a linked account in consolidated billing",
 "group" : {
 "key" : "billing",
 "name" : "Billing"
   },
 "label" : "Linked Account Name",
 "name" : "linked_account_name",
  "sub_group" : {
  "key" : "vendor",
  "name" : "Vendor"
   },
   "type" : "dimension"
  }
]
```

Getting list of available filter operators

Retrieve a list of recognized filter operators for requesting data

```
curl ‘https://api.cloudability.com/v3/reporting/cost/filters’ -u ‘[auth_token]:’
```

Example Response

```
  [
        "!=@",  # does not contain
        "!=",   # not equals
        "!==",  # strictly not equals*
        "<=",   # less than or equals
        ">",    # greater than
        "[]!=", # not in*
        "===",  # strictly equals*
        "<",    # less than
        "=@",   # contains
        "!^=",  # does not start with
        "!$=",  # does not end with
        "==",   # equals
        ">="    # greater than or equals
        "$=",   # ends with
        "[]=",  #    in*
        "^=",   # starts with
        ]
```

* Note that these operators are available via the API only

Run a cost report

Request Parameters

| Argument | Description |
| --- | --- |
| start_date (required) | The start date for the cost report. Format: YYYY-MM-DD |
| end_date (required) | The end date for the cost report. Format: YYYY-MM-DD |
| dimensions (required) | Comma delimited list of dimensions to include in report. Example: dimensions=vendor,region |
| metrics (required) | Comma delimited list of metrics to include in report. Example: metrics = total_amortized_cost,usage_hours |
| filters | Filter to apply to report. Filters can be based on dimensions or metrics. Note : the filters query parameter is for a single filter only. Use multiple query parameters for multiple filters Example : filters = transaction_type%3D%3Dusage Important: the comparison operator should generally be URL encoded (as above) to avoid problems with special characters |
| sort | Comma delimited list of measures, each appended with ASC or DESC to indicate order (order is required). Example: sort = total_amortized_costASC,regionDESC |
| limit | The maximum number of rows to return. Example: limit = 50 |
| offset | Position to start for the results. Example: offset = 100 |
| chart | Format the row data for chart purposes (based around dates). Example: chart = 1 |
| view_id | If omitted, the user's default view will be applied. Unrestricted users can set view_id = 0 to remove view. |
| applyAllocations | If the optional parameter is set to true, the report will include information on post allocated costs. Conversely, if it is absent or set to false, the report will contain details on per allocated costs. |

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

Pagination is implemented if the number of rows in a returned report exceeds 10,000. This typically occurs when users add several dimensions to a report that have high cardinality, such as resource_identifier. The total_results having a value of 10,000 and presence of a pagination object indicates pagination has occurred.

Example pagination object:

```
"pagination": {
        "next": "38bc18d0",
        "previous": "1d93c71e"
```

To navigate between the pages of a report, add a token query parameter to the end of the report URL with the applicable token ID value (e.g., token = 38bc18d0).

Note : You can increase the auto-pagination to 64,000 rows by setting limit = 0 in the request parameters

Run a typical cost report by - grouped by cloud vendor with cost amortized

```
curl ‘https://api.cloudability.com/v3/reporting/cost/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=vendor&metrics=total_amortized_cost&sort=total_amortized_costASC&filters=transaction_type%3D%3Dusage’ -u ‘[auth_token]:’
```

Example Response

```
{
   "results": [
   {
   "total_amortized_cost": "5334044.71",
   "vendor": "Azure"
   },
         {
   "total_amortized_cost": "593944.59",
   "vendor": "Amazon"
    }
      ],
    "meta": {
    "dates": {
    "start": "2022-02-01T00:00:00Z",
    "end": "2022-02-28T00:00:00Z"
       },
     "filters": [
      {
    "comparator": "==",
    "value": "usage",
    "measure": {
    "name": "transaction_type",
    "label": "Transaction Type",
    "description": "A new dimension ...",
    "data_type": "string",
    "type": "dimension",
      "group": {
       "ID": 2,
       "Key": "billing",
      "Name": "Billing"
          },
      "sub_group": {
      "ID": 6,
      "Key": "usage",
      "Name": "Usage"
      }
       }
        }
     ],
        "metrics": [
        {
       "name": "total_amortized_cost",
       "label": "Cost (Amortized)",
       "description": "This cost is ...",
       "data_type": "currency",
       "type": "metric",
       "group": {
       "ID": 2,
         "Key": "billing",
         "Name": "Billing"
           },
          "sub_group": {
          "ID": 3,
          "Key": "costs",
          "Name": "Costs"
          }
           }
            ],
         "dimensions": [
                 {
     "name": "vendor",
     "label": "Vendor",
     "description": "Vendor that provided the product",
      "data_type": "string",
       "type": "dimension",
       "group": {
      "ID": 2,
       "Key": "billing",
          "Name": "Billing"
            },
         "sub_group": {
         "ID": 7,
         "Key": "vendor",
         "Name": "Vendor"
          }
           }
            ],
          "aggregates": [
            {
      "name": "total_amortized_cost",
      "label": "Cost (Amortized)",
      "description": "This cost is ...",
      "data_type": "currency",
      "type": "metric",
      "value": "5927989.3"
        }
         ]
           },
    "offset": 0,
    "pagination": {},
     "limit": 10000,
     "total_results": 2
}
```

Generate a Report of Cost Data and Retrieve the Results Later

This option is applicable when reports take a long time to return, by triggering the report generation but retrieving the results later. The end point to the asynchronous cost reporting takes the same parameters as the synchronous cost reporting, but instead of waiting and returning the contents of the report, it will instead return a request token.

The current state of processing is retrieved by requesting the state resource for the given token. When the state is given as "finished", the contents of the report can be retrieved by requesting the results resource for the token. An example is given below:

```
curl ‘https://api.cloudability.com/v3/reporting/cost/enqueue?start_date=2022-02-01&end_date=2022-02-28&dimensions=vendor&metrics=total_adjusted_amortized_cost-u ‘[auth_token]:’
```

Example Response

```
{"id":31272850}
```

```
curl ‘https://api.cloudability.com/v3/reporting/cost/enqueue?start_date=2022-02-01&end_date=2022-02-28&dimensions=vendor&metrics=total_adjusted_amortized_cost&useDimensionNames=true -u ‘[auth_token]:’
```

Query the State of an Asynchronous Report

Valid state of an asynchronous report are enqueued, running, errored and finished . This can be queried with the following API call (replace :id with your report ID, as returned from the enqueue call)

```
curl https://api.cloudability.com/v3/reporting/reports/:id/state -u ‘[auth_token]:’

```

Example Response

```
{"status":"running"}
```

Retrieve a Report Previously Generated by Enqueue

Reports that have a state of finished can be retrieved. This returns a standard cost report object.

```
curl ‘https://api.cloudability.com/v3/reporting/reports/:id/results’ -u ‘[auth_token]:’
```

List of sample reports

Below are a few sample reports that can help you with usage of the cost reports API.

Cost report with relative dates

```
curl ‘https://api.cloudability.com/v3/reporting/cost/run?start_date=beginning+of+last+quarter&end_date=end+of+last+quarter&dimensions=vendor&metrics=total_adjusted_amortized_cost’ -u ‘[auth_token]:’
```

Cost report with apply allocations

```
curl ‘https://api.cloudability.com/v3/reporting/cost/run?applyAllocations=true&dimensions=vendor&metrics=total_adjusted_amortized_cost’ -u ‘[auth_token]:’

```

Cost by cloud vendor and region, filtered to usage only and returned via CSV

```
curl -H ‘Accept: text/csv’ ‘https://api.cloudability.com/v3/reporting/cost/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=vendor,region&metrics=total_amortized_cost&filters=transaction_type%3D%3Dusage’ -u ‘[auth_token]:’

```

Cost report with multiple dimensions and filters (amortized cost > 100, region contains ‘us-east-‘)

```
curl ‘https://api.cloudability.com/v3/reporting/cost/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=vendor,region,enhanced_service_name&metrics=total_amortized_cost&filters=total_amortized_cost%3E100&filters=region%3D%40us-east-’ -u ‘[auth_token]:’
```

Going to next cost report page via token

```
curl ‘https://api.cloudability.com/v3/reporting/cost/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=vendor,region,resource_identifier&metrics=total_amortized_cost,usage_hours=&tokenId=e641deae’ -u ‘[auth_token]:’ 
```

Using the “IN” operator to get cost information for two regions

```
curl ‘https://api.cloudability.com/v3/reporting/cost/run?start_date=2022-02-01&end_date=2022-02-28&dimensions=region,enhanced_service_name&metrics=total_amortized_cost&filters=region[]%3Dus-east-1,us-west-2’ -u ‘[auth_token]:’
```
