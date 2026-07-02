---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "API Integration"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Integrate and Extend"
source_path: "studio/new-uc/howtoguides/integrate-extend/api-integration.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API Integration

**Content Type:** How-To Guide Collection

**Target Audience:** Developers, Technical Administrators

**Applies to:** TBM Studio 12.0 and later

**Prerequisites:** API credentials, programming knowledge, network access to TBM
Studio

## Overview

The TBM Studio Platform API enables programmatic automation of data uploads and downloads.
This section provides how-to guides for integrating your systems with TBM Studio using the
REST API, including authentication, data operations, and production-ready error handling
patterns.

The API provides a direct link between your corporate data systems and TBM Studio through
simple HTTP commands. You can integrate these commands into job schedulers, ETL tools, or
custom applications with minimal setup—no additional software installation required.

Note: For release 12.9 and above, include these headers on all API calls: app-type="Flagship"
and app-version="NA"

## Choosing Your Integration Method

TBM Studio offers multiple integration approaches. Use this decision guide to select the
right method for your use case.

|  |  |  |
| --- | --- | --- |
| **Method** | **Best For** | **Requires** |
| Platform API | Custom integrations, third-party ETL tools, environments where on-prem agents cannot be installed | Scripting skills, API credentials |
| DataLink (Classic) | Point-and-click data loading, users without scripting skills | DataLink agent installation, DataLink license |
| Published Tables | Exporting model data to external BI tools (Power BI, Tableau) | TBM Studio 12.11.3+, report configuration |

**Use the Platform API when:**

- You cannot install an on-premises DataLink agent to upload data from on-prem
  sources
- You want to use embedded scripting in a third-party ETL tool
- You need to automate data loads through corporate job schedulers
- You require programmatic control over data operations

**Use Published Tables when:**

- You need to export model-calculated data to external systems
- You want a stable schema for downstream BI tool consumption
- You need controlled data egress with governance

See [User authentication using APIs](https://community.ibm.com/community/user/viewdocument/user-authentication-using-apis?CommunityKey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8&tab=librarydocuments "(Opens in a new tab or window)") for more information.

- **[How-To: Authenticate with the API](../../../../studio/new-uc/howtoguides/integrate-extend/how-to-authenticate-api.html)**
- **[How-To: Upload Data via API](../../../../studio/new-uc/howtoguides/integrate-extend/upload-data-via-api.html)**
- **[Uploader Service API](../../../../studio/admin/uploader-service-api.html)**  
  **Applies to**: TBM Studio 12.0 and later
- **[How-To: Download Data via API](../../../../studio/new-uc/howtoguides/integrate-extend/download-data-api.html)**
- **[How-To: Handle API Errors](../../../../studio/new-uc/howtoguides/integrate-extend/handle-api-errors.html)**
- **[Quick Reference](../../../../studio/new-uc/howtoguides/integrate-extend/quick-ref.html)**
