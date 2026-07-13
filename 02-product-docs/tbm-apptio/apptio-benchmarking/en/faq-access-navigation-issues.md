---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "apptio-benchmarking"
title: "Access and navigation issues"
breadcrumb:
  - "Benchmarking Reports"
  - "Troubleshooting and FAQ"
  - "Access and navigation issues"
source_path: "SSIU957/it-benchmarking/troubleshooting/access-navigation-issues.html"
images: []
capability_ids: []
last_updated: "2026-07-12"
summary: ""
---
# Access and navigation issues

User cannot see Interactive Benchmarking in the navigation

- Benchmarking not provisioned to your company
- User role does not include access to the Interactive Benchmarking endpoint
- User role does not include the “ViewInteractiveBenchmarksAndCostData” permission.
- User in the wrong environment (for example “sandbox” instead of “main”)

1. Confirm Benchmarking is provisioned to your company.
1. Check which roles include access to Interactive Benchmarking and whether the user has one of them.
1. Check the assigned role has the “ViewInteractiveBenchmarksAndCostData” permission.
1. Verify the user is logged into the correct Frontdoor environment.

User can open Costing but cannot access Benchmarking reports

- User doesn’t have access to the underlying Costing reports
- Report was removed, renamed, or moved
- Role-based access for that report is more restrictive
- Benchmarking components were not installed into the Costing project

1. Open the report yourself to verify it exists and runs.
1. Confirm which Costing project it depends on and whether the user can access that project.
1. Check any report-level or folder-level permissions.
1. Verify the “IT Spend Benchmarks” and, if applicable, the “Infra Benchmarks” components are installed.

Short answer you can send You can get into Costing, but your current role can’t access or the report is not available. Once that access is granted and the report is made available, the report will appear.
