---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Cost Source Workshop"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/costsourceworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Cost Source Workshop

Costs are brought into the Cost Source Object at the bottom of the model, usually from
your organization's general ledger. The costs then are allocated to the objects in the model using
strategies based on Technology Business Management best practices.

## Preparing your Cost Source data

You can get started and prepare your Cost Source data by reviewing the below checkpoints:

1. If you haven’t already done so, load your Cost Source Actuals data including:
   - GL Actuals (OpEx and (CapEx)
   - GL Budget (if applicable)
   - GL Forecast (if applicable)
   - Chart of Accounts
   - List of Cost Centers

   We need at least the first month of GL data loaded into Apptio before proceeding.
2. Following Apptio standard practices, categorize each raw data set into the category of Cost
   Source.
3. If appropriate, apply a date filter to your GL actuals data.

## About the Cost Source Identifier

The Identifier for the Cost Source object is pre-defined and should not be altered. It
includes:

- Cost Pool
- Cost Sub Pool
- Account
- Cost Center
- Project ID
- Vendor ID
- UID Metafield
- Fixed Variable
- Expense Type
- Benchmark Identifier

If you need additional granularity (such as down to the individual GL line items), you can
populate the UID Metafield with the appropriate level of detail.

## About the Cost Source Keys

The keys for the Cost Source Master Data set are all pre-defined and should not be altered.

| Key | Field key is based on | Logic |
| --- | --- | --- |
| Cost Source\_Fixed **Asset Key** | Is Depr Fixed Asset Key Metafield | IF Is Depr is “yes”  THEN  Append prefix text of FA\_Key to the Fixed Asset Key Metafield  ELSE  Set the text to CS\_FA\_null |
| **Cost Source\_Labor Key** | Is Labor Cost Center  Cost Pool  Cost Sub Pool  Labor Key Metafield | IF Is Labor is “yes”  THEN  Append prefix text of Labor\_Key to the Cost Center, Cost Pool, Cost Sub Pool and Labor Key Metafield  ELSE  Set the text to CS\_Labor\_null |
| **Cost Source\_Vendor Key** | Is Vendor Is Labor  Is Depr  Vendor ID  Vendor Key Metafield | IF Is Vendor is “yes” and Is Labor is “no” and Is Depr is “no”  THEN  Append prefix text of CS\_Vendor to the Vendor ID and Vendor Key Metafield  ELSE  Set the text to CS\_Vendor\_null |
| **Cost Source\_Project Key** | Is Project Project ID | IF Is Project = “yes”  THEN  Append prefix text of Project\_Key to Project ID  ELSE  Set text to CS\_Project\_null |
| **Cost Source\_Other Cost Pool Key** | Cost Source\_Fixed Asset Key Cost Source\_Labor Key  Cost Source\_Vendor Key  Cost Source\_Project Key  Cost Center  Other Cost Pool Key Metafield | IF Cost Source\_Fixed Asset Key = CS\_FA\_null AND  Cost Source\_Labor Key = CS\_Labor\_null AND  Cost Source\_Vendor Key = CS\_Vendor\_null AND  Cost Source\_Project Key = CS\_Project\_null  THEN  Append prefix text of CC.Map to Cost Center and Other Cost Pool Key Metafield  ELSE  Set the text to CC\_ITRT\_null |
| **Cost Source\_Benchmark Key** | Benchmark Sub-Tower | Append prefix text of “Benchmark” with the Benchmark Sub-Tower |

The above keys are pre-defined and should not be altered. If you need additional granularity,
populate the appropriate metafield with the level of granularity you require. Some suggestions
include:

- Fixed Asset Key Metafield – Cost Center Code
- Vendor Key Metafield – Cost Center Code

## Cost Source Drivers

The Cost Source object has unit drivers that determine what values are fed into the Cost Source
object. For the Cost model, there are two drivers. The table below describes the logic in each of
the drivers. In 12.6 we updated the Drivers to include Plane and not have the complexity that we
have with the current drivers: ([R12.6 Change - Expense Type Change](https://community.apptio.com/docs/DOC-10629 "(Opens in a new tab or window)"))

| Unit Driver | Driver is based on | Logic |
| --- | --- | --- |
| **OpEx Fixed** | Expense Type Fixed Variable  Amount | IF Expense Type is "OpEx" AND Fixed Variable is "Fixed"  THEN  Feed in the Amount  ELSE  Feed in 0 |
| **OpEx Variable** | Expense Type Fixed Variable  Amount | IF Expense Type is "OpEx" AND  Fixed Variable is "Variable"  THEN  Feed in the Amount  ELSE  Feed in 0 |

The other models that contain the Cost Source object (Budget, Forecast, CapEx, CapEx Budget,
CapEx Forecast) contain similar logic still based on the Expense Type, Fixed Variable, and Amount
fields. This means that you must populate these fields in order to drive values into the Cost Source
object.

Typically, the Expense Type and Fixed Variable data is mapped as part of the Chart of Accounts
and then translated (via a LOOKUP column) into the GL.

## Common Computed Columns Needed for Cost Source

Below is a list of computed columns you may need to create. In most cases, the columns are
translating data from your Chart of Accounts and Cost Center List into the GL data set. In 12.7 we
have reached two new features with regards to configuring the Cost Source and this can help with
creating the columns below:

- The Chart of Accounts Master Data now will be leveraged for Machine Learning to help assign
  Accounts to Costs Pools instead of having to pass a spreadsheet back and forth with a customer.
  ([Machine
  Learning for Cost Pools](https://community.apptio.com/docs/DOC-11548 "(Opens in a new tab or window)")).
- In addition with leveraging the Chart of Accounts you can now leverage the Join Step ([Join data](https://community.apptio.com/docs/DOC-5078 "(Opens in a new tab or window)") )
  in the customers General Ledger, Budget, and Forecast to pull in the columns typically found in the
  Chart of Accounts. ([Assign Cost Pools and Map Columns](https://community.apptio.com/docs/DOC-11359 "(Opens in a new tab or window)"))

Note: Leveraging the Join Step for this will eliminate the need for all the Lookups
that contain Chart of Accounts below

- Lookup of Account Description from Chart of Accounts into the GL data set
- Lookup of Cost Pool from Chart of Accounts into the GL data set
- Lookup of Cost Sub-Pool from Chart of Accounts into the GL data set
- Lookup of Fixed/Variable from Chart of Accounts into the GL data set
- Lookup of Discretionary/Non-Discretionary from Chart of Accounts into the GL data set
- Lookup of Account Group from Chart of Accounts into the GL data set
- Lookup of Account Sub-Group from Chart of Accounts into the GL data set
- Lookup of Cost Center Owner from Functional Unit list into the GL data set
- Lookup of IT Owner from Functional Unit list into the GL data set
- Is Depreciation Yes/No flag based on Cost Sub-Pool in the GL data set
- Is Labor Yes/No flag based on Cost Sub-Pool in the GL data set
- Is Project Yes/No flag based on Project Code in the GL data set

For all of these computed columns, you may need to create these in the relevant forecast and
budget data sets as well.

## Map data to Cost Source Master Data

Map your cost source data to the Cost Source Master Data set. Most of the mapping is
self-explanatory. There are no unusual mapping requirements. In 12.7 you can now leverage the Column
Map function in your raw dataset to map to the Cost Source master Data ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Opens in a new tab or window)")
)

Points to keep in mind:

- Map your GL actuals data set to the Cost Source Master Data set.

## Review the Cost Source object on the models

After you have mapped your data to the Cost Source Master data, you can go ahead and review the
Cost Source objects on the models. Review the following models and ensure the values are flowing
into the Cost Source object appropriately.

- Cost
- Budget
- Forecast
- CapEx
- CapEx Budget
- CapEx Forecast

## Review Cost Source reports

The following reports are updated after you have configured the Cost Source object:

- Cost Pool Analysis
- Cost Pool Analysis Details
- Cost Source Validity
- Costing Standard Upload Data Set
- Data Dimensions - Cost Source
- Data Dimensions Dashboard
- Data Dimensions Dashboard - Home
- Financial Analysis
- Financial Analysis - CapEx Transaction
- Financial Analysis - CapEx Trend
- Financial Analysis - OpEx Transaction
- Financial Analysis - OpEx Trend
- Financial Review
- Financial Variance Review
- Help - Allocation Table
- IT Finance - Account Transaction - CapEx Detail
- IT Financials
- TBM Dashboard
- Transaction Details
- Transactions
- Variance Detail

To see details of these reports (including navigation, roles, objectives, and questions answered
for each report), please see the Costing Standard User Guide in the Online Help.

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
