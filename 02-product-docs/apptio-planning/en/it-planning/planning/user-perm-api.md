---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "User Permissions APIs"
breadcrumb:
  - "Planning"
  - "APIs"
  - "Planning REST APIs Overview"
source_path: "it-planning/planning/user-perm-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# User Permissions APIs

The **User Permissions APIs** enable export and import of plan‑level and global
permission data. These APIs support automated access management and validation of user permissions
within Apptio Planning.

Using these APIs, you can manage permissions in bulk via CSV files, review existing access
configurations, and troubleshoot permission‑related issues using detailed help files generated
during import operations.

## POST planning/api/v1/userpermissions/export

**Description**

Exports plan level user permission data. The export is returned as a CSV file based on the
parameters supplied.

**Request**

```
POST https://app.apptio.com/planning/api/v1/userpermissions/export
```

Note: Ensure the URL matches your region (e.g., app-eu.apptio.com, app-au.apptio.com). Use the plans
GET api to get Plan Id of plan to export.

**Parameters**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Allowed Values** | **Required** | **Description** |
| planId | planID from the response of GET Plans API | FALSE | The ID of the plan whose user permissions should be exported. If not specified, the export will include global reference data permissions. |
| basePercentage | ONE ONE\_HUNDRED | FALSE | Format in which percentage has to be displayed. Default: ONE |
| characterEncoding | UTF\_8 SHIFT\_JIS | FALSE | Input file encoding Default: UTF\_8 |
| columnDelimiter | COMMA SEMICOLON  TAB | FALSE | CSV delimiter Default: COMMA |
| dateFormat | *Supported date formats:* *yyyy-MM-dd*  *yyyy/MM/dd*  *yyyy.MM.dd*  *yy-MM-dd*  *yy/MM/dd*  *yy.MM.dd*  *yy-M-d*  *yy/M/d*  *yy.M.d*  *MM-dd-yyyy*  *MM/dd/yyyy*  *MM.dd.yyyy*  *MM-dd-yy*  *MM/dd/yy*  *MM.dd.yy*  *M-d-yyyy*  *M/d/yyyy*  *M.d.yyyy*  *M-d-yy*  *M/d/yy*  *M.d.yy*  *dd-MM-yyyy*  *dd/MM/yyyy*  *dd.MM.yyyy*  *dd-MM-yy*  *dd/MM/yy*  *dd.MM.yy*  *d-M-yy*  *d/M/yy*  *d.M.yy*  *d-M-yyyy*  *d/M/yyyy*  *d.M.yyyy* | FALSE | Format of date fields in the import file. Default: yyyy-MM-dd |
| decimalPrecision | ZERO ONE  TWO  THREE  FOUR  FIVE  SIX  SEVEN  EIGHT | FALSE | Number of decimals applied to numeric values Default: EIGHT |
| decimalSymbol | PERIOD COMMA | FALSE | Decimal separator Default: PERIOD |

**Response**

A downloadable CSV file containing the selected plan’s variance analysis details.

## POST /planning/api/v1/userpermissions/import

**Description**

Imports plan level user permission or global Cost Object Permissions.

**Request**

```
POST https://app.apptio.com/planning/api/v1/userpermissions/import
```

Note: Ensure the URL matches your region (e.g., app-eu.apptio.com, app-au.apptio.com). Use the plans
GET api to get Plan Id of plan to export.

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
| planId | planID from the response of GET Plans API | FALSE | The ID of the plan whose user permissions should be imported. If not specified, import global reference data permissions. |
| commitWithIssues | TRUE FALSE | FALSE | TRUE — Uploads the CSV even if errors are present. Error details are returned in response. FALSE — Prevents the CSV from uploading if any errors are detected.  Default: FALSE |
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
"totalRows": 0, 
"modifiedRows": 0, 
"omittedRows": 0, 
"additionalRows": 0, 
"updatedDepartments": -1, 
"hasChanges": false, 
"helpFileKey": null, 
"status": "CANCELLED", 
"issues": { 
"OMIT": [], 
"ADDITION": [], 
"MODIFY": [ {
"type": "uploadContainsUnknownColumn",
"isIncludedInHelpFile": false, 
"column": "unknownColumn", 
"count": 35, 
"errorMessage": "Uploaded file contains one or more unknown columns which will be ignored: unknown column", 
"instances": [ "Account", "Cost Center", "Project Code", "Cost Type", "Location", "Location Name", "Vendor", "Vendor Name", "Description", "Transaction ID"] 
} ], 
"CANCEL": [] }, 
"uploadId": "F74974DEB2974B7E94D3351C73CACD80", 
"totalIssues": 35, 
"_links": [ {
"href":"http://app.apptio.com/planning/api/v1/userpermissionsimportcommitWithIssues=true&planId=D7BAC53A969D49EE836DB41D51EB746&basePercentage=ONE&columnDelimiter=COMMA&dateFormat=yyy-MM-dd", 
"rel": "commitWithIssues", 
"method": "POST", 
"type": "multipart/form-data" 
} ] 
}
```

**Response JSON Object Properties**

|  |  |  |  |
| --- | --- | --- | --- |
| **Property** | **Type** | **Values** | **Description** |
| committed | BOOLEAN | TRUE FALSE | TRUE - the file upload is successful. FALSE - the user can continue the upload using commitWithIssue=TRUE or download the help file from the attached links. |
| totalRows | NUMBER |  | Total number of rows in import file. |
| modifiedRows | NUMBER |  | Number of rows that will be modified once upload is processed. Reasons for row modifications can be found under issues.MODIFY in response. |
| omittedRows | NUMBER |  | Number of rows that will be omitted once upload is processed. Reasons for row omissions can be found under issues.OMIT in response. |
| additionalRows | NUMBER |  | Number of rows that will be added once upload is processed. Reasons for row additions can be found under issues.ADDITION in the response. |
| hasChanges | BOOLEAN | TRUE FALSE | TRUE – if there are any changes in line items after upload.  FALSE otherwise. |
| helpFileKey | UUID |  | Unique ID for the help file containing upload issues |
| status | STRING | COMPLETE CANCELLED | Upload status |
| issues.OMIT | ARRAY | [Issues](#upapi__upimpli) | Details of issues that caused rows to be omitted. |
| issues.ADDITION | ARRAY | [Issues](#upapi__upimpli) | Details of issues that caused rows to be added. |
| issues.MODIFY | ARRAY | [Issues](#upapi__upimpli) | Details of issues that caused rows to be modified. |
| issues.CANCEL | ARRAY | [Issues](#upapi__upimpli) | Details of issues that caused the upload to be canceled. |
| uploadId | UUID |  | Unique Id for the import action. |
| totalIssues | NUMBER |  | Total number of issues. |
| \_links | ARRAY | [links](#upapi__issues) | Included when import errors occur, providing follow-up API requests to download the help file or retry the import while ignoring the identified issues. |

**Issues**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Type** | **Values** | **Description** |
| type | STRING | *Sample issues:* *noMatchingCostObjectCostCenterFound*  *invalidBuildCostType*  *illegalCostCenterCostObjectMappingreferenceNotFound*  *missingEmployee*  *UploadContainsUnknownColumn* | Identifier for error type. |
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

## GET /planning/api/v1/userpermissions/import/helpfile/<helpfileId>

**Description**

Downloads a help file with detailed information about issues encountered during permission
upload.

Note: Use the helpFileId from the response of Import API

**Request**

```
https://app.apptio.com/planning/api/v1/userpermissions/import/helpfile/%3ChelpfileId
```

Note: Ensure the URL matches your region (e.g., app-eu.apptio.com, app-au.apptio.com).

**Parameters**

|  |  |  |
| --- | --- | --- |
| **Name** | **Value** | **Description** |
| filename | <filename for the exported data> | If set, the name of the exported file would be filename\_HelpFile.csv.  If not set, the name of the exported file would be helpfileid\_HelpFile.csv. |

**Response**

A downloadable CSV file that includes user permission import data and inline details of upload
issues for each affected row.

**Parent topic:** [Planning REST APIs Overview](../../it-planning/planning/plan-api.html "The Apptio Planning REST APIs provide secure, programmatic access to plans, planning data, metadata, and related artifacts within Apptio Planning. These APIs are designed to support automation and system integrations for planning, forecasting, analysis, governance, and data exchange use cases.")
