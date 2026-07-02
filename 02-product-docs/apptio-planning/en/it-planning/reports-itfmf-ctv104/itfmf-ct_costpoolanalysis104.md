---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Cost Pool Analysis report (v104 and later)"
breadcrumb: []
source_path: "it-planning/reports-itfmf-ctv104/itfmf-ct_costpoolanalysis104.html"
images:
  - "resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_costpoolanalysis_breakout.jpg"
  - "resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_costpoolanalysis_details.jpg"
  - "resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_costpoolanalysis_details2.jpg"
  - "resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_costpoolanalysis_overview.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Cost Pool Analysis report (v104 and later)

◆ Applies to: Planning and Costing
Standard on TBM Studio 12.3 and later, with Template v104 and
later

The **Cost Pool Analysis** report aggregates your financial spend into standard categories
(known as cost pools), as defined by the TBM Council. The report further breaks out the cost pool
spend by operational expenditures (OpEx) and capital expenditures (CapEx), as well as fixed and
variable costs.

## Display the report

Navigate to **Costing Standard** > **IT Financials**. The **Financial Review** report
opens.

From the report collection tab (element 1, below), select **Cost Pool Analysis**.

![image](../../../../../03-media/apptio-planning/resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_costpoolanalysis_overview.jpg)

**(1) Report collection**

Each of the reports in this collection provide the financial details you need to review your
spend variances and forecast accuracy:

- [Financial Review
  report (v107)](itfmf-ct_financialreview107.html "◆ Applies to: Planning and Costing Standard on TBM Studio 12.3 and later, with Template v107 and later")
- [Financial
  Review - CapEx report (v107)](itfmf-ct_financialreviewcapexv107.html)
- [Financial
  Analysis report (v104)](itfmf-ct_financialanalysis104.html "◆ Applies to: Planning and Costing Standard on TBM Studio 12.3 and later, with Template v104 and later")
- Cost Pool Analysis (described in this article)

**(2) Slicers**

Use the local and global slicers to refine the data in your report. Slicers in this report let
you see your cost data by region, account group, and organizational accountability, including cost
center, cost center owner, and owner (for example, CIO -1).

The following roles can use the slicers in this report for a more personalized view:

- **IT Financial Controller or CIO.** Without setting any slicers, you can see the overview of
  the spend of each cost pool across the organization. You can drill down into cost pools, cost center
  owners, and individual accounts.
- **Cost Center Owner or CIO -1.** Set the **Cost Center** or **Cost Center Owner**
  slicers to filter for your areas of responsibility.
- **Financial Analyst.** Set the **Cost Center** slicer for areas you support, or set a
  specific account group to enable a detailed, cross-organizational category spend analysis.

**(3) Fixed and Variable OpEx Spend by Cost Pool**

Use this view to understand the financial agility of the IT spend and where opportunities exist
to impact cost in the current fiscal year.

- **Fixed and Variable** displays a chart of the OpEx by cost pool (default tab).
- **Details** displays a spreadsheet of the OpEx by cost pool broken out by fixed variable.
  Expand any item in the **Pool** column by clicking the arrow to the left of the item.

  ![image](../../../../../03-media/apptio-planning/resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_costpoolanalysis_details.jpg)
- **Trend** displays the fixed and variable OpEx over time.

**Questions answered**:

- If demand or consumption drops, do I have the flexibility to reduce spend?
- Where can I consider sourcing changes that will create a more variable cost structure?
- What financial agility is appropriate for our company at this time? Shall I set a percent
  variable target?
- How much of my spend is fixed and variable?
- What is driving the fixed vs. variable spend ratio?

**(4) OpEx and CapEx Spend by Cost Pool**

Use this view to understand the cost pool spend broken out by OpEx and CapEx:

- **OpEx and CapEx** - displays a chart of the OpEx and CapEx by cost pool (default tab).
- **Details** - displays a spreadsheet of the OpEx and CapEx by cost pool. Expand any item in
  the **Cost Pool** column by clicking the arrow to the left of the item.

  ![image](../../../../../03-media/apptio-planning/resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_costpoolanalysis_details2.jpg)
- **Trend** displays the OpEx and CapEx spend over time.

**Questions answered**:

- How much of my spend is CapEx vs. OpEx?
- How does capitalization vary by cost pool?
- Where is most of my spend capitalized?
- How does my CapEx spend vary over the fiscal year? Is there an end-of-year spike (spend it or
  lose it)?

**(5) Summary by Cost Pool**

Use this table to view all cost pools with their fixed and variable costs, and the CapEx and OpEx
expenditures. Additional details, including cost sub-pool and account name, are available.

Click any row in the **Cost Pool** column to display the **Cost Pool Breakout** report,
where you can see the accounts that make up the cost pool or sub-pool you selected.

![image](../../../../../03-media/apptio-planning/resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_costpoolanalysis_breakout.jpg)

Then, click an account code to see the transaction details from your financial source of record
(such as your GL).

![image](../../resources/images/it%20planning_images/itfmf-ct_images/itfmf-ct_costpoolanalysis_transactiondetails.png)

**Questions answered**:

- What accounts are rolling into the cost pool categories?
- What is the budget variance in those accounts?
- What transactions occurred in the current period for an account?
