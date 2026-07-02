---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Delegate Contract Costs"
breadcrumb: []
source_path: "planning/iip/delegate-contract-costs.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Delegate Contract Costs

Users can now delegate contract expenses to a different cost center starting from a specified
date. This enhancement allows for accurate allocation of expenses to the appropriate cost center.
For projects with multiple phases (e.g., build/run), delegating expenses to specific cost centers
aids in tracking the financial performance of each project phase effectively.

Let us see an example how this works.

1. Navigate to Expenses > Contract tab and create an expense for a project with Cost
   Center as "Apps-Line of Business" with Start Date 01/15/2024 and End Date 01/14/2025, for amount
   $200,000. This expense is amortized for the selected time period as shown below.

   ![](../../../resources/images/it%20planning_images/del-cont-1_1255x617.png)
2. The Summary tab shows that all expenses for this contract are allocated only to a single
   Cost Center "Apps-Line of Business".

   ![](../../../resources/images/it%20planning_images/del-cntrct-2_1277x375.png)
3. Now, let us assign the contract cost from August 2024 to another Cost Center. Navigate to the
   Contracts tab and select the Delegation Cost Center as "Data Center Ops" and the Delegation
   Start Date to 8/15/2024.

   ![](../../../resources/images/it%20planning_images/del-cntrct-3_1333x432.png)
4. The Summary tab will now show two lines generated - one for each Cost Center, as per the
   configured delegation.

   ![](../../../resources/images/it%20planning_images/del-con-1_1295x377.png)
5. The Cost Center as "Apps-Line of Business" has expenses assigned from Jan FY24 to Jul FY24 while
   the Cost Center "Data Center Ops" has expenses assigned from Aug FY24.

   ![](../../../resources/images/it%20planning_images/del-con-2_1296x390.png)

Note: Contract expense can be delegated only once to another cost center.
