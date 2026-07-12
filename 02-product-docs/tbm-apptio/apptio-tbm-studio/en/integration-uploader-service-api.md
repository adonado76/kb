---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Uploader Service API"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Integrate and Extend"
  - "API Integration"
  - "Uploader Service API"
source_path: "SSWRJM/studio/admin/uploader-service-api.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Uploader Service API

*Applies to : TBM Studio 12.0 and later*

- Individual large files are uploaded as multiple parts.
- Uploads can be cancelled.
- Status of a multi-part upload is included in the final incorporation step.
- Multiple uploads can be checked in as a single group to the target Apptio project.
- Parallel uploading of multiple parts is supported.
- Asynchronous processing of data in Apptio project is supported.
- All data transport is handled in-region and is compliant with data localization laws.

For a sample implementation see the Uploader Service API Tutorial .

## Uploader Service endpoints

- North America - https://datalink.apptio.com/uls
- EU - https://datalink-eu.apptio.com/uls
- APAC - https://datalink-au.apptio.com/uls
- Middle East - https://datalink-me.apptio.com/uls

## REST API syntax

The base URL for API calls is as follows:

<ULS_URL>/api/<VERSION>

Currently, there is one valid value for VERSION : v1. For example, in North America the base URL would be: https://datalink.apptio.com/uls/v1. API endpoints consume and produce JSON except where otherwise noted.

## Authentication with Apptio opentoken

1. Go to Enhanced Access Administration APIs to retrieve an Apptio opentoken.
1. After you have the token, add following headers to your request:

| Header Name | Contents |
| --- | --- |
| app-type | "UploaderService" |
| app-version | "1.00.0" |
| apptio-opentoken | A valid opentoken representing the logged in user |
| apptio-current-environment | The FrontDoor environment to which this request is being made |

## REST APIs

- single-part upload
- multi-part upload
- processing upload
- get processing status

## Initiate a single-part upload

Method : POST <ULS_URL> /v1/upload?partSize= <long>

Content-type : multipart/form-data

Body :

```
"metadata": ( { "name": "
<TABLE_NAME>
" } )
"data": ()

```

Return Codes:

200 - Success

400 - Bad JSON body

404 - Incorrect API URL

415 - Unsupported media type

500 - Internal Upload Error (contact Support)

Response :

N/A

## Initiate a multi-part upload

Method : POST <ULS_URL> /v1/upload/multipart

Content-type : application/json

```

{
	"name":"
<TABLE_NAME>
"
}
```

Return Codes:

200 - Success

400 - Bad JSON body

404 - Incorrect API URL

500 - Internal Upload Error (contact Support)

Response (JSON) :

```

{
	"uploadId":""
<UPLOAD_ID>
", 
	"multipartId":"
<MULTIPART_ID>
"
}

```

## Uploading parts

Method : PUT <ULS_URL> /v1/upload/multipart/ <UPLOAD_ID> /part/ <PART_ID> ?lastPart=<Bool>&md5=<String>&partSize=<long>

Parameters :

| Name | Type | Description |
| --- | --- | --- |
| partId | Integer | A sequence number e.g 1, 2 or 3 |
| lastPart | Boolean | true : This is the last part. The length of the input stream of the last part can be less than 5MB. false : Not the last part. The length of the input stream that's not the last part can't be less than 5MB. |
| md5 | String | The base64-encoded 128-bit MD5 digest of the part data |
| partSize | long | The length of the input stream in bytes. |

Content-type : Depending the type of the body stream, the following types are supported:

text/plain

application/json

application/zip

application/octet-stream

Body :

The input stream in the body.

Return Codes :

200 - Success

204 - Success

400 - Invalid part size (must be between 5MB and 5GB)

404 - Incorrect API URL or bad upload ID

500 - Internal Upload Error (contact Support)

Response (JSON) :

Errors if any.

## Finalize a multi-part upload

Method : POST <ULS_URL> /v1/upload/multipart/ <UPLOAD_ID>

Return Codes :

200 - Success

404 - Incorrect API URL

500 - Internal Upload Error (contact Support)

Response (JSON ):

Errors if any.

## Abort a multi-part upload

Method : DELETE <ULS_URL> /v1/upload/multipart/ <UPLOAD_ID>

Return Codes :

200 - Success

404 - Incorrect API URL

500 - Internal Upload Error (contact Support)

Response (JSON) :

Errors if any.

## Initiate final processing of an upload

```
POST 
<ULS_URL>
/v1/process
```

Body :

```

{
	"metadata": {
		"period": "<Apptio time period e.g. Jan:FY2018>",
		"domain": "<Customer domain e.g. customer.apptio.com>",
		"name": "<File name e.g. file.tsv, file.zip, etc.>",
		"host": "<Apptio host name>",
		"format": "<File format e.g. tsv, csv, etc.>",
		"project": "<Project Name>",
		"source": "<Data source e.g. S3>",
		"category": "<Optional category name>",
		"branch": "<Optional branch name>",
		"overwrite": "<true or false to append>",
		"autoCheckin":"<true of false to check in BIIT>"
	},
	"uploadIds": [
		"<UPLOAD ID>"
	]
}

```

```

{
	"metadata": {
		"period": "<Apptio time period e.g. Jan:FY2018>",
		"domain": "<Customer domain e.g. customer.apptio.com>",
		"name": "<File name e.g. file.tsv, file.zip, etc.>",
		"host": "<Apptio host name>",
		"format": "<File format e.g. tsv, csv, etc.>",
		"project": "<Project Name>",
		"source": "<Data source e.g. S3>",
		"category": "<Optional category name>",
		"branch": "<Optional branch name>",
		"overwrite": "<true or false to append>"
		"autoCheckin": "<true of false to check in BIIT>"
	},
	"uploadIds": [
		"<UPLOAD_ID1>",
		"<UPLOAD_ID2>"
	],
	"uploadTargetMapping": {
		"<UPLOAD_ID1>": {
			"period": "<Apptio time period e.g. Jan:FY2018>",
			"domain": "<Customer domain e.g. customer.apptio.com>",
			"name": "<File name e.g. file.tsv, file.zip, etc.>",
			"host": "<Apptio host name>",
			"format": "<File format e.g. tsv, csv, etc.>",
			"project": "<Project Name>",
			"source": "<Data source e.g. S3>",
			"category": "<Optional category name>",
			"branch": "<Optional branch name>",
			"overwrite": "<true or false to append>"g
			"autoCheckin": "<true of false to check in BIIT>"
		},
		"<UPLOAD_ID1>": {
			"period": "<Apptio time period e.g. Jan:FY2018>",
			"domain": "<Customer domain e.g. customer.apptio.com>",
			"name": "<File name e.g. file.tsv, file.zip, etc.>",
			"host": "<Apptio host name>",
			"format": "<File format e.g. tsv, csv, etc.>",
			"project": "<Project Name>",
			"source": "<Data source e.g. S3>",
			"category": "<Optional category name>",
			"branch": "<Optional branch name>",
			"overwrite": "<true or false to append>"
			"autoCheckin": "<true of false to check in BIIT>"
		}
	}
}

```

Return codes :

200 - Success

400 - Bad request

404 - Incorrect API URL

500 - Internal Upload Error (contact Support)

```

{
	"processId": "<PROCESS_ID>"
}

```

Or errors if any.

## Get status of a processing request

This can be executed at any point during the upload or processing phase.

Method : GET <ULS_URL> /v1/status/ <PROCESS_ID>

Return Codes :

200 - Success

404 - Incorrect API URL

500 - Internal Upload Error (contact Support)

```

{
	"statuses": [
		{
			  "processId": "<PROCESS_ID>",
			  ...,
			  "statusMap": {
				   "<status map ID>": {
					    "statusCode": "<Status e.g. NotStarted, Finished, etc.>",
					    "errorCode": “<Error if any>”,
					    "detail": “<Details>”,
					    "tableName": "<Table name>",
					    "lastModified": "<Last modified date>"
				    }
			   }
		}
	]
}

```

Or errors if any.

## Group Session statusCode

| statusCode | Description |
| --- | --- |
| Null | statusCode is null if this is not group session (if there is only one uploadId in the process metadata, then it is not group session) |
| Success | Group session is successful |
| InProcess | Group session is in progress |
| IncompleteGroupSession | If one chunked upload fails for the group session, then group status is IncompleteGroupSession |
| FailedGroupCheckin | If end group session call fails (failure happens during group check-in), then group status is FailedGroupCheckin |

## Individual Session statusCode

| statusCode | Description |
| --- | --- |
| NotStarted | Session not started |
| Success | Success: Session is successful |
| Failed | Session is failed |

## Differences with the Legacy Platform API

1. Download the data initially uploaded via the Apptio UI.
1. Create a file which just includes the header.
1. Upload the header to the first time period in the project.
1. Upload the data downloaded in step 1 to the desired time period.

For more details on that API, see API URL for uploading a table.
