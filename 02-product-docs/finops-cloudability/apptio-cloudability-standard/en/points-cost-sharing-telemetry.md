---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cost Sharing Telemetry"
breadcrumb:
  - "Cloudability API"
  - "Cost Sharing End Points"
  - "Cost Sharing Telemetry"
source_path: "SSVCLNQ/api-v3/telemetry-cost-sharing.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cost Sharing Telemetry

Summary

The Telemetry API manages usage-based metrics for cost allocation, enabling data-driven distribution based on actual resource consumption patterns.

Core Functions

The core functions for Telemetry include:

- Upload telemetry data via CSV
- Retrieve uploaded telemetry data
- Download telemetry files
- Delete telemetry records
- Access metric meta data
- Query available destinations

Data Requirements

Following data requirements need to be met for Telemetry API.

- Date: Time stamp for measurements
- Category: Business dimension mapping
- Value: Actual metric measurement
- CSV format validation
- Business dimension index mapping

Integration Points

The integration points for telemetry API include the following:

- Links with allocation rules
- Maps to business dimensions
- Supports custom metrics
- Enables dynamic cost distribution
- Maintains historical data

End Points

POST /cost-sharing/telemetry-data?businessDimensionIndex={{businessDimensionIndex}}

This API is used for uploading Telemetry data in a CSV format for a specific Business Dimension.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 not already used in any allocation |
| files | CSV file containing the Telemetry Data | REQUIRED | A CSV file in a valid format. |

Telemetry File Specifications

| Collumn | Collumn Index | Nullable | Description |
| --- | --- | --- | --- |
| Date | 1 | No | A yyyy-MM-dd string. The value can be specified within and also without double-quotes. So “2025-01-25” AND 2025-01-25, both are valid values. When an uploaded Telemetry File is downloaded, the downloaded copy with have the date within double-quotes (eg. “2025-01-25”. |
| Business Dimension | 2 | No | The name of the column must be the name of a business dimension. The contents of the column must be values of that business dimension. |
| Metrics | 3 | No | Custom metric. Could be cost or usage metric, or other metric that may be relevant to the user or data source. Used for allocation. Column name should be descriptive of the metric. Must not be null or empty : The field should contain a value and cannot be left blank. Negative values are not supported: The field must contain a numeric value that is non-negative (i.e., zero or positive numbers are allowed) |

Example Request

```
curl --request POST \
      --url 'https://api.cloudability.com/v3/cost-sharing/telemetry-data?businessDimensionIndex=20' \
      --header 'accept: application/json, text/plain, */*' \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'content-type: multipart/form-data' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
      --form files=@/Downloads/telemetry_data.csv
```

Example Response

```
{
 "result": {
 "message": "telemetry data files uploaded successfully"
}
}
```

GET /cost-sharing/telemetry-data?businessDimensionIndex={{businessDimensionIndex}}

This API is used for retrieving the Telemetry data from the database for a specific Business Dimension previously uploaded through a CSV file.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The allocations will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 not already used in any allocation |

Example Request

```
curl --request GET \
      --url 'https://api.cloudability.com/v3/cost-sharing/telemetry-data?businessDimensionIndex=20' \
      --header 'accept: application/json, text/plain, */*' \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'content-type: multipart/form-data; \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
			  
```

Example Response

```
{
 "result": [
{
 "fileName": "telemetry_data.csv",
 "createdAt": "2025-01-27T12:27:06.000Z",
 "updatedAt": "2025-01-27T12:27:06.000Z"
}
				]
				}
			  
```

GET /cost-sharing/telemetry-data/download?fileName=${fileName}&businessDimensionIndex=${businessDimensionIndex}

This API is used to download the Telemetry data file previously uploaded for the given Business Dimension.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 not already used in any allocation |
| fileName | The name of the CSV file to be downloaded | REQUIRED | Text with a .csv extension |

Example Request

```
curl --request GET \
      --url 'https://api.cloudability.com/v3/cost-sharing/telemetry-data/download?fileName=telemetry_data.csv&businessDimensionIndex=20' \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
```

Example Response

```
Date,Category,Number of API Requests
 """2024-07-01""",prod_test,50
 """2024-07-01""",modeling,25
 """2024-07-01""",operative,25
 """2024-07-02""",apptio,50
 """2024-07-02""",ibm,25
 """2024-07-02""",TBM,25
			  
```

DELETE /cost-sharing/telemetry-data

This API is used for deleting one or more Telemetry data file(s) from the database for a specific Business Dimension previously uploaded through a CSV file.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 not already used in any allocation |
| fileNames | List of one or more names of the files to be deleted | REQUIRED | List of file names |

Example Request

```
curl --request DELETE \
     --url https://api.cloudability.com/v3/cost-sharing/telemetry-data \
     --header 'accept: application/json, text/plain, */*' \
     --header 'authorization: ${JWT_TOKEN}' \
     --header 'content-type: application/json' \
     --header 'x-fd-env-id: ${ENVIRONMENT_ID}' \
     --data '{
 "fileNames": [
 "telemetry_data.csv"
 ],
 "businessDimensionIndex": 20
 }'
		s
```

Example Response

```
{
 "result": []
}
```

GET /cost-sharing/allocation/${businessDimensionIndex}/metrics-metadata

This API is used for retrieving the metadata of the metrics for which the data was uploaded through Telemetry files.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 not already used in any allocation |

Example Request

```
curl --request GET \
      --url https://api.cloudability.com/v3/cost-sharing/allocation/14/metrics-metadata \
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
```

Example Response

```
{
 "telemetryOptions": [
{
 "telemetryDataSource": "custom",
 "telemetryMetrics": [
{
 "metricName": "Number of API Requests",
 "metricIndex": 1
},
{
 "metricName": "Share",
 "metricIndex": 2
}
]
}
]
}
	
```

GET /cost-sharing/telemetry-destinations?businessDimensionIndex=${businessDimensionIndex}&metricIndex=${metricIndex}

This API is used for retrieving the Telemetry destinations for the given Business Dimension and Metric Index.

Query Arguments

| Parameter | Description | Default | Allowed |
| --- | --- | --- | --- |
| businessDimensionIndex | The allocation will be created for this Business Dimension Index | REQUIRED | Numeric values between 1 - 25 not already used in any allocation |
| metricIndex | Index of the metric | REQUIRED | Numeric value |

Example Request

```
curl --request GET \
      --url 'https://api.cloudability.com/v3/cost-sharing/telemetry-destinations?businessDimensionIndex=20&metricIndex=1'\
      --header 'authorization: ${JWT_TOKEN}' \
      --header 'x-fd-env-id: ${ENVIRONMENT_ID}'
```

Example Response

```
{
  "result": [
  "test",
  "modeling",
  "operative",
  "apptio",
  "ibm",
  "TBM"
 ]
 }
```
