---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "API Integration"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Integrate and Extend"
  - "API Integration"
source_path: "SSWRJM/studio/new-uc/howtoguides/integrate-extend/api-integration.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# API Integration

Content Type: How-To Guide Collection

Target Audience: Developers, Technical Administrators

Applies to: TBM Studio 12.0 and later

Prerequisites: API credentials, programming knowledge, network access to TBM Studio

## Overview

The TBM Studio Platform API enables programmatic automation of data uploads and downloads. This section provides how-to guides for integrating your systems with TBM Studio using the REST API, including authentication, data operations, and production-ready error handling patterns.

The API provides a direct link between your corporate data systems and TBM Studio through simple HTTP commands. You can integrate these commands into job schedulers, ETL tools, or custom applications with minimal setup—no additional software installation required.

## Choosing Your Integration Method

TBM Studio offers multiple integration approaches. Use this decision guide to select the right method for your use case.

| Method | Best For | Requires |
| --- | --- | --- |
| Method | Best For | Requires |
| Platform API | Custom integrations, third-party ETL tools, environments where on-prem agents cannot be installed | Scripting skills, API credentials |
| DataLink (Classic) | Point-and-click data loading, users without scripting skills | DataLink agent installation, DataLink license |
| Published Tables | Exporting model data to external BI tools (Power BI, Tableau) | TBM Studio 12.11.3+, report configuration |

Use the Platform API when:

- You cannot install an on-premises DataLink agent to upload data from on-prem sources
- You want to use embedded scripting in a third-party ETL tool
- You need to automate data loads through corporate job schedulers
- You require programmatic control over data operations

Use Published Tables when:

- You need to export model-calculated data to external systems
- You want a stable schema for downstream BI tool consumption
- You need controlled data egress with governance

See User authentication using APIs for more information.
