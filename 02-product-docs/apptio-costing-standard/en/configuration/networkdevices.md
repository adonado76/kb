---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "CT Apps - Network Devices component"
breadcrumb: []
source_path: "configuration/networkdevices.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - Network Devices component

The Network Devices component is part of Costing Standard Applications and
Services module. It is used to allocate Network Device infrastructure costs including LAN, WAN,
Voice and other network equipment used in the data center and office locations to the consumers of
the Network Devices.

Applies to: Costing Standard on TBM Studio 12.0 and
later

Component Icon:

![](../../resources/images/ct_images/6846_1.png)

## Introduction

The Network Devices component installs a new object, data sets and recommended allocation
strategies for apportioning Network Device costs to the following typical services:

- Mainframe - for network equipment supporting the mainframes in the enterprise data centers
- Physical Servers - for network equipment supporting servers in the enterprise data centers
- Storage Devices - for network equipment supporting storage in the enterprise data centers
- End User Devices - for network equipment supporting physical and wireless connections to PCs, laptops and mobile devices in the office locations

## Supporting tables

When you install the CT Apps - Network Devices component, a new Network Devices group is created
with two tables: Network Devices (model table), Network Devices Master Data.

## Master data

For a description of the fields in the master data table, see the information on the CT Apps -
Network Devices component page in the product. To display the page:

1. Click the Project tab in the ribbon.
2. Click Components.
3. Click the CT Apps - Network Devices component.

## Upload the data

Upload your network devices data. The required and recommended fields are listed below. All of
the fields can be mapped to the Network Devices Master Data table.

- Device Count (required)
- Device Type (required)
- Location (recommended)
- Location Type (required)
- Network Devices\_Storage Devices (required)
- Object Identifier (required)
- Service ID (recommended)
- Service Name (recommended)

## Map the data

After uploading the network devices data, map the table to the Network Devices Master Data
table.

After you map the data, there should be value allocated from IT Resource Towers and Data Centers
to Network Devices, and from Network Devices to Physical Server, Storage Devices, End User Devices,
and Mainframes in the Cost model.

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
