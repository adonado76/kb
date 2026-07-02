---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "AI Platform Mapping"
breadcrumb:
  - "Costing Standard"
  - "Report NX Walkthrough"
  - "AI TCO NX Reports"
source_path: "cost-transparency/reports/ai-platform-mapping-nx.html"
images:
  - "resources/images/ct_images/nx-aitcomap.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# AI Platform Mapping

This report maps AI platform consumption to organizational cost centers, enabling accurate chargeback and budget allocation by assigning AI service usage to specific solutions, business units, and users across your enterprise.

This report is designed for use by the following personas:

- AI/ML Administrators
- Finance Teams
- IT Operations
- Data Science Teams
- Cost Allocation Analysts

## Key Elements

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-aitcomap.png)

| Element | Description |
| --- | --- |
| Tab Navigation (1) | Navigate between three data management views: enrichment for adding platform details, mapping for cost allocation, and normalization for standardizing token metrics. |
| Filter Options (2) | Two lists let you filter the report by platform name and model name. |
| Instructions Panel (3) | Review mapping hierarchy guidelines to ensure consistent cost allocation: prioritize solution-level mapping, then business unit, then user-level assignment. |
| Action Buttons (4) | These buttons open additional options, publish mapping changes, or add a row. |
| Mapping Data Table (5) | View and edit AI consumption mappings across platforms, models, and organizational entities. Each row links a specific AI service to its cost center, with usage quantities that drive allocation calculations. |

## Questions Answered

- Which AI platforms and models are generating costs that need allocation?
- How should AI consumption be allocated across solutions and business units for accurate chargeback?
- Which users are consuming which AI models?
- What is the usage quantity for each platform-model-consumer combination?
- Which AI platforms lack cost center assignments and require mapping?
- Which solutions use multiple AI models or platforms?
- How is AI usage distributed across different business units?
- Are there any unmapped platforms or models that need attention?

## Recommended Actions

- Review the table for placeholder or test data and replace with actual platform-to-cost-center
  assignments.
- Click "Add row" to create mappings for AI platforms that lack solution, business unit, or user
  assignments.
- Assign costs to Solution Offering first (preferred), then Business Unit, then User ID as
  fallback options.
- Confirm that usage values are accurate, as these metrics determine cost distribution.
- Use filters to review specific platforms (OpenAI, Hugging Face) and ensure complete model
  coverage.
- Click "Publish" to activate your mappings in the cost allocation system.
- Schedule monthly reviews to capture new AI platforms, models, and users as adoption grows.
