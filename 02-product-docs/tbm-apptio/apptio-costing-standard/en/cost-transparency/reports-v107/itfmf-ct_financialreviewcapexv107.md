---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Financial Review - CapEx report (v107)"
breadcrumb: []
source_path: "cost-transparency/reports-v107/itfmf-ct_financialreviewcapexv107.html"
images:
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_capexspendanalysis.png"
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_opex.png"
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_transactiondetail.png"
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_variancedetail.png"
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_viewby.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Financial Review - CapEx report (v107)

Applies to: Planning and Costing Standard on TBM Studio 12.3 and
later, with Template v107 and later

## Use cases

- Track IT spend by CIO -1 at an executive level, by cost center owner, and by cost pool
- Analyze transaction-level details to understand variance plan drivers
- Identify significant spend-to-plan variances

The **Financial Review - CapEx** report provides an executive view of the overall CapEx budget
variance and CapEx spend of your organization. The report breaks down IT cost per cost pool and
owner so you can determine which IT owners are responsible for the largest IT spend. Various charts
in the report also help you determine whether variances are real or caused by
mis-categorization.

Use this report to create an executive brief that explains IT CapEx spend and to perform the
periodic financial reviews that are essential for effectively managing IT spend. Data in this report
includes general ledger line items so you can adjust plans to accommodate for variance.

Note: The **Financial Review - CapEx** report requires the installation of the CTF
- CapEx component.

This report is designed for use by the following roles:

- CIO -1 (TBM Office)
- Cost center owners
- IT financial analysts

## Display the report

For Costing Standard:

1. Log in to Apptio and navigate to
   **Costing Standard**.
2. On the **Home** page, click **IT Financials**.The **Financial Review** report
   opens.
3. In the report collection tab (element 1, below), click **Financial Review - CapEx**.

For Planning:

1. Log in to Apptio and navigate to
   **Planning > Costing Standard**.
2. On the **Home** page, click **IT Financials**. The **Financial Review** report opens.
3. In the report collection tab (element 1, below), click **Financial Review - CapEx**.

The report contains the following elements.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_opex.png)

(1) Report collection
:   This report collection provides the IT financial details you need to review your spend variances
    and forecast accuracy:

    - [Financial Review (OpEx) report (v107)](itfmf-ct_financialreview107.html)
    - Financial Review - CapEx (v107) (described in this article)
    - [Financial Analysis report (v104 and later)](../reports-v104/itfmf-ct_financialanalysis104.html)
    - [Cost Pool Analysis report (v104 and later)](../reports-v104/itfmf-ct_costpoolanalysis104.html)

(2) Slicers
:   Use the local and global slicers to refine the data in your report. Slicers in this report let
    you see your cost data by region, account group, and organizational accountability, including cost
    center, cost center owner, and owner (for example, CIO -1).

    The following roles can use the slicers in this report for a more personalized view:

    IT Financial Controller or CIO
    :   Without setting any slicers, you can see the overview of the spend across all cost centers in
        the organization. You can drill down into cost pools, cost center owners, and individual
        accounts.

    Cost Center Owner or CIO -1
    :   Set the **Cost Center** or **Cost Center Owner** slicers to filter for your areas of
        responsibility.

    Financial Analyst
    :   Set the **Cost Center** slicer for areas you support, or set a specific account group to
        enable a detailed, cross-organizational category spend analysis.

(3) KPIs
:   KPIs provide a high-level view of your CapEx spend:

    **CapEx** and **CapEx Budget**
    :   These two KPIs show your overall CapEx budget compared to the CapEx for the current month. The
        percentage of variance is shown to the right.

    **CapEx YTD** and **CapEx Budget YTD**
    :   These two KPIs show your CapEx spend compared to the budget YTD. The percentage of variance is
        shown to the right.

    **Annual CapEx** and **Annual CapEx Budget**
    :   These two KPIs show your annual CapEx spend and budget YTD. The percentage of variance is shown
        to the right.

(4) CapEx Budget Variance
:   Use this chart and table to view your CapEx budget variance based on cost pool, account group,
    owner, cost center owner, or cost center ID. You can use this information to view over- or
    under-spend by category and identify the sources of greatest variance or exception to plan. This
    information will help you prioritize where to look for reduction opportunities.

    Select a metric (cost pool, account group, owner, cost center owner, or cost center ID) from the
    **View by** list to populate the **Top Over Budget YTD** and **Top Under Budget YTD**
    charts with the items in the category with the greatest budget variance to plan YTD.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_viewby.png)

    Click a bar in either chart to open a **Variance Detail** dialog that shows the CapEx spend,
    budget, variance, and percentage of variance for the selected metric. Use the options at the top of
    the page to toggle between time periods.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_variancedetail.png)

    Click an account code to see the transaction details from your financial source of record (such
    as your general ledger).

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_transactiondetail.png)

    The **Details** table allows you to see a summary of the CapEx budget, variance, and
    percentage of variance for all items in the selected metric based on the time periods you select
    above the table.

    Questions answered:

    - Where are there significant variances between spend vs. plan?
    - Which cost centers are driving spend vs. plan variance and who is responsible for that cost center?
    - Is a variance real or caused by mis-categorization of an expense?

(5) CapEx Forecast Variance
:   Select a metric (cost pool, account group, owner, cost center owner, or cost center ID) from the
    **View by** list to populate the **Top Over Forecast YTD** and **Top Under Forecast YTD**
    charts with the items with the greatest forecast variance to plan YTD.

    Click a bar in either chart to open a **Variance Detail** dialog that shows
    the CapEx spend, forecast, forecast variance, and percentage of variance for the selected metric.
    Use the options at the top of the page to select a time period.

    Click an account code in the left column to see the transaction details from your financial
    source of record (such as your GL).

    The **Details** table allows you to see a summary of the CapEx forecast, forecast variance,
    and percentage of forecast variance for all items in the selected metric based on the time periods
    you select above the table.

    Questions answered:

    - Where does the largest portion of our IT spend go? By cost pool? By IT owner (for example, CIO-1)? By cost center owner?
    - Where have we seen any significant period-over-period changes in spend?
    - What are the expense line items that contribute to the cost of an IT function?

(6) Spend Analysis
:   Select a metric (cost pool, account group, owner, cost center owner, or cost center ID) from the
    **View by** list to populate the **Top Over Forecast YTD** and **Top Under Forecast YTD**
    charts with the items with the greatest forecast variance to plan YTD.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_capexspendanalysis.png)

    Click a bar the chart to open a **Variance Detail** dialog that shows the CapEx spend,
    forecast, forecast variance, and percentage of variance for the selected metric. Use the options at
    the top of the page to select a time period.

    Click an account code in the left column to see the transaction details from your financial
    source of record (such as your GL).

    The **Details** table allows you to see a summary of the CapEx forecast, forecast variance,
    and percentage of forecast variance for all items in the selected metric based on the time periods
    you select above the table.

    Questions answered:

    - Where does the largest portion of our IT spend go? By cost pool? By IT owner (for example, CIO-1)? By cost center owner?
    - Where have we seen any significant period-over-period changes in spend?
    - What are the expense line items that contribute to the cost of an IT function?

(7) FY Outlook
:   Use the **FY Outlook** tab to view the CapEx budget, forecast, and spend variance for the
    fiscal year.

    Click any item in the left column to see the transaction details from your financial source of
    record (such as your GL).

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
