---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Network Workshop"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/networkworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Network Workshop

## Preparing your Network data

Network differs heavily by customer for the definition means different things to different
companies. Some companies don't care for additional Network reporting and therefore will just be
used to cost Services. Other companies will have Network devices, contact centers, etc. so if this
data exists then install the component, cost out the items, assign costs directly to infrastructure
where you can and then send the rest to services that utilize Networks.

1. If you haven’t already done so, load your Network data including (differs heavily by customer):

   - Network Devices
   - Network Usage Data
2. Following Apptio standard
   practices, categorize each raw data set into the category of Network Devices.
3. If appropriate, apply a date filter to your network data.

## About the Network Identifiers

The identifier for Network Devices Master Data set is Device Name by default. You must have some
way to identify each Network device and use that as device name.

## About the Network Keys

Some of the keys in the Network Devices Master Dataset are system generated and some are
user-defined. Any system generated key should not be altered. The pre-defined keys are:

- ITRT\_Network Devices Key
- Network Devices\_Mainframe Key
- Network Devices\_Phys Key
- Network Devices\_Storage Devices Key
- DC\_Network Devices Key

## Map data to Network Master Data

Map your Network Devices data to the Network Devices Master Dataset. Most of the mapping is
self-explanatory at this point. In 12.7 you can now leverage the Column Map function in your raw
dataset to map to the Network Devices Master Data (Map Columns )

## Network reports

Currently there are no reports that light up after adding data to Network Devices Master
dataset.

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
