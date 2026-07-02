---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Apptio API demo scripts"
breadcrumb: []
source_path: "studio/studio/apis/studio_demo_scripts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Apptio API demo scripts

## Introduction

Note:

In release 12.9 and above, include the following header values on any API calls to the platform
API.

app-type="Flagship"

app-version="NA"

This includes API calls which upload to or download from Costing Standard or other platform
projects. These are in addition to existing API headers you may already be using.

Apptio supports three APIs:

- The [Apptio Platform API](../../admin/the-apptio-api.html "Applies to: TBM Studio 12.0 and later")
- The [Enhanced Access Administration API](../../../frontdoor/home.html)
- The [Datalink (Classic) API](../../../datalink-classic/datalink/datalink_api_sample_scripts.html)

This document provides Apptio Platform API demo scripts in one or two commonly used scripting
languages, as well as instructions on how to set up the demo scripts for testing. It also supplies
users with an orientation to the mechanics of using the API so that they can then apply the learning
to their own scripted solutions.

Datalink (Classic) uses the Apptio API to transport data. The Apptio API
can also be used independently for data upload or download operations (for example, batch
operations), which Datalink (Classic) doesn't readily support. The use of
the API is more involved and usually requires some scripting or programming background to implement
and maintain. Therefore, it is recommended to use Datalink (Classic) unless
you have advanced needs and resources to implement and maintain the API implementation.

The Apptio API is distinct from the Datalink (Classic) API: The Apptio
API is used to upload to Apptio project tables, or download from Apptio project tables (including
those in reports), and it is what Datalink (Classic) uses under the hood.
The Datalink (Classic) API is used to automate Datalink
(Classic) agent connector execution. To learn more about the Datalink
(Classic) API, refer to [Datalink API sample scripts](../../../datalink-classic/datalink/datalink_api_sample_scripts.html).

The script attached to this article has been tested against the following specific releases.
However, it should work with other releases too:

- r11.8.3.5
- r12.3.2

## Basic operations

The first demo script is named ApptioAPI\_Demo\_Basic\_v2.ps1. It is written in Windows PowerShell,
which is widely available on Windows systems, can leverage .NET libraries, and can be used by
software, such as SQL Server Management Studio, to implement load and extraction from SQL Server.
This subject will be covered in more detail in future releases of this document.

The script is attached and commented on. The usage is as follows. This is displayed if the script
is executed with no arguments:

You need to specify -up or -down.

Usage (using API Keys):

```
ApptioAPI_Demo_Basic_v2.ps1 -help
ApptioAPI_Demo_Basic_v2.ps1 -down [-APIURL "valid API URL"]
[-downtimeperiod "Apptio time period"]
[-downloadfolder "folder to download to"] [-downfile "file name"]
ApptioAPI_Demo_Basic_v2.ps1 -up [-v1] [-upfile "path to file to upload"]
[-apptiohost "https://domain-r12.apptio.com"]
[-domain "domain.com"] [-project "Project Name"] [-table "Table Name"]
[-uptimeperiod "Apptio time period"] [-transformation overwrite | append]
```

Usage (using username/password auth):

```
ApptioAPI_Demo_Basic_v2.ps1 -help
ApptioAPI_Demo_Basic_v2.ps1 -user "username@domain.com" -pass "password"
-down [-APIURL "valid API URL"]
[-downtimeperiod "Apptio time period"]
[-downloadfolder "folder to download to"] [-downfile "file name"]
ApptioAPI_Demo_Basic_v2.ps1 -user "username@domain.com" -pass "password"
-up [-v1] [-upfile "path to file to upload"]
[-apptiohost "https://domain-r12.apptio.com"]
[-domain "domain.com"] [-project "Project Name"] [-table "Table Name"]
[-uptimeperiod "Apptio time period"] [-transformation overwrite | append]
```

It is possible to provide combinations of the optional arguments and execute without
modification. However, if you want to use only the "-up" and "-down" flags, you can edit the script
to modify the necessary variables. The following is an explanation of the variables, what they
contain, and what you may need to do for setup.

## Authentication arguments

The following arguments support API Keys authentication. This is the preferred method for use
within v12 environments.

*-pubkey "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"*

This argument supplies a valid API Key public key. See [Enhanced Access Administration API: Overview of API keys and FAQ](../../../frontdoor/admin-guide/eaa-api/overview-api-keys-faq.html) for more information on how
to obtain a public key.

*-secret "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"*

This argument supplies a valid API Key secret key. See [Enhanced Access Administration API: Overview of API keys and FAQ](../../../frontdoor/admin-guide/eaa-api/overview-api-keys-faq.html) for more information on how
to obtain a public key.

*-envid "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"*

This argument supplies a valid v12 environment ID. See [Enhanced Access
Administration API: Update environment information for a user](../../../frontdoor/admin-guide/eaa-api/api-get-user-environment.html) for information on how to
obtain this ID using the API. You can also request it from Apptio Support or your CSM or CSE.

The following arguments support username/password authentication. This is for backward
compatibility with r11 environments and should not be used in v12 environments.

*-user "user@domain.com" -pass "password"*

These arguments specify a user account that has access to the project that contains data to
download and the password for that account. Remember that if you create a new account to support
this, you will need to edit the account after creation to uncheck the **Single-Use
Password** checkbox, or the API may not respond.

## Download arguments

*-APIURL "valid API
URL"*

This argument specifies a valid, quoted, Apptio API URL. This can be obtained
from almost anything in Apptio by clicking the export icon, which appears as
follows:

![](../../../resources/images/studio_images/studioimages/studio%2028.png)

This icon
appears in the r11 Data tab of the studio in association with any Transform Table or Raw
Table view, or via the Export button of TBM Studio in r12 when a
table is selected.

In reports, you can access it by right-clicking at the base of a
table (for example, in the totals row area).

*-downtimeperiod "Apptio time
period"*

This argument specifies a correctly formatted Apptio time period to
download from (for example, Aug:FY2016). This will replace any time period that happens to
be in the APIURL.

*[-downloadfolder "folder to download to"]*

This argument
specifies the folder for the downloaded data.

*[-filename "file
name"]*

This argument specifies the name for the file to which the data is
downloaded.

## Upload arguments

`[-v2]`

This argument specifies the use of the API v2 URL for upload. This is optional and is only
necessary in specific situations.

`[-upfile "path to file to upload"]`

This argument specifies the path to a file that is to be uploaded.

`[-apptiohost "https://domain-dev.apptio.com"]`

This argument specifies the Apptio host instance where the project the file is being uploaded
into resides.

`[-domain "domain.apptio.com"]`

This argument specifies your company's domain.

`[-project "Project Name"]`

This argument specifies the project's name into which the file will be uploaded.

`[-table "Table Name"]`

This argument specifies the name of the table into which the data is to be loaded.

`[-uptimeperiod "Apptio time period"]`

This argument specifies a correctly formatted Apptio time period into which to upload (for
example, Aug:FY2016).

`[-transformation overwrite | append]`

This argument specifies whether or not the table should be overwritten or appended to.

## Download demo scripts

Click [here](../../../resources/apptio_api_demo_scripts.zip) to
download the demo scripts of the Apptio API.
