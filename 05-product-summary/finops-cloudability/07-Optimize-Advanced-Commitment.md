---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "07-Optimize-Advanced-Commitment"
source_files_count: 6
last_updated: "2026-07-13"
---

# 07-Optimize-Advanced-Commitment

## Guide to Advanced Commitment Functionality

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Advanced Commitment Functionality
- **source_path:** SSVCLNQ/product/guide_to_advanced_commitment_functionality.html
- **original_file:** optimize-guide-advanced-commitment-functionality.md
- **images:** []

## Guide to Advanced Commitment Functionality

Summary

Cloudability Commitments advanced features that provide deeper insights into cloud cost optimization. It introduces powerful modals—such as the Coverage Modal and Net Savings Modal—that help users understand how key performance indicators (KPIs) like coverage and net savings are calculated, interpreted, and used to guide strategic decisions. These tools offer transparency into what cloud spend is optimized through commitments, what remains uncovered, and how unused commitments impact overall savings.

With integrated reporting links and detailed breakdowns, users can move from high-level metrics to actionable insights, enabling smarter commitment renewals, improved chargeback/showback processes, and more confident financial planning. Whether you're analyzing performance or identifying optimization opportunities, these tools will help you to maximize the value of your cloud commitments.

---

## Advanced Commitment Functionality FAQ

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Advanced Commitment Functionality > Advanced Commitment Functionality FAQ
- **source_path:** SSVCLNQ/product/advanced_commitment_functionality_faq.html
- **original_file:** functionality-advanced-commitment-faq.md
- **images:** []

## Advanced Commitment Functionality FAQ

---

## Coverage Modal

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Advanced Commitment Functionality > Coverage Modal
- **source_path:** SSVCLNQ/product/coverage_modal.html
- **original_file:** functionality-coverage-modal.md
- **images:** []

## Coverage Modal

### Purpose

As previously discussed, coverage is an important KPI. It gives insight into both performance, what you currently have rate optimized through commitments, and risk, what percent of your total committable spend is currently covered. The coverage modal exposes how this KPI is calculated to give our users confidence and to unlock insights around performance and opportunity.

### How to Access

Currently, you can access the coverage modal via the details button on the coverage KPI on the portfolio page. We have future plans to provide access to this modal on the recommendations and manger pages. The modal inherits the current header selection and filters on the page such that the modal data is always in context to what you were previously viewing.

### Layout of the Coverage Modal

Coverage Calculation: The modal will first show what two values in the chart below were used to calculate the coverage metric.

Coverage Metric Breakdown : The modal then breaks down each of the covered and uncovered costs. Taking inspiration from a financial statement, the values direct proceeding a line is a sum of the previous values.

Vendor Coverage Summary : To provide a sense of materiality when assessing different service coverage metrics, we provide the covered, uncovered, and ineligible ODE values for the selected vendor. Note that this section does not change with the current header selection and filters on the underlying page.

Important : All amounts in the Coverage Modal are expressed in terms of on-demand equivalent (ODE) costs. For 'uncovered' values, this means that they are in terms of on-demand, and thus the on-demand value = ODE. For 'covered' values, this means that the value shown is not cost, it is ODE. This allows for an apples-to-apples comparison across covered and uncovered costs.

### Coverage Modal Terminology

All vales are in terms of ODE. First, a reminder of two important terms:

Resource–based Commitments: Abbreviated to resource commitments. Provides a discount in exchange for a commitment to a certain amount of usage on a product or service (Reserved Instance, CUD).

Spend-based Commitments: Abbreviated to spend commitments. Provides a discount in exchange for a commitment to a certain amount of spend on a product or service (Savings Plan, Flexible CUD).

Coverage Metric Breakdown - Covered

- Resource Covered : The covered amount fulfilled by resource based commitments.
- Spend Covered : The covered amount fulfilled by spend based commitments.
- Spend Covered, Resource Eligible : Portion covered by spend commitments that could have been covered by resource commitments given the same eligibility rules.
- Resource Covered, Spend Eligible : Portion covered by resource commitments that could have been covered by spend commitments given the same eligibility rules.
- Total Covered Amount : The ODE of the total amount covered.

Coverage Metric Breakdown - Uncovered

- Spend Exclusive Uncovered : On-demand usage that only a spend commitment could have covered.
- Resource Exclusive Uncovered : On-demand usage that only a resource commitment could have covered.
- Nonexclusive Uncovered : On-demand usage that either a resource or spend commitment could have covered.
- Total Uncovered Amount : The total amount that could have—but was not—covered.

Coverage Metric Breakdown - Total amount

- Total Amount : The Total Covered Amount + the Total Uncovered Amount. Another interpretation is this value is the ODE of what could have or was covered by commitments.

Vendor Coverage Summary

- Covered Amount : The amount commitments covered. Note that this value ignores commitment cost that was left unutilized.
- Uncovered Amount : The amount that commitments did not cover. Because it was billed on-demand, this can be viewed as both ODE and actual cost.
- Commitment Ineligible : Costs that cannot be covered by commitments due to service or usage type rules.
- Total Service Amount : The total ODE (cost if no commitments were purchased for the given vendor) of the services supported by Cloudability Commitments. (See Commitment Types Summary)
- Sustained Use Discount Credits (SUDs) : A GCP specific monthly discount for sustained GCE usage when not receiving other discounts. Minor but included here for awareness.

### Covered vs. Uncovered Usage: How to Interpret

Coverage helps you answer two questions:

1. How much of my eligible demand was optimized through discounted rates? (covered)
1. Where could commitments have applied but didn’t? (uncovered)

Potential Interpretations of data

- A high Spend Covered share with large Resource Eligible overlap may indicate room to convert some demand into more resource commitments that often carry a higher commitment discount rate (CDR).
- High Nonexclusive Uncovered suggests broad opportunity—either resource or spend commitments could close the gap. Use Recommendations to determine what category mix is right for your risk tolerance.
- High Resource Exclusive Uncovered often points to specific instance families/regions lacking resource commitments. Spend commitments wouldn't apply here so a resource specific commitment strategy must be created to optimize this spend.
- High Spend Exclusive Uncovered can indicate infrequent, mixed, or cross service usage patterns better suited to spend commitments. Take solace in knowing this spend can not be further optimized with a resource commitment.

Reminder: If your organization uses custom pricing, the ODE baseline will reflect those rates; savings rates derived from ODE will differ from retail baselines.

### Reporting Link Integration

Debuting with GCP, we have introduced deep linking into the values shown on the coverage modal. These links open a new tab and build a report using Cloudability native reporting. This feature further extends the purpose of modal in the first place by:

- Exposing the underlying costs such that there is full transparency to how the coverage KPI was calculated.
- Exposing the underlying covered costs for chargeback/show back use cases.
- Exposing the underlying covered costs to develop an understanding of what was covered for the purpose of determine whether a commitment renewal is appropriate.
- Exposing the underlying uncovered costs to develop an understanding of whether or not this cost is stable enough that it would result in savings if covered by a commitment. In conjunction with the recommendations functionality, users can develop confidence that future purposes will result in a positive outcome for a risk worth taking.

### Key Takeaways

- Coverage is presented in ODE to standardize interpretation across providers.
- The modal separates what was covered from what could have been covered, and classifies the uncovered portion by eligibility (resource only, spend only, either).
- Use the reporting links to move from signal to root cause, then trial strategies in Commitment Recommendations.

---

## Net Savings Modal

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Advanced Commitment Functionality > Net Savings Modal
- **source_path:** SSVCLNQ/product/net_savings_modal.html
- **original_file:** functionality-net-savings-modal.md
- **images:** []

## Net Savings Modal

### Purpose

Net Savings is the most important KPI. It is ultimately what is used to clearly communicate out performance and justify past and future commitment purchases, as such, we want to bring transparency and added detail to how this KPI is calculated. This modal attempts to satisfy this desire.

### How to Access

Soon, you can access the coverage modal via the details button on the Net Savings KPI on the portfolio page. We have future plans to provide access to this modal on the recommendations and manger pages. The modal inherits the current header selection and filters on the page such that the modal data is always in context to what you were previously viewing.

### Layout of the Net Savings Modal

Net Savings Calculation — Explicitly displays [gross] savings and waste (unused commitment) for a given reporting range. Savings - Waste = Net Savings.

Aggregate Net Savings Histogram — Time series daily chart with green bars (when savings is greater than waste) and red bars (when waste is greater than savings). This UI mirrors the Net Savings chart displayed in the Details Panel for a given commitment. Here, it is simply aggregated across whatever commitments are shown on the table.

Forecasted Net Savings by Year — As a nice to have, we show the expected net savings by year assuming a similar utilization percentage as the current selection. Note that this value is directionally correct given that it makes some assumptions and ignores future purchases. It does include an understanding of future expiration's.

### Net Savings Modal Terminology

Savings - The difference between the covered ODE and the commitment cost for the selected period. Savings is implied as 'gross'.

Waste - Value of unused commitments over the period.

Net Savings - The KPI. Savings - Waste.

### Interpreting Net Savings vs. Waste

Use the top cards to anchor on what happened (Actuals) and what we expect (Forecast). Then use the bars to understand why:

All Green - No days exist where the waste from your portfolio selection was greater than the savings it generated.

Consistent green, minimal red - Healthy utilization of purchased commitments.

Green with periodic red - Seasonal or scheduling gaps. Ensure you understand your workloads before making additional purchases. Understand whether the more flexible spend commitments could be more advantageous that resource commitments that have limited applicable scope.

Frequent red spikes - Systematic overbuying; evaluate exchanges/convertibles or reduce future purchase size/term.

### Key Takeaways

Net Savings = Savings − Waste is the primary performance indicator for commitments.

Know that you can track expected savings by year via this modal.

---

## Supplemental Guide to GCP's Spend CUD Program

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Advanced Commitment Functionality > Supplemental Guide to GCP's Spend CUD Program
- **source_path:** SSVCLNQ/product/supplemental_guide_to_gcp_s_spend_cud_program.html
- **original_file:** functionality-supplemental-guide-gcps-spend-cud-program.md
- **images:**
  - 03-media/apptio-cloudability-standard/migration-date-gcp-console.png

## Supplemental Guide to GCP's Spend CUD Program

Instructions to backfill data for customers who voluntarily migrated to the new Spend CUD Program before February 1st, 2026

Customers need us to refetch GCP data dating back to the month of their migration. There are three cohorts:

1. Forced Migration: Customers who were force migrated by GCP during the first week of February have been taken care of. No further action is needed by our customers/field to support this cohort.
1. Voluntary Migration, Customer Communicated Awareness: For customers that migrated and let us know, we have gone ahead and refetched your data on your behalf.
1. Voluntary Migration, Customer Did Not Communicate Awareness: For customers who have not notified us, please file a support case with the following information:

<Your name> voluntarily migrated to GCP’s New Spend CUD Program and is requesting a refetch of their GCP data dating back to their migration date. Provided is the requested information about their account: Customer Name, Frontdoor Region, Frontdoor Customer Name, FrontdoorEnvironment Name, Internal Contact, Migration Date, Billing Accounts, and whether or not the accounts are credentialed as detailed or standard billing.

Note the account information is not required but is much preferred since there is a non-trivial cost to be running these refetches. If you do not know if the refetch took place on your behalf, please reach out to your account team. The date for your migration can be found in the GCP console. See below:

If you do not know if the refetch took place on your behalf, please reach out to your account team.

---

## Understanding Commitments Using Cloudability Native Reporting

<!-- sub-header -->
- **breadcrumb:** Optimize > Guide to Advanced Commitment Functionality > Understanding Commitments Using Cloudability Native Reporting
- **source_path:** SSVCLNQ/product/understanding_commitments_using_cloudability_native_reporting.html
- **original_file:** functionality-understanding-commitments-using-cloudability-native-reporting.md
- **images:** []

## Understanding Commitments Using Cloudability Native Reporting

Savings Plans (SP) is the new discount instrument launched by AWS. This topic explains how the savings plans are different from traditional discounting with reserved instances (RI) and also gives in depth knowledge into billing implications. You can use the Lease Type dimension, along with other regular dimensions and metrics about your SP usage.

Comparison of RIs

- The discount rates are identical between EC2 Instance SPs and Standard RIs, and between Compute SPs and Convertible RIs.
- With Savings Plans, you can make a commitment above the service and regional level (in the case of compute savings plans). This has major implications for how you plan and govern your cloud bill.
- Instead of committing to instance hours , you are now committing to dollar hours . You can verify if the dollars per hour you are committing to are the after Savings Plan discount dollars or the net cost.

Deep dive into billing implications

The major differences between how Savings Plans and RIs are handled in the detailed billing (CUR file) are mentioned here:

- The usage hours covered by SPs are largely represented as On Demand hours. The item description looks like $0.156 per On Demand Linux ... The standard cost metrics Unblended Cost and Unblended Rate are based on the On Demand figures. This is in contrast to RIs where the figures are heavily reduced.
- While the recurring costs for RIs (in the case of no-upfront or partial upfront) appeared as one line item at the beginning of each month for SPs, the recurring costs are broken into individual lines for each hour in the month. All the lines for the month load as the month begins, meaning that you have future cost reporting in the CUR file.
- There is a brand new type of billing line called Negation that allows the regular cost metrics to accurately represent your bill at the monthly level.

Use Case

Let us see how this holds together for one SP being consumed over one hour. This is a very simple example from the CUR file for a no-upfront EC2 Instance Savings Plan:

![Notes Icon](../images/understanding_how_aws_savingsmceclip0.jpg)

The first two lines are the actual EC2 instance usage hours which fully consume the SP for that hour.

The scenario

The Unblended Cost nets out to the recurring fee, which is our discounted rate. This is a result of the negation line completely negating the two usage lines. However, neither the negation nor the recurring lines include the resource ID or important information, like tags. This means that if you are allocating costs based on tags or resource IDs, you are going to get the On-Demand cost for hours covered by SPs and heavily reduced costs for hours covered by RIs. What to do?

The solution

Cloudability gives you two straightforward ways to fairly allocate cost in a world where RIs and SPs are impacting cost line items. The Cost (List) metric completely removes the impact of any commitment based discounting, thereby removing the unpredictable nature of discounts being applied. The Cost (Amortized) metric allows you to pass on the benefits to your teams while making sure there's consistent behavior between RIs and SPs. This metric can be used throughout Cloudability and associates the full cost (including the upfront component) of RIs and SPs at the resource level. This allows for a complete True Cost roll up.

Further information

- To know the historical behavior of RIs, see Understanding AWS Cost Metrics: Do You Have a True Cost Metric?
- To know more about reports, see Custom Report .

---
