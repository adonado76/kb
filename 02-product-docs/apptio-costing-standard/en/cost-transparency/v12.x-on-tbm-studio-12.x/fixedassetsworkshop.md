---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Fixed Assets Workshop"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/fixedassetsworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Fixed Assets Workshop

## Preparing your Fixed Assets data

You can get started and prepare your Fixed Assets by reviewing the below checkpoints:

1. If you haven’t already done so, load your Fixed Asset Register.
2. Following Apptio standard
   practices, categorize each raw data set into the category of Fixed Assets.
3. If appropriate, apply a date filter to your fixed assets data.

## About the Fixed Asset Ledger Identifier

The Identifier for the Fixed Asset Ledger object is populated when you map data to the Fixed
Asset Master Data set. Consider the level of detail you need for both modeling and reporting and set
the Identifier. If you have a Fixed Asset Register, this typically lists each individual fixed asset
and so you can use the ID for each asset.

## About the Fixed Asset Keys

The keys for the Fixed Assets Master Data set are all system generated and should not be
altered.

| Key | Field key is based on | Logic |
| --- | --- | --- |
| **Cost Source\_Fixed Asset Key** | Cost Source Key Metafield | Append the text FA\_Key with the Cost Source Key Metafield |
| **Asset\_Resource Key** | IT Resource Tower  IT Resource Sub-Tower | Append the text Asset\_Resource with the IT Resource Tower and IT Resource Sub-Tower |
| **Asset\_Storage Key** | No pre-defined fields | Consider using the Fixed Asset ID assuming each of your storage devices uses the same ID to uniquely identify each asset. |
| **Asset\_Server Key** | No pre-defined fields | Consider using the Fixed Asset ID assuming each of your servers uses the same ID to uniquely identify each asset. |

You only need to populate the Asset\_Storage Key and Asset\_Server Key if you are implementing the
Storage and Servers components. Otherwise, those keys can be left blank.

## Common Computed Columns Needed for Fixed Assets

There are no specific computed column you need to create. It will vary depending on your data.
However, here’s a couple to consider:

- Lookup of IT Resource Tower from a cost center to IT tower mapping data set into the Fixed Assets data set
- Lookup of IT Resource Sub-Tower from a cost center to IT tower mapping data set into the Fixed Assets data set

As appropriate, build the computed columns you need in order to map your data to the Fixed Assets
Master Data set. Remember, you can look at the Master Data set to determine what column might be
necessary.

Make sure you’re creating the columns in the transform of the fixed asset data (not the raw data
set).

## Map data to Fixed Assets Master Data

Map your fixed asset data to the Fixed Asset Master Data set. Most of the mapping should be
self-explanatory at this point.

If you populated the Fixed Asset Key Metafield in the Cost Source Master Data set, ensure you
populate the matching value in the Cost Source Key Metafield in the Fixed Assets Master Data set. In
12.7 you can now leverage the Column Map function in your raw dataset to map to the Fixed Asset
Master Data (Map Columns )

Points to keep in mind:

- Map your fixed asset data set to the Fixed Assets Master Data set.

## Review the Fixed Asset Ledger object on the models

| Model | Actions |
| --- | --- |
| **Cost** | Ensure values are flowing from the Cost Source object to the Fixed Asset Ledger object.  From Cost Source to Fixed Asset Ledger, allocate using the Data-based Reference weighted by Depreciation Amount (this is the default setting).The keys joining the two data sets include the Cost Source/Fixed Asset Key Metafields. |
| **Budget** | Ensure values are flowing from the Cost Source object to the Fixed Asset Ledger object.  If values are not flowing, you may need to check the Automatically create many to many relationship checkbox.  From Cost Source to Fixed Asset Ledger, allocate using the Data-based Reference weighted by Depreciation Amount (this is the default setting).The keys joining the two data sets include the Cost Source/Fixed Asset Key Metafields. |
| **Forecast** | Ensure values are flowing from the Cost Source object to the Fixed Asset Ledger object.  If values are not flowing, you may need to check the Automatically create many to many relationship checkbox.  From Cost Source to Fixed Asset Ledger, allocate using the Data-based Reference weighted by Depreciation Amount (this is the default setting).The keys joining the two data sets include the Cost Source/Fixed Asset Key Metafields. |

IT Towers have not yet been mapped so no values will flow to the IT Resource Towers object
yet.

## Fixed Asset reports

Track fixed asset depreciation and use new fixed asset depreciation reports to make more informed
decisions about current infrastructure costs and anticipated replacement costs.

What Apptio Answers:

- What depreciation remains for existing fixed asset by time periods?
- Which assets are fully depreciated?

Fixed Assets

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
