---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "How-To: Download Data via API"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Integrate and Extend"
  - "API Integration"
source_path: "studio/new-uc/howtoguides/integrate-extend/download-data-api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How-To: Download Data via API

**Objective:** Extract data from TBM Studio tables and reports programmatically

**Time estimate:** 10-15 minutes per integration

**When to use:** Extracting data for external analysis, feeding data warehouses, or
integrating with BI tools.

**Prerequisites**

- Valid authentication token and environment ID
- Download/view permissions assigned to your API account
- API URL for the target table or report (obtained from TBM Studio UI)

## Step 1: Get the API URL from TBM Studio

**For tables:**

1. Navigate to the table in TBM Studio
2. Select the Home tab, click Export, then select Show API URL
3. Copy the URL from the modal dialog

**For report tables and charts:**

1. Right-click on the report element (table or chart)
2. Select Show API URL from the context menu
3. Copy the URL for your desired format (TSV, JSON, or Excel)

## Step 2: Download the data

**cURL:**

```
# Download as TSV
curl -X GET "https://customer.apptio.com/biit/api/v2/domains/customer.com/projects/Cost%20Transparency/tables/GL%20Data/dates/Jan:FY2024.tsv" \
 -H "Content-Type: text/tab-separated-values" \
 -H "apptio-opentoken: YOUR_TOKEN" \
 -H "apptio-current-environment: YOUR_ENV_ID" \
 -o output.tsv
```

**Python:**

```
import requests
 
def download_data(token, env_id, api_url, output_path, format="tsv"):
 """
 Download data from TBM Studio via API.
 
 Args:
 token: Authentication token
 env_id: Environment ID
 api_url: API URL obtained from TBM Studio
 output_path: Path to save the downloaded file
 format: Output format ('tsv', 'json', 'xlsx')
 
 Returns:
 str: Path to downloaded file
 """
 content_types = {
 "tsv": "text/tab-separated-values",
 "json": "application/json",
 "xlsx": "application/vnd.openxmlformats-officedocument.spreadsheetml.sheet"
 }
 
 headers = {
 "Content-Type": content_types.get(format, "text/tab-separated-values"),
 "apptio-opentoken": token,
 "apptio-current-environment": str(env_id),
 "app-type": "Flagship",
 "app-version": "NA"
 }
 
 response = requests.get(api_url, headers=headers)
 response.raise_for_status()
 
 with open(output_path, 'wb') as f:
 f.write(response.content)
 
 return output_path
 
# Usage example
download_data(
 token=token,
 env_id=env_id,
 api_url="https://customer.apptio.com/biit/api/v2/domains/customer.com/projects/Cost%20Transparency/tables/GL%20Data/dates/Jan:FY2024.tsv",
 output_path="gl_data.tsv"
)
```

## Customizing the Download

**Changing the delimiter:**

Add the delimiter parameter with a URL-encoded character:

# Use pipe as delimiter (%7C = |)

...tables/GL%20Data/dates/Jan:FY2024.tsv?delimiter=%7C

**Replacing delimiter characters in data:**

If your data contains the delimiter character, use delimiterReplacement:

# Replace pipe characters in data with commas

...?delimiter=%7C&delimiterReplacement=%2C

## Downloading from Published Tables

Published Tables provide stable, schema-controlled datasets ideal for external
integrations.

1. In Project Explorer, right-click on the Published Table
2. Select Show API URL and copy the URL
3. Use the URL with the same download code shown above

Tip: Published Tables are pre-calculated by default, ensuring fast API response
times. Use them instead of ad-hoc report exports for production integrations.

## Supported Download Formats

|  |  |  |  |
| --- | --- | --- | --- |
| **Format** | **Extension** | **Content-Type** | **Best For** |
| Tab-separated | .tsv | text/tab-separated-values | Large files, data processing |
| JSON | .json | application/json | API integrations, web applications |
| Excel | .xlsx | application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | User-friendly analysis |

## Common Pitfalls

- **Date format in URL:** Download URLs use fiscal year format (e.g., Jan:FY2024) which
  may differ from upload format.
- **Large file timeouts:** For very large datasets, use TSV format instead of Excel.
  Consider enabling pre-calculation for Published Tables.
- **Report URLs:** Report API URLs are specific to the reporting element. Changes to
  the report structure may invalidate the URL.

**Parent topic:** [API Integration](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
