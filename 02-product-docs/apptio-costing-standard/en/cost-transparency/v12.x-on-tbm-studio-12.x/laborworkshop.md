---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Labor Workshop"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/laborworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Labor Workshop

## Preparing your Labor data

You can get started and prepare your Labor by reviewing the below checkpoints:

1. If you haven’t already done so, load your Labor data including:
   - Actual Headcount
   - Planned Headcount
2. Following Apptio standard
   practices, categorize each raw data set into the category of Labor.
3. If appropriate, apply a date filter to your Labor data.

## About the Labor Identifier

Previously, the Identifier for the Labor Master Data set was automatically populated. This
changed in R12 and you must now map a field to this column in the Labor Master Data Set. Consider
how granular you need the data to be and set your identifier accordingly. For example if you are
costing out at the employee level then map Employee ID to the Labor ID.

You may be inclined to set the identifier to be the employee’s ID number such as in the example
above. However, there are no off-the-shelf reports that display that level of detail. Reporting
pivots the data on attributes such as cost center, role, or other information, so consider mapping
these combinations in the key for bigger clients or if the ID is too sensitive to show in the
model.

## About the Labor Keys

The keys for the Labor Master Data set are all system generated and should not be altered.

| Key | Field key is based on | Logic |
| --- | --- | --- |
| **Cost Source\_Labor Key** | Cost CenterCost PoolCost Sub Pool  Cost Source Key Metafield | Append the text Labor Key to the Cost Center, Cost Pool, Cost Sub Pool, and Cost Source Key Metafield |
| **Labor\_Project Key** | User-defined during mapping | Consider using the project code as this needs to link the Labor object and the Projects object in the model |
| **Labor\_Resource Key** | IT Resource Tower  IT Resource Sub-Tower | Append the text Labor\_Resource to the IT Resource Tower and IT Resource Sub-Tower |
| **Labor\_Time Tracking Key** | Labor ID | Append the text Labor\_Time Tracking to the Labor ID |

## Map data to Labor Master Data

Map your labor data to the Labor Master Data set. Most of the mapping should be self-explanatory
at this point.

If you set your identifier to the employee ID, map **=1** to the Labor Headcount field. If you
used something else for your identifier (such as cost center), map the headcount field in your data
set to the Labor Headcount field.

When mapping planned headcount, ensure you map the headcount value to the Planned Headcount field
(instead of the Headcount field). In 12.7 you can now leverage the Column Map function in your raw
dataset to map to the Labor Master Data ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(Opens in a new tab or window)") )

Points to keep in mind:

- Map your labor data set to the Labor Master Data set.

## Review the Labor object on the models

| Model | Actions |
| --- | --- |
| **Cost** | Ensure values are flowing into the Labor object.  From Cost Source to Labor, allocate using the Data-based Reference (this is the default setting).The keys joining the two data sets include Cost Center, Cost Pool, Cost Sub Pool, and Cost Source Key Metafield.  You may need to adjust the allocation to weight by another value if your unique identifier was not the individual employee ID. |
| **Budget** | Ensure values are flowing into the Labor object.  From Cost Source to Labor, allocate using the Data-based Reference (this is the default setting).The keys joining the two data sets include Cost Center, Cost Pool, Cost Sub Pool, and Cost Source Key Metafield.  You may need to adjust the allocation to weight by another value if your unique identifier was not the individual employee ID. |
| **Forecast** | Ensure values are flowing into the Labor object.  From Cost Source to Labor, allocate using the Data-based Reference (this is the default setting).The keys joining the two data sets include Cost Center, Cost Pool, Cost Sub Pool, and Cost Source Key Metafield.  You may need to adjust the allocation to weight by another value if your unique identifier was not the individual employee ID. |
| **CapEx** | Ensure values are flowing into the Labor object.  From Cost Source to Labor, allocate using the Data-based Reference (this is the default setting).The keys joining the two data sets include Cost Center, Cost Pool, Cost Sub Pool, and Cost Source Key Metafield.  You may need to adjust the allocation to weight by another value if your unique identifier was not the individual employee ID. |
| **CapEx Budget** | Ensure values are flowing into the Labor object.  From Cost Source to Labor, allocate using the Data-based Reference (this is the default setting).The keys joining the two data sets include Cost Center, Cost Pool, Cost Sub Pool, and Cost Source Key Metafield.  You may need to adjust the allocation to weight by another value if your unique identifier was not the individual employee ID. |
| **Capex Forecast** | Ensure values are flowing into the Labor object.  From Cost Source to Labor, allocate using the Data-based Reference (this is the default setting).The keys joining the two data sets include Cost Center, Cost Pool, Cost Sub Pool, and Cost Source Key Metafield.  You may need to adjust the allocation to weight by another value if your unique identifier was not the individual employee ID. |

IT Towers have not yet been mapped so no values will flow to the IT Resource Towers object
yet.

## Review Labor reports

The following reports are updated after you have configured the Labor object:

- Labor Review
- Labor Review - Details
- Labor Analysis
- Data Dimensions - Labor
- Labor Validity

To see details of these reports (including navigation, roles, objectives, and questions answered
for each report), please see the Costing Standard User Guide available in the Online Help.

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
