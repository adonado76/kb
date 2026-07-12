---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Vendor Insights (Dashboard)"
breadcrumb:
  - "Costing Standard"
  - "Report Walkthrough"
  - "Vendor Collection"
source_path: "cost-transparency/vi_content/report-vendor-insights.html"
images:
  - "resources/images/vi_images/vi/export.jpg"
  - "resources/images/vi_images/vi/vi-vendor.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Vendor Insights (Dashboard)

◆ Applies to: Vendor Insights on TBM Studio 12.8 and later (v107)

Use the Vendor Insights dashboard to analyze total vendor portfolio spending across vendor types
and cost pools, and to analyze vendor contract spend and expiration data. This report is designed
for:

- CIO and senior IT leadership
- Application Owners
- Services Owners
- IT Finance Managers
- Vendor Managers

The dashboard provides the following information:

- Vendor distribution by category, with current and trending spend
- Vendor spend per month, quarter, and year, and the manager of each vendor
- Biggest vendor spend by cost pool, and how spend has changed over time
- Distribution of cost pool spend per vendor
- Analysis of contract spend

**Display the Vendor Insights report**

In the  Application  menu, select  Vendor Insights  .

1. Navigate to  Report Collections > Vendors  .
2. From the bar at the top of the page, select  Vendor Insight  .
3. To export or email your data, select  Export  ( ![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/export.jpg) ) at the top right of
   the page and select an export format.

The  **Vendor Insights**  report contains the following elements:

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/vi-vendor.jpg)

**(1) Report collection**

The reports in the  **Vendors**  collection provide the details you need to review vendor
activity and spend, and to analyze the accuracy of your AP, PO, and vendor data:

- Vendor Insights (Dashboard) report (described in this document)
- [Vendor Summary report](report-vendor-summary.html)

**(2) Vendor Type**

Use the Vendor Type charts to understand vendor distribution by type, with their current and
trending spend month over month. Vendor type is derived from the Vendor Category mapping file.

**Bar chart**  . The bar chart shows the number of unique vendors and their total spend in the
current month. Costs not allocated from accounts payable (AP) or purchase orders (PO) are not
included.

**Trend chart**  . The trend chart shows vendor spend per month by vendor type. Use this chart
to watch for anomalies that might need investigation.

**Table**  . Use the table to see more details about the spend and change for each vendor in the
current month, quarter to date, and year to date.

Click any item in the  **Vendor Name**  column to open a  [Vendor Detail report](report-vendor-detail.html)  that has information specific to that
vendor.

**(3) Cost Pool Composition**

Use this section to view the vendor spend broken out by cost pool (for example, External Labor,
Software, Telecom, Outside Services, and more), and the amount of change as the trending spend per
cost pool month over month. The report also helps you see the distribution of your cost pool
spending per vendor.

Use the table to see the current, quarterly, and YTD spend per vendor, broken out cost pool.
Click any item in the  **Vendor Name**  column to open a details page that contains information
specific to that vendor. See the Vendor Detail report.

**(4) Contract Expiration**

**KPIs**

- **Contract Spend Expiring < 1 Yr**  . The total for vendor contracts set to expire in less
  than one year, and the percentage of that total compared to the total spend.
- **Contract Spend Expiring 1 to 3 Yrs**  . The total for vendor contracts set to expire in one to
  three years, and the percentage of that total compared to the total spend.
- **Contract Spend Expiring > 3 Yr**  . The total for vendor contracts set to expire in more
  than three years, and the percentage of that total compared to the total spend.

**Trend chart**  . Use the trend chart to see the trending spend of expiring contracts broken
out by the length of contract month over month.

**Table**  . The table provides an overview contract details, including the contract owner, days
remaining, current spend, spend YTD, and lifetime spend. Click any item in the Contract Name column
to open a details page that has additional information about the contract. To learn more, see the
 [Contract Detail report](report-contract-detail.html)  .

Questions answered

Use this report to answer the following questions:

- What are we spending with preferred vs. commodity vendors?
- Which cost pools compose my vendor costs?
- Where do we have variances in spend?
- What changes should we make to re-balance vendor spend?
- How fragmented/concentrated is spending across vendors?
- Do we have redundant vendors?
