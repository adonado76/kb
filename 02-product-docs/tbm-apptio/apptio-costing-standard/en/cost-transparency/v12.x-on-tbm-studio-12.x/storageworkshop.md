---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Storage Workshop"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/storageworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Storage Workshop

## Preparing your Storage data

1. If you haven’t already done so, load your storage data including:
   - Storage devices
     - Arrays (Example)
     - Tape Backup (Example)
   - Storage
     - LUNS (Example)
2. Following Apptio standard
   practices, categorize each raw data set into the category of Storage.
3. If appropriate, apply a date filter to your storage data.

## About the Storage Identifiers

The identifier for the Storage Devices Master Data set is the Storage Device ID. You must have
some way to identify each storage device and use that as the Storage Device ID.

The identifier for the Storage Master Data set is the Storage ID. One storage device may hold
multiple storage hosts. This identifier must be the ID of the separate storage hosts.

## About the Storage Keys

Some of the keys in the Storage Devices Master Data set are system generated and some are
user-defined. Any system generated key should not be altered. The recommended logic for the
user-defined keys is in the table below.

| Key | Field key is based on | Logic |
| --- | --- | --- |
| **ITRT\_Storage Key** | User-defined | Recommended logic is to append Asset\_Resource – "Storage" and Sub-Tower |
| **Asset\_Storage Key** | User-defined | Optional key that allows for a data-based reference between Fixed Assets and Storage Devices |
| **Devices\_Storage Key** | Storage Device ID  Location | Append the Storage Device ID and the Location |
| **Network Devices\_Storage Devices Key** | User-defined | Recommended logic is to append Network Devices\_Storage Devices with the Storage Device ID |

Some of the keys in the Storage Master Data set are system generated and some are user-defined.
Any system generated key should not be altered. The recommended logic for the user-defined keys is
in the table below.

| Key | Field key is based on | Logic |
| --- | --- | --- |
| **Storage\_Server Key** | User-defined | Recommended logic is to append Storage\_Server Key with the Storage Device ID |
| **Devices\_Storage Key** | Storage Device ID  Location | Append the Storage Device ID and the Location |
| **Storage\_App Key** | User-defined | Recommended logic is to append Storage\_Server Key with the Application ID |
| **Storage\_Server Key** | User-defined | Recommended logic is to append Storage\_Server Key with the Server ID |

## Common Computed Columns Needed for Storage

Aside from the user-defined keys mentioned above, there are no specific computed column you need
to create. It will vary depending on your data, but typically you'll need to do figure out the
resources that are using the storage and directly allocate to those infrastructure items.
Supplemental attributes help for reporting such as capacity and utilization stats.

## Map data to Storage Devices and Storage Master Data

Map your storage device data to the Storage Devices Master Data set. Most of the mapping should
be self-explanatory at this point.

If you set your identifier to the storage device ID, map =1 to the Actual Units field. If you do
not have budgeted storage device data, you can set the Budgeted Units field to =1 as well. In 12.7
you can now leverage the Column Map function in your raw dataset to map to the Storage Devices
Master Data ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Opens in a new tab or window)"))

Map your storage data to the Storage Master Data set. Most of the mapping should be
self-explanatory at this point.

If you set your identifier to the storage host name, map =1 to the Actual Units field. If you do
not have budgeted storage data, you can set the Budgeted Units field to =1 as well. In 12.7 you can
now leverage the Column Map function in your raw dataset to map to the Storage Master Data ([Map
Columns](https://community.apptio.com/docs/DOC-10561 "(Opens in a new tab or window)"))

## Review the Storage objects on the models

| Model | Actions |
| --- | --- |
| **Cost** | Ensure values are flowing into the Storage Devices and Storage objects.  From IT Resource Towers to Storage Devices, allocate using the Data-based Reference, weighted by Storage Devices Master Data.Actual Units (this is the default setting). The keys joining IT Resource Towers and Storage Devices are the Asset\_Resource Key on the IT Resource Towers side and the ITRT\_Storage Key on the Storage Devices side.  From Storage Devices to Storage, allocation using the Data-based Reference (this is the default setting). The keys joining the two data sets is the Devices\_Storage Key. |
| **Budget** | Ensure values are flowing into the Storage Devices and Storage objects.  From IT Resource Towers to Storage Devices, allocate using the Data-based Reference, weighted by Storage Devices Master Data.Budgeted Units (this is the default setting). The keys joining IT Resource Towers and Storage Devices are the Asset\_Resource Key on the IT Resource Towers side and the ITRT\_Storage Key on the Storage Devices side.  From Storage Devices to Storage, allocation using the Data-based Reference (this is the default setting). The keys joining the two data sets is the Devices\_Storage Key. |

## Review Storage reports

The following reports are updated after you have configured the Storage object:

- Storage TCO
- Infra - Storage TCO - Detail
- Infra - Storage TCO - LUN Detail
- Infra - Summary - Storage
- Infrastructure Review
- Storage Validity
- App Infra
- App Infra - Storage Detail
- Data Dimensions - Storage
- Data Quality - IT Resources
- Data Quality - Storage

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
