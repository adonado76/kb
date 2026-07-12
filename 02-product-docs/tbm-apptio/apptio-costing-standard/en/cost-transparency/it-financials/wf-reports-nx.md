---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Workforce NX Reports"
breadcrumb:
  - "Costing Standard"
  - "Financial Use Cases"
  - "Workforce"
source_path: "cost-transparency/it-financials/wf-reports-nx.html"
images:
  - "resources/images/ct_images/nrs-lab-analysis.png"
  - "resources/images/ct_images/nrs-lab-ct.png"
  - "resources/images/ct_images/nrs-lab-review.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Workforce NX Reports

The **Labor report collection** provides visibility into labor cost, headcount, and
workforce composition across internal employees and external contractors. These reports support
periodic labor reviews, workforce planning, and variance analysis by combining high-level
summaries with detailed, role- and cost-center-level insights.

The Labor report collection includes:

- Labor Review
- Labor Analysis
- Labor Cost Take-out

## Labor Review

The Labor Review report provides a high-level view of labor cost and headcount across
internal employees and external contractors. It helps organizations monitor labor spend,
headcount trends, open positions, and the balance between internal and external labor.

This report supports periodic labor reviews by highlighting the drivers of labor budget
variances and enabling adjustments to forecasts and workforce plans using general
ledger–level detail.

This report is designed for the following roles:

- IT leadership (CIO -1 /TBM Office)
- Cost Center Owners and Budget Owners
- IT Financial Analysts

**Insights Provided**

- Analyze how labor costs vary by role, location, and sourcing model to identify
  optimization opportunities.
- Identify the mix of internal and external labor supporting IT functions and cost
  centers.
- Understand whether labor spend and headcount are aligned with hiring plans and budget
  targets.
- Detect drivers of labor budget variance by reviewing labor spend and headcount trends
  over time.

For more details on how to use the Labor Review report go [Labor Review](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-labor-review "(Opens in a new tab or window)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nrs-lab-review.png)

## Labor Analysis

The Labor Analysis report provides an interactive, ad hoc view of labor spend and headcount
across the organization. It allows users to dynamically filter data and select metrics to
analyze labor costs, rates, and headcount by cost center, role, employee type, and
location.

This report is designed for deeper analysis of labor spend drivers and supports detailed
investigation into rates, role distribution, and internal versus external labor.

This report is designed for use by the following roles:

- IT Finance Analyst
- Business Analyst

**Insights Provided**

- View a comprehensive workforce summary across all cost centers, including headcount,
  OpEx, budget, variances, and average labor rates.
- Filter labor data by region, cost center, owner, employee type, and role type to support
  targeted analysis.
- Analyze month-over-month trends to identify changes in staffing levels, cost patterns,
  and labor allocation.
- Customize the analysis by selecting additional metrics such as budget variance, internal
  versus external headcount, and average hourly rate to support financial and workforce
  decisions.

For more details on how to use the Labor Analysis report go [Labor Analysis](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-labor-analysis "(Opens in a new tab or window)")

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nrs-lab-analysis.png)

## Labor Cost Take-Out

![Labor Cost](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nrs-lab-ct.png)

| Key Benefits | Details |
| --- | --- |
| - Compare labor rates by role, location, and vendor - Identify high and low-cost locations and vendors for each role - Analyse trends with other factors like cost center and employee type (internal   or external) - View the potential cost savings of sourcing labor resources through lower-cost   locations and vendors   **Questions Answered**   - How much can we save by hiring an Engineer in Seattle vs Chicago? - Should we employ an internally or outsource? - Which vendor gets us the lowest rates? | **For** :  Business Unit Leaders  **How to navigate to reports**: Go to **Reports** > **Labor collections** > **Labor Cost Take-Out** |

**Insights**

Above table provides insights into the possible cost optimization for different vendor.

Highlighted row represents the cost of QA role in Seattle location with TDK vendor can be
reduced/optimized upto 13,866$ by moving the QA role to PointB consulting in Seatle

Average Rate represents Total cost per labor headcount 138432/4=34608.

Lowest rate (this column is hidden) is the lowest Average Rate out of that particular role
type i.e. Software Engr =31136

Potential cost take-out per headcount represents the cost which can be optimized compared
to the lowest value out of Software Engr .`Potential cost take-out per headcount =
Average Rate – Lowest Rate  
 = 34608-1136   
(This is the cost which
can be optimized ) = 3472`

```
Potential Cost Take-Out Overall gives us multiplication of no of labor headcount and Potential Cost Take-Out per headcount = 3472 * 4 = 13866
```
