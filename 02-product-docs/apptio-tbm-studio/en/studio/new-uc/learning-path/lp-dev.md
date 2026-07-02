---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Learning Paths for Developers"
breadcrumb:
  - "TBM Studio"
  - "Learning Paths (Role-Based)"
source_path: "studio/new-uc/learning-path/lp-dev.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Learning Paths for Developers

**Objective:** Integrate TBM Studio with enterprise systems and extend platform
capabilities

**Who this is for:** Software developers, integration specialists, ETL developers, and
anyone building automated data pipelines or custom integrations with TBM Studio

## Foundation (30 minutes)

**What you**'ll learn: Integration architecture and when to use different integration
methods

**Learning objectives:**

- Understand TBM Studio integration architecture
- Learn authentication methods and security
- Decide when to use API vs. Published Tables vs. DataLink
- Understand data ingress and egress patterns
- Review available integration points

**Topics to complete:**

1. **Integration Architecture** (10 min) *→ Section 4.1, 4.2*
2. **Authentication Methods** (10 min) *→ Section 5.5*
3. [API Integration](../howtoguides/integrate-extend/api-integration.html) (10 min)

**Prerequisites:** Programming knowledge in any language, understanding of REST APIs

## Essential Skills (3 hours)

**What you**'ll learn: Implement API authentication, upload and download data, configure
published tables

**Learning objectives:**

- Set up API authentication successfully
- Upload cost data via API (automate data loads)
- Download data via API or Published Tables
- Handle errors and implement retry logic
- Configure Published Tables for reporting integration
- Test and validate integrations

**Topics to complete:**

1. API Authentication Setup (30 min) *→ Section 5.5*
2. [Upload Data via API](../howtoguides/integrate-extend/upload-data-via-api.html)(60 min)
3. [Download Data via API](../howtoguides/integrate-extend/download-data-api.html)(45 min)
4. Configure Published Tables (45 min) *→ Section 3.5.2*

**Prerequisites:** Foundation completed, development environment set up

**Estimated practice time:** Add 2-3 hours building and testing integrations

## Advanced (5 hours)

**What you**'ll learn: Master ApptioScript, implement complex integrations, handle edge
cases, and build production-grade solutions

**Learning objectives:**

- Write ApptioScript for custom calculations and logic
- Implement complex formula patterns
- Build ServiceNow or other enterprise integrations
- Handle errors gracefully with retry logic
- Optimize API performance
- Implement production monitoring and alerting
- Build robust, maintainable integration solutions

**Topics to complete:**

1. ApptioScript Fundamentals (90 min) *→ Section 5.6*
2. Complex Formula Patterns (60 min) *→ Section 5.4, 5.6*
3. [Enterprise System
   Integration](../howtoguides/integrate-extend/api-integration.html) (90 min)
4. [Error Handling and
   Retry Logic (45 min)](../howtoguides/integrate-extend/handle-api-errors.html)
5. [Performance Optimization](../admin/performance-optimize.html) (30 min)
6. [Production
   Integration Patterns (45 min)](../howtoguides/integrate-extend/htg-use-common-pattern.html)

**Prerequisites:** Essential Skills completed, experience with production systems

## Common challenges

- **Authentication failures:** Verify API key validity, check permissions
- **Upload validation errors:** Review data format, check column mappings
- **Rate limiting:** Implement backoff, batch operations
- **Data inconsistencies:** Add reconciliation logic, validate before upload
- **Performance issues:** Batch operations, optimize data size
