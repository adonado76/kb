---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Spend Management APIs"
breadcrumb:
  - "Planning"
  - "APIs"
  - "Planning REST APIs Overview"
source_path: "it-planning/planning/spnd-mgmt-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Spend Management APIs

The **Spend Management APIs** support the export and import of actuals data used in
planning and financial analysis.

You can export actuals for specific periods and years or import update actuals using structured
CSV files. Import operations include robust validation, error reporting, and help file generation to
assist with correcting data issues.

## POST planning/api/v1/spendmanagement/export

**Description**

Exports Actuals from Spend Management. The export is returned as a CSV file based on the
parameters supplied.

**Request**

```
POST https://app.apptio.com/planning/api/v1/spendmanagement/export
```

Note: Ensure the URL matches your region (e.g., app-eu.apptio.com, app-au.apptio.com).

**Parameters**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Allowed Values** | **Required** | **Description** |
| departmentcode |  | FALSE | Code of the department for which Spend Management data is to be exported  Default: All Departments |
| period | 1  2  3  4  5  6  7  8  9  10  11  12  13 | TRUE | Month or period for which Spend Management data is to be exported |
| year |  | TRUE | Year for which Spend Management data is to be exported |
| basePercentage | ONE  ONE\_HUNDRED | FALSE | Controls how percentage values are formatted:   - ONE – Imports percentages as decimal values. - ONE HUNDRED – Imports percentages as whole numbers.   Default: ONE |
| characterEncoding | UTF\_8  SHIFT\_JIS | FALSE | Input file encoding  Default: UTF\_8 |
| columnDelimiter | COMMA  SEMICOLON  TAB | FALSE | CSV delimiter  Default: COMMA |
| dateFormat | *Supported date formats:* *yyyy-MM-dd*  *yyyy/MM/dd*  *yyyy.MM.dd*  *yy-MM-dd*  *yy/MM/dd*  *yy.MM.dd*  *yy-M-d*  *yy/M/d*  *yy.M.d*  *MM-dd-yyyy*  *MM/dd/yyyy*  *MM.dd.yyyy*  *MM-dd-yy*  *MM/dd/yy*  *MM.dd.yy*  *M-d-yyyy*  *M/d/yyyy*  *M.d.yyyy*  *M-d-yy*  *M/d/yy*  *M.d.yy*  *dd-MM-yyyy*  *dd/MM/yyyy*  *dd.MM.yyyy*  *dd-MM-yy*  *dd/MM/yy*  *dd.MM.yy*  *d-M-yy*  *d/M/yy*  *d.M.yy*  *d-M-yyyy*  *d/M/yyyy*  *d.M.yyyy* | FALSE | Format of date fields in the import file.  Default: yyyy-MM-dd |
| decimalPrecision | ZERO  ONE  TWO  THREE  FOUR  FIVE  SIX  SEVEN  EIGHT | FALSE | Number of decimals applied to numeric values  Default: EIGHT |
| decimalSymbol | PERIOD  COMMA | FALSE | Decimal separator  Default: PERIOD |

**Response**

A downloadable CSV file containing the selected plan’s variance analysis details.

## POST /planning/api/v1/spendmanagement/import

**Description**

Imports actuals data into Spend Management using a CSV input file. Returns a JSON response
detailing upload success or failure. The response also includes options to download a help file for
issue analysis.

**Request**

```
POST https://app.apptio.com/planning/api/v1/spendmanagement/import
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
| period | 1  2  3  4  5  6  7  8  9  10  11  12  13 | TRUE | Month or period for which Spend Management data is to be exported |
| year |  | TRUE | Year for which Spend Management data is to be exported |
| commitWithIssues | TRUE  FALSE | FALSE | TRUE — Uploads the CSV even if errors are present. Error details are returned in the response.  FALSE — Prevents the CSV from uploading if any errors are detected.  Default: FALSE |
| uploadOperationType | REPLACE\_ALL\_LINE\_ITEMS  UPDATE | TRUE | Type of upload to be performed |
| basePercentage | ONE  ONE\_HUNDRED | FALSE | Controls how percentage values are formatted:   - ONE – Imports percentages as decimal values. - ONE HUNDRED – Imports percentages as whole numbers.   Default: ONE |
| characterEncoding | UTF\_8  SHIFT\_JIS | FALSE | Input file encoding  Default: UTF\_8 |
| columnDelimiter | COMMA  SEMICOLON  TAB | FALSE | CSV delimiter  Default: COMMA |
| dateFormat | *Supported date formats:*  *yyyy-MM-dd*  *yyyy/MM/dd*  *yyyy.MM.dd*  *yy-MM-dd*  *yy/MM/dd*  *yy.MM.dd*  *yy-M-d*  *yy/M/d*  *yy.M.d*  *MM-dd-yyyy*  *MM/dd/yyyy*  *MM.dd.yyyy*  *MM-dd-yy*  *MM/dd/yy*  *MM.dd.yy*  *M-d-yyyy*  *M/d/yyyy*  *M.d.yyyy*  *M-d-yy*  *M/d/yy*  *M.d.yy*  *dd-MM-yyyy*  *dd/MM/yyyy*  *dd.MM.yyyy*  *dd-MM-yy*  *dd/MM/yy*  *dd.MM.yy*  *d-M-yy*  *d/M/yy*  *d.M.yy*  *d-M-yyyy*  *d/M/yyyy*  *d.M.yyyy* | FALSE | Format of date fields in the import file.  Default: yyyy-MM-dd |
| decimalPrecision | ZERO  ONE  TWO  THREE  FOUR  FIVE  SIX  SEVEN  EIGHT | FALSE | Number of decimals applied to numeric values  Default: EIGHT |
| decimalSymbol | PERIOD  COMMA | FALSE | Decimal separator  Default: PERIOD |

**Body**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Allowed Values** | **Required** | **Description** |
| file |  | TRUE | File to be uploaded |

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
			  "MODIFY": [ 	
				  { "type": "uploadContainsUnknownColumn",
 				   "isIncludedInHelpFile": false, 
				    "column": "unknownColumn", 
				    "count": 35, "errorMessage": "Uploaded file contains one or more unknown columns which will be ignored: unknown column", 
				    "instances": [ 
						"Account", 
						"Cost Center", 
						"Project Code", 
						"Cost Type", 
						"Location", 
						"Location Name", 
						"Vendor", 
						"Vendor Name", 
						"Description", 
						"Transaction ID" 
						] 
				   } 
			   ], 
			    "CANCEL": [] 
}, 
"uploadId": "F74974DEB2974B7E94D3351C73CACD80", 
"totalIssues": 35, 
"_links": [ 
		 { 
		 "href":"http://app.apptio.com/planning/api/v1/spendmanagement/importcommitWithIssues=true&planId=D7BAC53A969D49EE836DB41D51FEB746&basePercentage=ONE&columnDelimiter=COMMA&dateFormat=yyyy-MM-dd", 	
		 "rel": "commitWithIssues", "method": "POST", "type": "multipart/form-data" 
		 } 
	    ] 
}
```

Returns a JSON object with the following properties:

**Response JSON Object Properties**

|  |  |  |  |
| --- | --- | --- | --- |
| **Property** | **Type** | **Values** | **Description** |
| committed | BOOLEAN | TRUE  FALSE | TRUE - the file upload is successful.  FALSE - the user can continue the upload using commitWithIssue=TRUE or download the help file from the [Links](#spdmgmapi__link). |
| totalRows | NUMBER |  | Total number of rows in import file. |
| modifiedRows | NUMBER |  | Number of rows that will be modified once upload is processed.  Reasons for row modifications can be found under issues.MODIFY in response. |
| omittedRows | NUMBER |  | Number of rows that will be omitted once upload is processed.  Reasons for row omissions can be found under issues.OMIT in the response. |
| additionalRows | NUMBER |  | Number of rows that will be added once upload is processed.  Reasons for row additions can be found under issues.ADDITION in the response. |
| hasChanges | BOOLEAN | TRUE  FALSE | TRUE – if there are any changes in line items after upload.  FALSE otherwise. |
| helpFileKey | UUID |  | Unique ID for the help file containing upload issues |
| status | STRING | COMPLETE  CANCELLED | Upload status |
| issues.OMIT | ARRAY | [Issues](#spdmgmapi__is) | Details of issues that caused rows to be omitted. |
| issues.ADDITION | ARRAY | [Issues](#spdmgmapi__is) | Details of issues that caused rows to be added. |
| issues.MODIFY | ARRAY | [Issues](#spdmgmapi__is) | Details of issues that caused rows to be modified. |
| issues.CANCEL | ARRAY | [Issues](#spdmgmapi__is) | Details of issues that caused the upload to be canceled. |
| uploadId | UUID |  | Unique Id for the import action. |
| totalIssues | NUMBER |  | Total number of issues. |
| \_links | ARRAY | [Links](#spdmgmapi__link) | Included when import errors occur, providing follow-up API requests to download the help file or retry the import while ignoring the identified issues. |

**Issues**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Type** | **Values** | **Description** |
| type | STRING | Sample issues: noMatchingCostObjectCostCenterFound  invalidBuildCostType  illegalCostCenterCostObjectMapping  referenceNotFound  missingEmployee  uploadContainsUnknownColumn | Identifier for error type. |
| isIncludedInHelpFile | BOOLEAN | TRUE  FALSE | TRUE – Issue details are included in the help file  FALSE – Issue details are not included in the help file |
| column | STRING |  | The name of the column where the issue was detected |
| errorMessage | STRING |  | Details of the issue. |
| instances | ARRAY |  | All occurrences of the specified error type in the import file.    Example: If the issue **type** is **uploadContainsUnknownColumn**, the **instances**will list all unknown columns found in the import file.  ``` "instances": [ "Project: Invest Type",  "Project: Sponsor BU",  "Project: Initiative", "Project: Priority", "Project: Project Owner",  "Project: Project Group",  "Project: Code", "Project Cost Center",  "Project Cost Center: Cost Center Owner", "Project Cost Center: Cost Center Owner Title"  ] ``` |

**Links**

|  |  |  |  |
| --- | --- | --- | --- |
| **Name** | **Type** | **Values** | **Description** |
| href | STRING |  | Endpoint of the linked resource |
| rel | STRING | commitWithIssues downloadHelpFile | commitWithIssue - link to process upload and ignore the issues detected  downloadHelpFile – link to download help file containing the issues details |
| method | STRING | GET  POST  PUT  PATCH  DELETE | HTTP method to use for the link |
| type | STRING |  | Content-type header expected for the request |

## GET /planning/api/v1/plans/expenses/import/helpfile/<helpfileid>

**Description**

Downloads a help file with detailed information about issues encountered during upload.

Note: Use
the helpFileId from the response of Import API

**Request**

```
GET https://app.apptio.com/planning/api/v1/spendmanagement/import/helpfile/%3Chelpfileid%3E>
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
