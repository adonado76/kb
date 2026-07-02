---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Contract Summary"
breadcrumb:
  - "Costing Standard"
  - "Report Walkthrough"
  - "Vendor Collection"
source_path: "cost-transparency/vi_content/report-contract-summary.html"
images:
  - "resources/images/vi_images/vi/alertsicon.jpg"
  - "resources/images/vi_images/vi/export.jpg"
  - "resources/images/vi_images/vi/vi_contract_summary_11.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Contract Summary

◆ Applies to: Vendor Insights on TBM Studio 12.8 and later (v107)

Use the  **Contract Summary**  report to view the contract spend by the top ten vendors and
the contract details across time. This report allows you to:

- Proactively analyze contracts prior to expiration and renewals
- Analyze contract business terms
- Analyze SLA performance

This report is designed for:

- CIO and senior IT leadership
- Application Owners
- Services Owners
- IT Finance Managers
- Vendor Managers

**Display the Contract Summary report**

In the  Application  menu, select  Vendor Insights  .

1. Navigate to  Report Collections > Contracts  .
2. From the bar at the top of the page, select  Contract Summary  .
3. To export or email your data, select  Export  ( ![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/export.jpg) ) at the top right of
   the page and select an export format.
4. To create an alert to notify you if a contract is expiring, select  Alert  ( ![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/alertsicon.jpg) ) on the top right
   of the page. To learn more, see  [Create alerts for expiring vendor
   contracts](alerts.html)  .

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/vi_contract_summary_11.jpg)

**(1) Report collection**

This report collection provides the details you need to analyze your vendor contract’s planned
vs. actual spend and your progress towards meeting any contractual spend minimums:

- Contract Summary (described in this article)
- [Contract Expiration](report-contract-expiration-12-6.html)
- [Contract to Applications](report-contract-applications.html)
- [Contract Expiration Notification](report-contract-expiration-notification.html)

**(2) KPIs**

KPIs provide a high-level view of your contract spend and contract expiration:

- **Contract Spend to Date**  - This KPI shows the total contract spend YTD and the monthly
  contract spend in the current period. Spend to date is the sum of all account payables associated
  with contracts from the beginning of the fiscal year to the current period.
- **Active # Contracts**  - This KPI shows the total number of active contracts as of the current
  period and the total number of contracts.
- **Contracts Expiring < 90 Days**  - This KPI shows the number of contracts expiring in less
  than 90 days, and less than 180 days.
- **Min Committed Spend for Contract Expiring < 90 Days**  - This KPI shows the minimum
  committed spend for contracts expiring in less than 90 days, and less than 180 days.

**(3) Contract Spend by Top 10 Vendors**

Use this section to identify the top 10 vendors with the most contract spend for the current
period and the trend of that spend YTD.

For additional details about a specific vendor, click on the chart to open the  [Vendor Detail report](report-vendor-detail.html)  .

**(4) Contract Details by Vendor**

Use this section to view contract details by  **vendor**  . Use the bar chart to see the
vendors with the top contract spend. Employ the table to view the details of those contracts sorted
by the contract with the most spend on top.

Click the tabs to view contract spend for the current period, current quarter, YTD, and
contracts with no spend. The slicers for normalized vendor name, function, and contract owner allow
you to narrow the results as needed.

For additional details about a specific contract, click on the chart or click on the **Contract Title**  column in the table to open the [Contract Detail report](report-contract-detail.html)  .

**(5) Contracts by Hierarchy**

Use this section to view contract details by  **parent contract**  . Use the bar chart to see
the parent contracts with the top contract spend. Employ the table to view the details of those
contracts sorted by the contract with the most spend on top.

Click the tabs to view contract spend for the current period, current quarter, and YTD. The
slicers for normalized vendor name, parent contract, and contract owner allow you to narrow the
results as needed.

For additional details about a specific contract, click in the chart or click on the **Contract Title**  column in the table to open the [Contract Detail report](report-contract-detail.html)  .

**(6) Contract Plan**

Use this section to view budgeted contract spend details. Use the bar chart to see the vendor
with the top contract budget spend. Employ the table to view the details of those contracts sorted
by the contract with the most spend on top.

Click the tabs to view the original contract plan from ITP and the latest contract plan. The
slicers for cost center owner, cost center name, vendor, contract type, and location allow you to
narrow the results as needed.

Use the options above the table to add specific details to your analysis, including cost center
owner, cost center name, and location.

This section will only appear with the  [ITP integration](../../it-planning/planning/integrate-ct.html "If your organization runs both Apptio Costing Standard and an Apptio Planning application, you can integrate them to share data.")  with Vendor Insights to pull in the budget from ITP .

**(7) Contract ARC RRC**

Use this section to view an overview of the ARC RRC contracts. Use the bar chart to see the top
baseline contract amount for ARC RRC contracts. Employ the table to view the details of those ARC
RRC contracts by vendor sorted by the contract with the highest baseline cost on top.

Click the  **Contract ARC RRC**  button to navigate to the  **ARC RRC Summary**  report.
The slicers for the resource unit and vendor allow you to narrow the results as needed.

Use the options above the table to add specific details to your analysis, including actual
units, invoice to actual units variance, resource unit description, IT resource tower, and IT
resource sub tower.

For additional details about a specific contract, click on the  **Contract Title**  column in
the table to open the  [Contract Detail report](report-contract-detail.html)  .

**View the ARC RRC Summary**

To learn how to view the ARC RRC Summary, see  [ARC RRC
Summary report](report-arcrrc-summary.html)  .

Questions answered

Use the information in this report to answer the following
questions:

- Am I at risk of overspending or under-spending?
- Are we meeting our minimum contracted spend?
- How can I verify that services are being delivered as expected?
- What are the details of each contract (renewal and expiration dates, contract minimums, rate
  changes, etc.)?
