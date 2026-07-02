---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Maintain the data"
breadcrumb: []
source_path: "boit/maintain-the-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Maintain the data

After you have configured Billing Standard , you will need to maintain the supporting data.
There are three main types of data.

- **Service consumption data**
  - The number of computers, applications, and email accounts being used.
- **Service Library data**
  - As you add and delete the services you offer to your customers, you will need to update the service library.
- **Business unit data**
  - As the business units change in your organization, you will need to update the business unit data.

**Upload data from an existing data set**

You can upload data from a variety of files including Excel and .csv (comma separated
values). If the source application can produce a compatible file, you can append the data to the
existing table in Billing Standard . For more information, see  [Append data](../studio/data_studio/append-data.html "Applies to: TBM Studio 12.0 and later")  .

**Automate the upload using Apptio DataLink**

Automate the upload using the Apptio DataLink application (recommended method). For more
information on DataLink, see the [DataLink knowledge base](../datalink/home.html)  . DataLink is an extract-load solution that provides a reliable,
automated method to load data into the Apptio applications including Billing Standard . DataLink
connectors extract data and load it into target Apptio projects.

When you create a connector, you can define a schedule for automatic execution of the connector. Schedules can be based on days, weeks, months, and annually.
