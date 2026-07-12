---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "End User Devices Workshop"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/eudevicesworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# End User Devices Workshop

## Preparing your End User Devices data

1. If you haven’t already done so, load your end user devices data like:
   - Desktops
   - Mobile Devices
   - Any End User Devices
2. Following Apptio standard
   practices, categorize each raw data set into the category of 01 – Raw Data.
3. If appropriate, apply a date filter to your end user devices data.

## About the End User Devices Identifiers

The identifier for End User Devices Master Data set is Object Identifier by default. You must
have some way to identify each End User device and use that as object identifier.

## About the End User Devices Keys

Some of the keys in the End User Master Dataset are system generated and some are user-defined.
Any system generated key should not be altered. The pre-defined keys are:

ITRT\_End User Devices Key
:   A user-generated key used to allocate costs from the IT Resource Tower object to the End User
    Devices object.

Communication\_End User Devices Key
:   A user-generated key used to allocate costs from the Communications object to the End User
    Devices object.

Network Devices\_End User Devices Key
:   A user-generated key used to allocate costs from the Network Devices object to the End User
    Devices object.

End User Devices\_Services Key
:   A user-generated key used to allocate costs from the End User Devices object to the Services
    object.

Server\_End User Devices Key
:   A user-generated key to allocate server instances used to host VDI instances

## Map data to End User Devices Master Data

Map your End User Devices data to the End User Devices Master Data dataset. In 12.7 you can now
leverage the Column Map function in your raw dataset to map to the End User Devices Master Data
([Map
Columns](https://community.apptio.com/docs/DOC-10561 "(Opens in a new tab or window)"))

## End User Devices reports

Currently there are no reports that light up after adding data to End User Devices Master Data
dataset.

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
