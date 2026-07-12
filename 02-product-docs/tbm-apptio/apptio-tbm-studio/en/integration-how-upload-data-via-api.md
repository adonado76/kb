---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "How-To: Upload Data via API"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Integrate and Extend"
  - "API Integration"
  - "How-To: Upload Data via API"
source_path: "SSWRJM/studio/new-uc/howtoguides/integrate-extend/upload-data-via-api.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# How-To: Upload Data via API

Objective: Upload data files to TBM Studio tables programmatically

Time estimate: 10-20 minutes per integration

When to use: Automating monthly data loads, integrating with ETL pipelines, or uploading from systems where DataLink agents cannot be installed.

Prerequisites

- Valid authentication token and environment ID (see Authenticate with the API)
- Upload permissions assigned to your API account
- Data file in supported format (CSV, TSV, CSV.GZ, or TSV.GZ)

## API URL Structure

https://[customerid].apptio.com/biit/api/v1/[domain]/[project]/[table]/[time-period]/[action]

URL Parameters:

| Parameter | Required | Description |
| --- | --- | --- |
| Parameter | Required | Description |
| customerid | Yes | Your Apptio customer ID (e.g., acme) |
| domain | Yes | Your customer domain (e.g., acme.com) |
| project | Yes | Target project name (URL-encoded if contains spaces) |
| table | Yes | Target table name (URL-encoded if contains spaces) |
| time-period | Yes | Apptio date format (e.g., January:2024) or current |
| action | No | append or overwrite (defaults to overwrite) |

Additional Parameters:

| Parameter | Values | Description |
| --- | --- | --- |
| Parameter | Values | Description |
| force | true/false | Override data validation checks. Cannot combine with action in URL—use POST body instead. |

## Steps

Step 1: Prepare your data file

- Ensure data is in CSV or TSV format
- Column headers should match the target table schema
- For large files, compress using gzip (.csv.gz or .tsv.gz)

Step 2: Upload the file

```
curl -X POST "https://customer.apptio.com/biit/api/v1/customer.com/Cost%20Transparency/GL%20Data/January:2024/overwrite" \
 -H "apptio-opentoken: YOUR_TOKEN" \
 -H "apptio-current-environment: YOUR_ENV_ID" \
 -H "app-type: Flagship" \
 -H "app-version: NA" \
 -F "myfile=@/path/to/data.csv"
```

```
import requests
import urllib.parse
 
def upload_data(token, env_id, customer_id, domain, project, table, 
 time_period, file_path, action="overwrite"):
 """
 Upload data to TBM Studio via API.
 
 Args:
 token: Authentication token from login
 env_id: Environment ID
 customer_id: Your Apptio customer ID
 domain: Your domain (e.g., 'customer.com')
 project: Target project name
 table: Target table name
 time_period: Time period (e.g., 'January:2024' or 'current')
 file_path: Path to the data file
 action: 'append' or 'overwrite' (default: 'overwrite')
 
 Returns:
 dict: Response containing md5, length, and fileName
 """
 # URL-encode project and table names
 project_encoded = urllib.parse.quote(project)
 table_encoded = urllib.parse.quote(table)
 
 url = (f"https://{customer_id}.apptio.com/biit/api/v1/"
 f"{domain}/{project_encoded}/{table_encoded}/"
 f"{time_period}/{action}")
 
 headers = {
 "apptio-opentoken": token,
 "apptio-current-environment": str(env_id),
 "app-type": "Flagship",
 "app-version": "NA"
 }
 
 with open(file_path, 'rb') as f:
 files = {'myfile': f}
 response = requests.post(url, headers=headers, files=files)
 
 response.raise_for_status()
 return response.json()
 
# Usage example
result = upload_data(
 token=token,
 env_id=env_id,
 customer_id="acme",
 domain="acme.com",
 project="Cost Transparency",
 table="GL Data",
 time_period="January:2024",
 file_path="/path/to/gl_data.csv"
)
print(f"Upload complete: {result['fileName']}, {result['length']} bytes")
```

## Expected Results

```
{
 "md5": "3727119d89edcdd71377e39e18f3a5e1",
 "length": 13,
 "fileName": "data.csv"
}
```

After upload, the Data > Overview tab in TBM Studio displays "API Data" in the Source field.

## Using Append vs. Overwrite

| Action | Behavior | Use Case |
| --- | --- | --- |
| Action | Behavior | Use Case |
| overwrite | Replaces all existing data in the target time period | Monthly full data refresh |
| append | Adds data to existing records | Incremental updates, adding new records |

## Common Pitfalls

- URL encoding: Project and table names with spaces must be URL-encoded (spaces become %20 or +).
- Date format: Use the exact format Month:Year (e.g., January:2024). "current" uses the current calendar month.
- MIME type: The only supported MIME type is multipart/form-data.
- Table creation: If the target table doesn't exist, the API creates it in the first time period of the project, with data appearing in the specified period.
