---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "SAP LeanIX Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Technology Integrations"
  - "SAP LeanIX"
source_path: "cost-transparency/technology-integration/sapleanix/sap-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# SAP LeanIX Getting Started

## Getting Started

The integration between SAP LeanIX and IBM Apptio Costing is a bi-directional integration.
The base integration focuses on the data flow from SAP LeanIX into IBM Apptio Costing. The
advanced integration is built on top of the base integration, where it exposes application TCO
metrics for consumption by SAP LeanIX.

**Key Features**

The following table lists features included in the integration.

|  |  |
| --- | --- |
| **Base Integration** | **Advanced Integration** |
| - Export information from SAP LeanIX to IBM Apptio through the SAP LeanIX   Integration API - Schedule periodic data pulls from SAP LeanIX to IBM Apptio - Out-of-the-box export of the following Fact Sheet types with predefined fields   and all relevant relations: - Organization - Business Capability - Application - IT Component - Provider - Projects - IBM Apptio API user credentials - Configuration options to select which Fact Sheets, relations, and attributes are   exported - Configurable extension of the fields that are exported - Access existing or build new Dashboards & Reports in IBM Apptio | All features included in the Base integration, plus the following:  - Import data from IBM Apptio to SAP LeanIX - On demand data pulls from IBM Apptio to SAP LeanIX - Link to Fact Sheet-specific detail page in Apptio - Synchronize Fact Sheets - Cost fields - Fact Sheet level cost view - Fact Sheet level cost over time (metric) - Search “Filtering by cost type” - Cost view for Reports and Diagrams - Manual or scheduled execution of data export |

## Enabling the Base Integration

The core of the integration between SAP LeanIX and IBM Apptio Costing gets configured in
SAP LeanIX.

All relevant information on the SAP LeanIX side, can be found here:

[Apptio Integration | SAP Help Portal](https://help.sap.com/docs/leanix/ea/apptio-integration "(Opens in a new tab or window)")

## Components Install

Once the base integration is in place, the advanced integration becomes possible.

Install the following component in IBM Apptio Costing:

**CT Apps- LeanIX Integration** - This component installs a pre-defined report that the
SAP LeanIX API uses to pull application TCO metrics directly into SAP LeanIX to be used in
their solution. The report included is called the **LeanIX Export Report** and is located
in the Application folder.

Note: This component currently sits behind Beta. Contact your Admin to install it from the
available components list.
