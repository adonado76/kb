---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "API URL for uploading a table"
breadcrumb: []
source_path: "studio/apis/studio_api_url_table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API URL for uploading a table

♦ Applies to: v11.x, v12.0, v12.1, v12.2+

You can upload data to Apptio using the API URL command line or the Apptio ETL (Extract,
Transform, Load) tool. The information below describes how to use the API URL. For information on
the ETL tool, see [https://community.apptio.com/docs/DOC-4223](https://community.apptio.com/docs/DOC-4223 "(Opens in a new tab or window)")[Datalink API sample scripts](../../../datalink-classic/api-dlc-sample-scripts.html "(Opens in a new tab or window)").

## URL

Use the following URL to upload a table to Apptio:

```
https://[customerid].apptio.com/biit/api/v1/[domain]/[project]/[table]/[time-period]/[action
        | force]
```

The parameters used in the URL are described below. Parameters with an asterisk (\*) are
required.

| Parameter | Description |
| --- | --- |
| customerid\* | The ID assigned to the customer. |
| domain\* | The customer domain ( i.e. customer.com ). |
| project\* | The project inside the customer domain. |
| table\* | The name of the table to store the data in. |
| time-period\* | An Apptio compatible time designation (i.e. January:2000) or current to represent the current month:year on the Gregorian calendar. |
| action | The behavior to perform on the table with the data, either Append or Overwrite. If you use this parameter, do not use the Force parameter.ValuesAppend: appends the data to the current data set.Overwrite: removes the current data and replaces it with the new data.NOTE: If you need to use both the Action and Force parameters, you will need to include the parameters in the POST body instead of in the URL. |
| force | Used to override data set validity checks done by the application's import function. If you use this parameter, do not use the Action parameter. Values:true: Validity checks will be overridden.false: Validity checks will not be overridden. |

## Example URLs

Below are URL examples with the parameters included in the URL.

| Example | URL |
| --- | --- |
| Force parameter defaults to false | biit/api/v1/[domain]/[project]/[table]/[time-period]/overwrite |
| Force parameter defaults to false | biit/api/v1/[domain]/[project]/[table]/[time-period]/append |
| Action parameter defaults to overwrite | biit/api/v1/[domain]/[project]/[table]/[time-period]/force |
| Force past validation and append | --form “force=true” biit/api/v1/[domain]/[project]/[table]/[time-period]/append |

## Using form fields in the POST body to specify parameters

Instead of including the overwrite/append/force parameters in the URL, you can specify them in
form fields in the POST body. The parameters are shown below.

| Parameter | Values |
| --- | --- |
| force | "true" or "false" |
| action | "append" or "overwrite" |

## Method

To upload data to Apptio, use the http:POST method.

## Supported file formats

The supported file formats are:

- CSV
- TSV
- CSV.GZ
- TSV.GZ

Note: The only supported mime type is multipart/form-data.

## Return codes

There are three possible return codes:

- 200 OK
- 400 Incorrect API String
- 500 Internal Upload Error

## Responses

Responses are returned in JavaScript Object Notation (JSON). Success responses will include the
filename, the length of the file, and the MD5 checksum based on the data as transmitted to Apptio.
An example response is shown below.

```
{
"md5":"3727119d89edcdd71377e39e18f3a5e1\",
"length":13,
"fileName":"testFile.csv"
}
```

Error responses return the message which describes the error. Below is an example where an
improper date was provided.

```
{

"message":"Poorly formatted date string: 'SOMEDATE:2010'. Ought to be of the form 'granularity':'year'."

}
```

## Uploads reflected in Data>Overview tab

When you upload data to Apptio through the API, API Data is displayed in
the Source field on the Data>Overview tab as shown
below.

![](../../../resources/images/studio_images/studioimages/studio-upload-table.png)

## Differences with the Uploader Service API (ULS API)

When you use this API call to upload to an R12 project where the target table doesn't yet exist,
Apptio creates the table in the first time period of the project, but the data appears in the period
specified in the API call. This differs from the ULS API.

For more details on ULS API, see [Uploader Service API](../../admin/uploader-service-api.htm "(Opens in a new tab or window)")
