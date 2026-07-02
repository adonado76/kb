---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Configure multi-currency for Cloud"
breadcrumb: []
source_path: "configuration/multicurrency.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configure multi-currency for Cloud

You can enable multi-currency support for Apptio Cloud products.

Applies to: Cloud for Costing Standard on TBM Studio 12.4.1 and later; Apptio Cloud Business
Management on TBM Studio 12.6 and later

## Introduction

You can enable multi-currency support for Apptio Cloud products to do the following:

- Convert bills into the base currency within your Apptio project
- Display a session currency in reports

For additional information related to the multi-currency feature, see [Configure
multi-currency](../../studio/formulas-and-functions/functions/tablematch.html "Applies to: TBM Studio R12.0 and later; some arguments are available only in R12.5+ as noted below.").

The following configuration instructions are specific to configuring both AWS and Azure billing
files to “ConvertToBase”.

Note:

For Apptio Cloud products, the values in the Type column in the data that you load into the
Currency Exchange table must be labeled as "Actual" in your raw data for the multi-currency feature
to work.

## Instructions for new customers

For new customers, only one step is required: Update the Azure EA Detailed Bill Master
Data.CurrencyCode with the currency code of the bill.

## Instructions for existing customers with CCM configured

Make the following changes:

## AWS Cost Allocation Bill Master Data

Add the following Columns:

- **Base Currency BlendedRate** =If(lookup(CurrencyCode,Currency Exchange,Currency
  Code,Type)="",BlendedRate,ConvertCurrencyToBase(BlendedRate,CurrencyCode,"Actual"))
- **Base Currency CostBeforeTax** =If(lookup(CurrencyCode,Currency Exchange,Currency
  Code,Type)="",CostBeforeTax,ConvertCurrencyToBase(CostBeforeTax,CurrencyCode,"Actual"))
- **Base Currency Credits**=If(lookup(CurrencyCode,Currency Exchange,Currency
  Code,Type)="",Credits,ConvertCurrencyToBase(Credits,CurrencyCode,"Actual"))
- **Base Currency TaxAmount**=If(lookup(CurrencyCode,Currency Exchange,Currency
  Code,Type)="",TaxAmount,ConvertCurrencyToBase(TaxAmount,CurrencyCode,"Actual"))
- **Base Currency TotalCost** =If(lookup(CurrencyCode,Currency Exchange,Currency
  Code,Type)="",TotalCost,ConvertCurrencyToBase(TotalCost,CurrencyCode,"Actual"))

Update the append into Cloud Service Provider Master Data:

Append **AWS Cost Allocation Bill Master Data.****Base Currency TotalCost** into **Cloud
Service Provider Master Data.Cost**

## AWS RDS RI Purchases Master Data

Add the following columns:

- **Base Currency Fixed Price** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",Fixed Price,ConvertCurrencyToBase(Fixed Price,Currency Code,"Actual"))
- **Base Currency Recurring Charge** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",Hourly Recurring Charge,ConvertCurrencyToBase(Hourly Recurring Charge,Currency
  Code,"Actual"))
- **Base Currency Usage Price** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",Usage Price,ConvertCurrencyToBase(Usage Price,Currency Code,"Actual"))

Modify the following existing columns:

- Effective UpFront Cost=Base Currency Fixed Price/((Term in
  Years\*31536000)/Elapsed(Start,Expiration))
- Blended Rate =Hourly Upfront Rate+Base Currency Recurring Charge+Base Currency Usage Price

Update the append into Reserved Instances Master Data

- Append AWS RDS RI Purchases Master Data.Base Currency Recurring Charge into Reserved Instances
  Master Data.Recurring Charges
- Append AWS RDS RI Purchases Master Data.Base Currency Fixed Price into Reserved Instances Master
  Data.UpFront Cost

## AWS RI Purchases Master Data

Add the following columns:

- **Base Currency Fixed Price** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",Fixed Price,ConvertCurrencyToBase(Fixed Price,Currency Code,"Actual"))
- **Base Currency Recurring Charge** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",Hourly Recurring Charge,ConvertCurrencyToBase(Hourly Recurring Charge,Currency
  Code,"Actual"))
- **Base Currency Usage Price** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",Usage Price,ConvertCurrencyToBase(Usage Price,Currency Code,"Actual"))

Modify the following existing columns:

- **Hourly Upfront Rate** =IF(RowCount(AWS RI Modifications Master Data)>0,Effective UpFront
  Cost/(Elapsed(Start,Expiration)/3600),((Base Currency Fixed Price/Term in Years)/8760))
- **Blended Rate** =Hourly Upfront Rate+Base Currency Recurring Charge+Base Currency Usage
  Price
- **Upfront Price Helper** =if(Base Currency Fixed Price=0,SumIf(Parent,Reserved Instance
  ID,Base Currency Fixed Price)\*Footprint Weighting,Base Currency Fixed Price)

Update the append into Reserved Instances Master Data:

- Append AWS RI Purchases Master Data.Base Currency Recurring Charge into Reserved Instances
  Master Data.Recurring Charges
- Append AWS RI Purchases Master Data.Base Currency Fixed Price into Reserved Instances Master
  Data.UpFront Cost

## Recommendations Master Data

Revert the following data sets back to OOTB within the Cloud – Recommendations component:

Recommendations Master Data set

Should there be existing modifications, make the following changes:

- Add new column **Currency Code** ="USD"
- Modify **Estimated Monthly Savings** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code,"Actual"))

## Amazon EC2 Reserved Instances Optimization Transform

**Upfront Cost**
changed to type = Numeric

## Amazon EC2 Reserved Instances Optimization with Term

Add new column Currency Code ="USD"

Modify the following existing columns:

- **Estimated Bill (Current RIs)** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code,"Actual"))
- **Estimated Bill (Current RIs)\_|\_1** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code,"Actual"))
- **Estimated Bill (Optimized RIs)** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code,"Actual"))
- **Estimated Bill (Optimized RIs)\_|\_1** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code,"Actual"))
- **Estimated Monthly Savings** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code,"Actual"))
- **Estimated Monthly Savings\_|\_1** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code,"Actual"))
- **Upfront Cost** =If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code,"Actual"))
- **Upfront Cost\_|\_1**=If(lookup(Currency Code,Currency Exchange,Currency
  Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code,"Actual"))

## Azure EA Detailed Bill Master Data

Add the following columns:

- **CurrencyCodeNOTE** Append a value into this field to define the currency of your Azure
  bill.
- **Base Currency ResourceRate** =If(lookup(CurrencyCode,Currency Exchange,Currency
  Code,Type)="",ResourceRate,ConvertCurrencyToBase(ResourceRate,CurrencyCode,"Actual"))
- **BaseCurrency ExtendedCost** =If(lookup(CurrencyCode,Currency Exchange,Currency
  Code,Type)="",ExtendedCost,ConvertCurrencyToBase(ExtendedCost,CurrencyCode,"Actual"))

Update the append into Cloud Service Provider Master Data:

Append **Azure EA Detailed Bill Master Data.Base Currency ExtendedCost** into **Cloud Service
Provider Master Data.Cost**

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
