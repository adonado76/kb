---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Installing New IBM Apptio Costing Solutions on Older Template Projects"
breadcrumb: []
source_path: "cost-transparency/configuration/install-apptio-ibm-costing-old-template.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Installing New IBM Apptio Costing Solutions on Older Template Projects

## Key Terms

**Server Version**

- Refers to the version of IBM Apptio TBM Studio software installed. Determines platform
  capabilities and compatibility.
- To check current version navigate to **Settings** > **About**
- Current series: 12.11.1x

**Template / Component Version**

- Refers to the version of Out-of-the-Box (OOTB) content (Data Tables, Models, Reports).
- Each solution is linked to a specific Component Version.
- To check Component version navigate to **TBM Studio** > **Project** > **Project
  Settings** > **Component Version**

Note:

- To install the new solutions, you do not need to upgrade all of the existing components.
- Refer to the **[Solution Version Release
  Details](#aicot__solutionversiontable "(Opens in a new tab or window)")** section to identify the required Server Version and Template Version for your
  desired solution.

**Steps**

- **Check Server Version**: Ensure your instance's Server Version is equal to or newer than the
  release version of the solution.
- **Identify Required Component Version**: Use the **[Solution Version Release Details](#aicot__solutionversiontable "(Opens in a new tab or window)")** to find the Component
  Version (e.g., v120).
- **Temporarily Change Component Version**: Navigate to **Project** > **Project
  Settings**. Change the Component Version to match the version of the solution.
- **Install the Solution Components**: Navigate to the **Components** tab and install the
  required solution components.
- **Upgrade Existing Components (If needed)**: Revert and reapply customizations after
  upgrading components or manually apply changes to Master Tables as per the Configuration Guide.
- **Revert “Project Settings” Change**: Return to the original Component Version to avoid
  upgrade prompts.

**Pro tips**

- Document custom changes for easy reapplication.
- Always refer to the Configuration Guide provided with the solution.
- We can have multiple versions of different components in a project.

## Solution Version Release Details

Table 1. Solution Version Release
Details

| IBM Apptio Costing New Solutions | Costing Essentials | Costing Standard | Template | Server Version |
| --- | --- | --- | --- | --- |
| Hybrid IT TCO Impact | - | Yes | v120 | 12.11.12 |
| Public Cloud TCO | Yes | Yes | v120+v200 | 12.11.13 |
| Apptio - Turbonomic Integration (GA) | - | Yes | v120 | 12.11.13 |
| AI TCO & Usag | - | Yes | v120 | 12.11.14 |
| Mainframe TCO | - | Yes | v120 | 12.11.17 |
| Maximo Maintenance Cost Insights | N/A | N/A | v200 | 12.11.17 |
| Cost Take-Out Reports | - | Yes | V120 | 12.11.17 |
| Product TCO | - | Yes | v120 | To be released |
