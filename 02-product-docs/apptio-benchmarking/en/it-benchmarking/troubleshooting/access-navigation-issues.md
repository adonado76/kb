---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Access and navigation issues"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
  - "Troubleshooting and FAQ"
source_path: "it-benchmarking/troubleshooting/access-navigation-issues.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Access and navigation issues

**User cannot see Interactive Benchmarking in the navigation**

Symptom  
User logs into Frontdoor and does not see the Benchmarking application or
tile. Otherwise, user may be attempting to access Benchmarking from Costing or other IBM Apptio
product via in-app navigation   
Likely causes

- Benchmarking not provisioned to your company
- User role does not include access to the Interactive Benchmarking endpoint
- User role does not include the “ViewInteractiveBenchmarksAndCostData” permission.
- User in the wrong environment (for example “sandbox” instead of “main”)

What to check

1. Confirm Benchmarking is provisioned to your company.
2. Check which roles include access to Interactive Benchmarking and whether the user has one of
   them.
3. Check the assigned role has the “ViewInteractiveBenchmarksAndCostData” permission.
4. Verify the user is logged into the correct Frontdoor environment.

Short answer you can send  
You don’t see Benchmarking because your user permissions
do not have access to that application in this environment. Once you’re granted the right role, the
Benchmarking application will appear up in your navigation.

**User can open Costing but cannot access Benchmarking reports**

Symptom  
User sees the Costing landing page, but some Benchmarking-specific tiles or
reports are missing or error out.  
Likely causes

- User doesn’t have access to the underlying **Costing** reports
- Report was removed, renamed, or moved
- Role-based access for that report is more restrictive
- Benchmarking components were not installed into the Costing project

What to check

1. Open the report yourself to verify it exists and runs.
2. Confirm which Costing project it depends on and whether the user can access that project.
3. Check any report-level or folder-level permissions.
4. Verify the “IT Spend Benchmarks” and, if applicable, the “Infra Benchmarks” components are
   installed.

Short answer you can send  
You can get into Costing, but your current role can’t
access or the report is not available. Once that access is granted and the report is made available,
the report will appear.
