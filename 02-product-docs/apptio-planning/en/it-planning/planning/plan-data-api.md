---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Plan APIs"
breadcrumb:
  - "Planning"
  - "APIs"
  - "Planning REST APIs Overview"
source_path: "it-planning/planning/plan-data-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Plan APIs

The **Plan APIs** allow you to discover available plans and manage plan‑level expense
data through import and export operations. These APIs form the foundation of most planning data
integrations with Apptio Planning.

Using Plan APIs, you can retrieve plan identifiers, export detailed expense data across multiple
cost types, and import updated plan data using CSV files. Flexible formatting and validation options
support repeatable workflows, bulk updates, and integration with external systems.

## GET /planning/api/v1/plans

**Description**

Retrieves plan names and plan ids for all the plans accessible to the user in the given
environment.

**Request**

```
GET https://app.apptio.com/planning/api/v1/plans
```

Note: Ensure the URL matches your region (e.g., app-eu.apptio.com, app-au.apptio.com).

**Headers**

|  |  |  |
| --- | --- | --- |
| **Header** | **Value** | **Description** |
| apptio-opentoken | <open-token> | Authentication token generated in step 2 of prerequisites |
| apptio-current-environment | <environment-id> | Required environment context from step 3 of prerequisites |

**Response**

```
[ 
 { 
 "id": "0DD868B85BD445EFBDB9F20066F1C7CA", 
 "name": "FY2025 Budget" 
 }, 
 { 
 "id": "1841D23C513444B19B9F1743C5D90445", 
 "name": "FY2024 Budget Final" 
 }, 
 { 
 "id": "29A92951F2F94A5AB9D9556613A4CA6E", 
 "name": "FY2024 October Forecast" 
 } 
]
```

Returns a JSON object with the following properties:

- ***id***: Unique identifier for the plan
- ***name***: Display name of the plan

## POST /planning/api/v1/plans/< Plan Id >/expenses/export

**Description**

Exports expense data for a specific plan. The export is returned as a CSV file based on the
parameters supplied.

**Request**

```
POST https://app.apptio.com/planning/api/v1/plans/<planId>/expenses/export
```

Note: Use
the plans GET api to get Plan Id of plan to export

**Headers** 

|  |  |  |
| --- | --- | --- |
| **Header** | **Value** | **Description** |
| apptio-opentoken | <open-token> | Authentication token generated in step 2 of prerequisites |
| apptio-current-environment | <environment-id> | Required environment contextfrom step 3 of prerequisites |

**Parameters**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Allowed Values** | **Required** | **Description** |
| type | SUMMARY  LABOR\_EXISTING  LABOR\_PLANNED  LABOR\_ACTIVITY  CONTRACT  ASSET\_EXISTING  ASSET\_PLANNED  OTHER | TRUE | Type of plan data to export |
| departmentCode | <code> or blank | FALSE | Filters results to a specific Department; blank exports All Departments |
| basePercentage | ONE  ONE\_HUNDRED | FALSE | Controls how percentage values are formatted:  - ONE – Exports percentages as decimal values. - ONE HUNDRED – Exports percentages as whole numbers.   Default Value: ONE |
| characterEncoding | UTF\_8 SHIFT\_JIS | FALSE | Output file encoding Default Value: UTF\_8 |
| columnDelimiter | COMMA SEMICOLON  TAB | FALSE | CSV delimiter Default Value: COMMA |
| dateFormat | Supported date formats: yyyy-MM-dd  yyyy/MM/dd  yyyy.MM.dd  yy-MM-dd  yy/MM/dd  yy.MM.dd  yy-M-d  yy/M/d  yy.M.d  MM-dd-yyyy  MM/dd/yyyy  MM.dd.yyyy  MM-dd-yy  MM/dd/yy  MM.dd.yy  M-d-yyyy  M/d/yyyy  M.d.yyyy  M-d-yy  M/d/yy  M.d.yy  dd-MM-yyyy  dd/MM/yyyy  dd.MM.yyyy  dd-MM-yy  dd/MM/yy  dd.MM.yy  d-M-yy  d/M/yy  d.M.yy  d-M-yyyy  d/M/yyyy  d.M.yyyy | FALSE | Format of date fields in the output Default Value: yyyy-MM-dd |
| decimalPrecision | ZERO ONE  TWO  THREE  FOUR  FIVE  SIX  SEVEN  EIGHT  FIFTEEN | FALSE | Number of decimals applied to numeric values Default Value: FIFTEEN |
| decimalSymbol | PERIOD COMMA | FALSE | Decimal separator Default Value: PERIOD |
| laborDisplayType | FTE HOUR | FALSE | This parameter is available only if type parameter is LABOR\_ACTIVITY  Default value: HOUR |
| isForReimport | TRUE FALSE | FALSE | Exports data in a format suitable for re-import if set to TRUE  Default Value: FALSE |
| layoutId |  | FALSE | Id of the layout to be exported |
| currency | ORIGINAL\_CURRENCY COMPANY\_CURRENCY | FALSE | Applicable only when Multi-Currency is enabled.  - ORIGINAL\_CURRENCY (default): Exports financial data in the currency specified for each line   item. - COMPANY\_CURRENCY: Exports financial data in the company's default currency, with values   automatically converted where required.   Default Value: ORIGINAL\_CURRENCY |

**Response**

A downloadable CSV file containing the selected plan’s expense details. The export includes the
complete plan schema for the selected plan type.

A bad request error is thrown when using both **isForReimport** and **layoutId**. These two
parameters are not compatible to be used at the same time.

## POST /planning/api/v1/plans/< Plan Id >/expenses/import

**Description**

Imports expense data for a specific plan using a CSV input file. Returns a JSON response
detailing upload success or failure, the number of departments updated, rows added, modified, or
omitted, and any upload issues. The response also includes options to retry the upload while
ignoring issues or to download a help file for issue analysis.

**Request**

```
POST https://app.apptio.com/planning/api/v1/plans/<planId>/expenses/import
```

Note: Ensure the URL matches your region (e.g., app-eu.apptio.com, app-au.apptio.com).

**Headers**

|  |  |  |
| --- | --- | --- |
| **Header** | **Value** | **Description** |
| apptio-opentoken | <open-token> | Authentication token generated in step 2 of prerequisites |
| apptio-current-environment | <environment-id> | Required environment contextfrom step 3 of prerequisites |
| Content-Type | multipart/form-data |  |

**Parameters**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Allowed Values** | **Required** | **Description** |
| type | SUMMARY LABOR\_EXISTING  LABOR\_PLANNED  LABOR\_ACTIVITY  CONTRACT  ASSET\_EXISTING  ASSET\_PLANNED  OTHER | TRUE | Type of plan data to import |
| uploadOperationType | REPLACE\_ALL\_LINE\_ITEMS UPDATE | TRUE | Data upload type:  - REPLACE\_ALL\_LINE\_ITEMS deletes all existing data and replaces it with the data from the uploaded   file. - UPDATE option updates existing data only for lines with a matching Line Item Code. |
| departmentCode | <code> or blank | FALSE | The department code for which plan data should be imported. Default: Leave blank to import data to All Departments. |
| commitWithIssues | TRUE FALSE | FALSE | TRUE — Uploads the CSV even if errors are present. Error details are returned in the response. FALSE — Prevents the CSV from uploading if any errors are detected.  Default: FALSE |
| externalItems | TRUE FALSE | FALSE | TRUE – Imports as External Line Items. Default: FALSE |
| basePercentage | ONE ONE\_HUNDRED | FALSE | Controls how percentage values are formatted:  - ONE – Imports percentages as decimal values. - ONE HUNDRED – Imports percentages as whole numbers.   Default: ONE |
| characterEncoding | UTF\_8 SHIFT\_JIS | FALSE | Input file encoding Default: UTF\_8 |
| columnDelimiter | COMMA SEMICOLON  TAB | FALSE | CSV delimiter Default: COMMA |
| dateFormat | *Supported date formats:* *yyyy-MM-dd*  *yyyy/MM/dd*  *yyyy.MM.dd*  *yy-MM-dd*  *yy/MM/dd*  *yy.MM.dd*  *yy-M-d*  *yy/M/d*  *yy.M.d*  *MM-dd-yyyy*  *MM/dd/yyyy*  *MM.dd.yyyy*  *MM-dd-yy*  *MM/dd/yy*  *MM.dd.yy*  *M-d-yyyy*  *M/d/yyyy*  *M.d.yyyy*  *M-d-yy*  *M/d/yy*  *M.d.yy*  *dd-MM-yyyy*  *dd/MM/yyyy*  *dd.MM.yyyy*  *dd-MM-yy*  *dd/MM/yy*  *dd.MM.yy*  *d-M-yy*  *d/M/yy*  *d.M.yy*  *d-M-yyyy*  *d/M/yyyy*  *d.M.yyyy* | FALSE | Format of date fields in the import file. Default: yyyy-MM-dd |
| decimalPrecision | ZERO ONE  TWO  THREE  FOUR  FIVE  SIX  SEVEN  EIGHT | FALSE | Number of decimals applied to numeric values Default: EIGHT |
| decimalSymbol | PERIOD COMMA | FALSE | Decimal separator Default: PERIOD |

**Body**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Value** | **Required** | **Description** |
| file | <csv file to import> | TRUE | The CSV file to import |

**Response**

```
{ 
  "committed": false, 
  "totalRows": 157, 
  "modifiedRows": 0, 
  "omittedRows": 157, 
  "additionalRows": 0, 
  "updatedCostObjects": 0, 
  "hasChanges": false, 
  "helpFileKey": "BAD29F5238994EFFBA9DB8204A1B4226", 
  "displayName": "Financials", 
  "status": "CANCELLED", 
  "issues": { 
    "OMIT": [ 
      { 
        "type": "noMatchingCostObjectCostCenterFound", 
        "isIncludedInHelpFile": true, 
        "column": "Cost Object", 
	        "count": 157, 
        "errorMessage": "No values found for Cost Object and Cost Center: Cost Object", 
        "instances": [] 
      }, 
      { 
        "type": "invalidBuildCostType", 
        "isIncludedInHelpFile": true, 
        "column": "Cost Type", 
        "count": 155, 
        "errorMessage": "One or more rows in uploaded lines has invalid Cost Type: Build, please include Project Code to consider Build Cost Type: Cost Type", 
        "instances": [] 
      } 
    ], 
    "ADDITION": [], 
    "MODIFY": [ 
      { 
        "type": " 
        ", 
        "isIncludedInHelpFile": false, 
        "column": "unknownColumn", 
        "count": 112, 
        "errorMessage": "Uploaded file contains one or more unknown columns which will be ignored: unknown column", 
        "instances": [ 
          "Project: Invest Type", 
          "Project: Sponsor BU", 
          "Project: Initiative", 
          "Project: Priority", 
          "Project: Project Owner", 
          "Project: Project Group", 
          "Project: Code", 
          "Project Cost Center", 
          "Project Cost Center: Cost Center Owner", 
          "Project Cost Center: Cost Center Owner Title" 
        ] 
      }, 
      { 
        "type": "invalidPrefix", 
        "isIncludedInHelpFile": true, 
        "column": "Line Item Code", 
        "count": 157, 
        "errorMessage": "Invalid prefix format: Line Item Code", 
        "instances": [ 
          "LAP-156", 
          "LAP-2", 
          "LAP-95", 
          "LAP-133", 
          "LAP-132", 
          "LAP-150", 
          "LAP-115", 
          "LAP-33", 
          "LAP-141", 
          "LAP-6" 
        ] 
      } 
    ], 
    "CANCEL": [] 
  }, 
  "uploadId": "4361C20A391A4DA39AF61DD11655ACC8", 
  "totalIssues": 581, 
  "_links": [ 
    { 
      "href": "https://app.apptio.com/planning/api/v1/plans/C66E072F4E9745D29D541236FD28592A/expenses/import?type=SUMMARY&uploadOperationType=REPLACE_ALL_LINE_ITEMS&commitWithIssues=true&externalItems=false", 
      "rel": "commitWithIssues", 
      "method": "POST", 
      "type": "multipart/form-data" 
    }, 
    { 
      "href": "https://app.apptio.com/planning/api/v1/plans/expenses/import/helpfile/BAD29F5238994EFFBA9DB8204A1B4226?filename=response-exportall-oas.csv", 
      "rel": "downloadHelpFile", 
      "method": "GET", 
      "type": "text/csv" 
    } 
  ]
```

Response returns a JSON object with the following properties:

**Response JSON Object Properties**

|  |  |  |  |
| --- | --- | --- | --- |
| **Property** | **Type** | **Values** | **Description** |
| committed | BOOLEAN | TRUE FALSE | TRUE - the file upload is successful. FALSE - the user can continue the upload using commitWithIssue=TRUE or download the help file from the [Links](#plndataapi__links). |
| totalRows | NUMBER |  | Total number of rows in import file. |
| modifiedRows | NUMBER |  | Number of rows that will be modified once upload is processed. Reasons for row modifications can be found under issues.MODIFY in the response. |
| omittedRows | NUMBER |  | Number of rows that will be omitted once upload is processed. Reasons for row omissions can be found under issues.OMIT in the response. |
| additionalRows | NUMBER |  | Number of rows that will be added once upload is processed. Reasons for row additions can be found under issues.ADDITION in the response. |
| updatedDepartments | NUMBER |  | Number of Departments updated. |
| hasChanges | BOOLEAN | TRUE FALSE | TRUE – if there are any changes in line items after upload. FALSE otherwise. |
| helpFileKey | UUID |  | Unique ID for the help file containing upload issues |
| status | STRING | COMPLETE CANCELLED | Upload status |
| issues.OMIT | ARRAY | [Issues](#plndataapi__issues) | Details of issues that caused rows to be omitted. |
| issues.ADDITION | ARRAY | [Issues](#plndataapi__issues) | Details of issues that caused rows to be added. |
| issues.MODIFY | ARRAY | [Issues](#plndataapi__issues) | Details of issues that caused rows to be modified. |
| issues.CANCEL | ARRAY | [Issues](#plndataapi__issues) | Details of issues that caused the upload to be canceled. |
| uploadId | UUID |  | Unique Id for the import action. |
| totalIssues | NUMBER |  | Total number of issues. |
| \_links | ARRAY | [Links](#plndataapi__links) | Included when import errors occur, providing follow-up API requests to download the help file or retry the import while ignoring the identified issues. |

**Issues**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Type** | **Values** | **Description** |
| type | STRING | Sample issues: noMatchingCostObjectCostCenterFound  invalidBuildCostType  illegalCostCenterCostObjectMapping  referenceNotFound  missingEmployee  uploadContainsUnknownColumn | Identifier for error type. |
| isIncludedInHelpFile | BOOLEAN | TRUE FALSE | TRUE – Issue details are included in the help file FALSE – Issue details are not included in the help file |
| column | STRING |  | The name of the column where the issue was detected |
| errorMessage | STRING |  | Details of the issue. |
| instances | ARRAY |  | All occurrences of the specified error type in the import file. Example: If the issue type is uploadContainsUnknownColumn, the instances will list all unknown columns found in the import file. |

**Links**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Type** | **Values** | **Description** |
| href | STRING |  | Endpoint of the linked resource |
| rel | STRING | commitWithIssues downloadHelpFile | commitWithIssue - link to process upload and ignore the issues detected downloadHelpFile – link to download help file containing the issues details |
| method | STRING | GET POST  PUT  PATCH  DELETE | HTTP method to use for the link |
| type | STRING |  | Content-type header expected for the request |

## GET /planning/api/v1/plans/expenses/import/helpfile/<helpfileid>

**Description**

Downloads a help file with detailed information about issues encountered during upload.

Note: Use the helpFileId from the response of Import API

**Request**

```
GET https://app.apptio.com/planning/api/v1/plans/expenses/import/helpfile/<helpfileid>
```

Note: Ensure the URL matches your region (e.g., app-eu.apptio.com, app-au.apptio.com).

**Parameters**

|  |  |  |
| --- | --- | --- |
| **Name** | **Value** | **Description** |
| filename | <filename for the exported data> | If set, the name of the exported file would be filename\_HelpFile.csv. If not set, the name of the exported file would be helpfileid\_HelpFile.csv. |

**Response**

A downloadable CSV file that includes plan import data and inline details of upload issues for
each affected row.

## POST /planning/api/v1/plans/<planId>/expenses/import/async

**Description**

Initiates an asynchronous import of expense data for a specified plan using a CSV file. Returns a
JSON response containing a unique import request UUID and a link to retrieve the import status and
results.

**Request**

POST [https://app.apptio.com/planning/api/v1/plans/<planId>/expenses/import/async](https://app.apptio.com/planning/api/v1/plans/%3cplanId%3e/expenses/import/async "(Opens in a new tab or window)")

Note: Ensure
the URL matches your region (e.g., app-eu.apptio.com, app-au.apptio.com).

**Headers**

|  |  |  |
| --- | --- | --- |
| **Header** | **Value** | **Description** |
| apptio-opentoken | <open-token> | Authentication token generated in step 2 of prerequisites |
| apptio-current-environment | <environment-id> | Required environment contextfrom step 3 of prerequisites |
| Content-Type | multipart/form-data |  |

**Parameters**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Allowed Values** | **Required** | **Description** |
| type | SUMMARY LABOR\_EXISTING  LABOR\_PLANNED  LABOR\_ACTIVITY  CONTRACT  ASSET\_EXISTING  ASSET\_PLANNED  OTHER | TRUE | Type of plan data to import |
| uploadOperationType | REPLACE\_ALL\_LINE\_ITEMS UPDATE | TRUE | Data upload type:  - REPLACE\_ALL\_LINE\_ITEMS deletes all existing data and replaces it with the data from the uploaded   file. - UPDATE option updates existing data only for lines with a matching Line Item Code. |
| departmentCode | <code> or blank | FALSE | The department code for which plan data should be imported. Default: Leave blank to import data to All Departments. |
| commitWithIssues | TRUE FALSE | FALSE | TRUE — Uploads the CSV even if errors are present. Error details are returned in the response. FALSE — Prevents the CSV from uploading if any errors are detected.  Default: FALSE |
| externalItems | TRUE FALSE | FALSE | TRUE – Imports as External Line Items. Default: FALSE |
| basePercentage | ONE ONE\_HUNDRED | FALSE | Controls how percentage values are formatted:  - ONE – Imports percentages as decimal values. - ONE HUNDRED – Imports percentages as whole numbers.   Default: ONE |
| characterEncoding | UTF\_8 SHIFT\_JIS | FALSE | Input file encoding Default: UTF\_8 |
| columnDelimiter | COMMA SEMICOLON  TAB | FALSE | CSV delimiter Default: COMMA |
| dateFormat | *Supported date formats:* *yyyy-MM-dd*  *yyyy/MM/dd*  *yyyy.MM.dd*  *yy-MM-dd*  *yy/MM/dd*  *yy.MM.dd*  *yy-M-d*  *yy/M/d*  *yy.M.d*  *MM-dd-yyyy*  *MM/dd/yyyy*  *MM.dd.yyyy*  *MM-dd-yy*  *MM/dd/yy*  *MM.dd.yy*  *M-d-yyyy*  *M/d/yyyy*  *M.d.yyyy*  *M-d-yy*  *M/d/yy*  *M.d.yy*  *dd-MM-yyyy*  *dd/MM/yyyy*  *dd.MM.yyyy*  *dd-MM-yy*  *dd/MM/yy*  *dd.MM.yy*  *d-M-yy*  *d/M/yy*  *d.M.yy*  *d-M-yyyy*  *d/M/yyyy*  *d.M.yyyy* | FALSE | Format of date fields in the import file. Default: yyyy-MM-dd |
| decimalPrecision | ZERO  ONE  TWO  THREE  FOUR  FIVE  SIX  SEVEN  EIGHT | FALSE | Number of decimals applied to numeric values Default: EIGHT |
| decimalSymbol | PERIOD COMMA | FALSE | Decimal separator Default: PERIOD |

**Body**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Value** | **Required** | **Description** |
| file | <csv file to import> | TRUE | The CSV file to import |

**Response**

```
{ 
      "importId": "11F160D23B68D2A697BDD658E768322C", 
      "_link": 
      { 
            "href":"https://app.apptio.com/planning/api/v1/plans/expenses/import/async/11F160D23B68D2A697BDD658E768322C", 
            "rel": "getStatus", "method": "GET", "type": "application/json"
      } 
}
```

**Response JSON Object Properties**

|  |  |  |  |
| --- | --- | --- | --- |
| **Property** | **Type** | **Values** | **Description** |
| importId | UUID |  | Unique identifier generated for the import request. |
| \_link |  | [link](#plndataapi__asynclink) | URL to retrieve the status and result of the import request. |

**Links**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Type** | **Values** | **Description** |
| href | STRING |  | URL of the linked resource. of the linked resource |
| rel | STRING | getStatus | Defines the relationship of the link. Indicates this link is used to retrieve the import status and result. |
| method | STRING | GET POST  PUT  PATCH  DELETE | HTTP method to be used when calling the link. |
| type | STRING |  | Expected Content-Type header for the request. |

**Errors**

|  |  |  |
| --- | --- | --- |
| 400 | Bad Request | A required parameter is missing, or an import is already in progress for the specified plan. |
| 403 | Unauthorized | The user is not authorized to perform this operation. |
| 404 | Not found | No plan or department was found for the provided plan ID. |

## GET /planning/api/v1/plans/expenses/import/async/<importId>

**Description**

Retrieves the current status of an import request. If the import has reached a final state
(**SUCCESS**, **WARNING**, or **FAIL**), the response also includes the import results and
any associated details.

**Request**

[https://app.apptio.com/planning/api/v1/plans/expenses/import/async/%3CimportId%3E](https://app.apptio.com/planning/api/v1/plans/expenses/import/async/%3CimportId%3E "(Opens in a new tab or window)")

Note: Ensure the URL matches your region (e.g., app-eu.apptio.com,
app-au.apptio.com).

**Headers**

|  |  |  |
| --- | --- | --- |
| **Header** | **Value** | **Description** |
| apptio-opentoken | <open-token> | Authentication token generated in step 2 of prerequisites |
| apptio-current-environment | <environment-id> | Required environment contextfrom step 3 of prerequisites |
| Content-Type | multipart/form-data |  |

**Response**

```
{
  "importId": "11F160D23B68D2A697BDD658E768322C",
  "status": "FAIL",
  "result": {
    "committed": false,
    "totalRows": 2,
    "modifiedRows": 0,
    "omittedRows": 2,
    "additionalRows": 0,
    "updatedDepartments": 0,
    "hasChanges": false,
    "helpFileKey": "E7915BDAF037483994D6FABD7564E174",
    "status": "CANCELLED",
    "issues": {
      "OMIT": [
        {
          "type": "noMatchingCostObjectCostCenterFound",
          "isIncludedInHelpFile": true,
          "column": "Cost Object",
          "count": 2,
          "errorMessage": "No values found for Cost Object and Cost Center: Cost Object",
          "instances": []
        }
      ],
      "ADDITION": [],
      "MODIFY": [
        {
          "type": "uploadContainsUnknownColumn",
          "isIncludedInHelpFile": false,
          "column": "unknownColumn",
          "count": 16,
          "errorMessage": "Uploaded file contains one or more unknown columns which will be ignored: unknown column",
          "instances": [
            "Event ID",
            "Timestamp",
            "User ID",
            "Event Type",
            "Container ID",
            "Area",
            "Container",
            "Item ID",
            "Item Type",
            "Item"
          ]
        }
      ],
      "CANCEL": []
    },
    "uploadId": "14B68FF8F91E412185D04B1CD52BA323",
    "totalIssues": 18
    "_links": [ { "href": "https://app.apptio.com/planning/api/v1/plans/E581EDF2752C434AAF62A63DF4F4B777/expenses/import/async?commitWithIssues=true&basePercentage=ONE&characterEncoding=UTF_8&columnDelimiter=COMMA&dateFormat=yyyy-MM-dd&decimalPrecision=EIGHT&decimalSymbol=PERIOD&type=SUMMARY&departmentCode=AllDept_6DC740A85A9C11E69E6CCC52AF3F6215&externalItems=false&uploadOperationType=UPDATE", 
    "rel": "commitWithIssues", 
    "method": "POST", 
    "type": "multipart/form-data" 
    }, 
    { 
        "href":"https://app.apptio.com/planning/api/v1/plans/expenses/import/helpfile/E7915BDAF037483994D6FABD7564E174?filename=response-export-filter.csv", 
        "rel": "downloadHelpFile", 
        "method": "GET", 
        "type": "text/csv" 
        } 
     ] 
  } 
}
```

**Response JSON Object Properties**

|  |  |  |  |
| --- | --- | --- | --- |
| **Property** | **Type** | **Values** | **Description** |
| importId | UUID |  | Unique identifier generated for the import request. |
| status | STRING | QUEUED RUNNING  SUCCESS  WARNING  FAIL | Current status of the import request. |
| result | JSON object | [Plan API Response](#plndataapi__importjson) | Contains the import result when the request reaches a final status (SUCCESS, WARNING, or FAIL). Returns null while the request is still in progress (QUEUED or RUNNING). |

**Errors**

|  |  |  |
| --- | --- | --- |
| 403 | Unauthorized | The user is not authorized to access the requested import. |
| 404 | Not found | No import request with ID <importId> was found for user <user>. |

**Parent topic:** [Planning REST APIs Overview](../../it-planning/planning/plan-api.html "The Apptio Planning REST APIs provide secure, programmatic access to plans, planning data, metadata, and related artifacts within Apptio Planning. These APIs are designed to support automation and system integrations for planning, forecasting, analysis, governance, and data exchange use cases.")
