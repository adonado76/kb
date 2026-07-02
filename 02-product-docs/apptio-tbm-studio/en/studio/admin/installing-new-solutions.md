---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Installing New IBM Apptio Costing Solutions on Older Template Projects"
breadcrumb: []
source_path: "studio/admin/installing-new-solutions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Installing New IBM Apptio Costing Solutions on Older Template Projects

## Key Terms You Should Know

**Server Version:**

- Refers to the version of IBM Apptio TBM Studio software installed. Determines platform
  capabilities and compatibility.
- Users can check their current version at: Settings > About
- Current series: 12.11.1x

**Template / Component Version:**

- Refers to the version of Out-of-the-Box (OOTB) content (Data Tables, Models, Reports).
- Each solution is tied to a specific Component Version.
- Check it at: TBM Studio > Project > Project Settings > Component Version

Important:

- To install the new solutions, you do NOT need to upgrade all the existing components.
- Refer to the table on the next page to identify the required Server Version and
  Template Version for your desired solution.

## Step-by-step Guide

1. **Check Server Version:**Ensure your instance's Server Version is equal to or newer
   than the release version of the solution.
2. **Identify Required Component Version:**Use the Solutions Release Table to find the
   Component Version (e.g., v120).
3. **Temporarily Change Component Version:**Navigate to Project > “Project Settings”.
   Change the Component Version to match the solution’s version.
4. **Install the Solution Components:** Go to the Components tab and install the
   required solution components.
5. **Upgrade Existing Components (If needed):** Revert and reapply customizations after
   upgrading components ORmanually apply changes to Master Tables as per the Configuration
   Guide.
6. **Revert “Project Settings” Change:**Return to the original Component Version to
   avoid upgrade prompts.

To know more, see the video: [How to install new IBM Apptio Costing Solution Components
on Projects with Older Template Versions](https://community.ibm.com/community/user/viewdocument/how-to-install-new-ibm-apptio-costi?CommunityKey=2e85ed45-9b8a-486c-bd55-019253d466eb "(Opens in a new tab or window)")

Tip: Document custom changes for easy reapplication. Always refer to the
Configuration Guide provided with the solution.

## Solution Version Release Details

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| IBM Apptio Costing  New Solutions | Costing Essentials | Costing Standard | Template | Server Version |
| Hybrid IT TCO Impact | - | Yes | v120 | 12.11.12 |
| Public Cloud TCO | Yes | Yes | v120 + v200 | 12.11.13 |
| Apptio - Turbonomic Integration (GA) | - | Yes | v120 | 12.11.13 |
| AI TCO & Usage | - | Yes | v120 | 12.11.14 |
| Mainframe TCO | - | Yes | v120 | To be released |
| Maximo Maintenance Cost Insights | N.A. | N.A. | v200 | 12.11.15 |
| Product TCO | - | Yes | v120 | To be released |
