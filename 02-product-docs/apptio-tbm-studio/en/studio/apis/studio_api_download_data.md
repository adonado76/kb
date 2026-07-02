---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "API: Downloading data"
breadcrumb: []
source_path: "studio/apis/studio_api_download_data.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API: Downloading data

Applies to: TBM Studio v11.x, v12.0, v12.1, v12.2 and later

Using the API, you can download raw tables and also transform tables from the Data tab. Also, you
can download data from tables and charts on reports. You can download data in Excel (.xls or .xlsx
file format). For large files, you can use the TSV (.TSV) file format.

## Authentication

See [https://community.apptio.com/docs/DOC-7836](https://community.apptio.com/docs/DOC-7836 "(Opens in a new tab or window)")[User authentication using
APIs](../../admin/user-auth-apis.htm "(Opens in a new tab or window)").

## Getting API URLs for tables

Navigate to a
table in TBM Studio. Select the Home tab, click Export in the drop-down, and then
select Show API URL.

![](../../../resources/images/studio_images/studioimages/studio_api_download_800x380.png)

A
modal dialog appears that allows you to select and copy the appropriate URL:

![](../../../resources/images/studio_images/studioimages/studio_api_download_1_800x458.png)

## Getting API URLs for reporting elements

Right-click on the bottom of tables, anywhere on a chart, or use the drop-down
menu in the upper-left of reporting elements (if so equipped) and you will get a context menu where
you can select Show API URL:

![](../../../resources/images/studio_images/studioimages/studio_api_download%202_800x469.png)![](../../../resources/images/studio_images/studioimages/studio_api_download%203_800x587.png)

A
modal dialog appears that allows you to select and copy the appropriate URL:

![](../../../resources/images/studio_images/studioimages/studio_api_download%204_800x533.png)

## Changing the Delimiter

In some cases, you may wish to change the delimiter. To do that you can use the “delimiter”
argument as follows specifying a hex character encoding value (to look up character encodings try
[this Wikipedia Page](https://en.wikipedia.org/wiki/ASCII#Printable_characters "(Opens in a new tab or window)")).

https://HOST/biit/api/v2/domains/DOMAIN/projects/PROJECT\_NAME/tables/TABLE\_NAME/dates/TIME\_PERIOD.tsv?delimiter=ENCODED\_CHARACTER

For example, if you wished to change the delimiter to be a pipe character “|”, you would obtain
the TSV format URL as shown earlier in this document, then specify the delimiter as “%7C” which is
the hex encoding for a pipe character similar to this:

https://customer.apptio.com/biit/api/v2/domains/customer.com/projects/Cost
Transparency/tables/Test Table/dates/Jan:FY2020.tsv?delimiter=%7C

Sometimes data may contain the delimiter you want to use. To look at an example, let’s say you
are starting with a table like the following:

![](../../../resources/images/studio_images/api-change_623x294.png)

However, you want to use the pipe character as the delimiter. Note that in the 3rd row, the
values include pipe characters. In order to successfully use the pipe character you must substitute
something else in the data values. In the following example, the pipe characters (%7C) will be
replaced by commas (%2C):

https://customer.apptio.com/biit/api/v2/domains/customer.com/projects/Cost
Transparency/tables/Test Table/dates/Jan:FY2020.tsv?delimiter=%7C&delimiterReplacement=%2C

The resulting download will look like this:

ColumnA|ColumnB

ValueA1|ValueB1

ValueA2|ValueB2

ValueA,3|ValueB,3

## Downloading via API

Refer to either of the following articles for more detail on how to use the API to execute a download:

- [API tutorial: Download and upload
  v.12 Costing Standard table using Postman tool](studio_tutorial.htm "(Opens in a new tab or window)")
- [Apptio API demo
  scripts](studio_demo_scripts.htm "(Opens in a new tab or window)")
