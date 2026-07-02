---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Custom Azure Daily Report"
breadcrumb: []
source_path: "cost-transparency/reports-v104/customazuredailyreport.html"
images:
  - "resources/images/ct_images/customazuredailyreport_1.png"
  - "resources/images/ct_images/customazuredailyreport_10.png"
  - "resources/images/ct_images/customazuredailyreport_11.png"
  - "resources/images/ct_images/customazuredailyreport_12.png"
  - "resources/images/ct_images/customazuredailyreport_13.png"
  - "resources/images/ct_images/customazuredailyreport_14.png"
  - "resources/images/ct_images/customazuredailyreport_15.png"
  - "resources/images/ct_images/customazuredailyreport_16.png"
  - "resources/images/ct_images/customazuredailyreport_17.png"
  - "resources/images/ct_images/customazuredailyreport_18.png"
  - "resources/images/ct_images/customazuredailyreport_19.png"
  - "resources/images/ct_images/customazuredailyreport_20.png"
  - "resources/images/ct_images/customazuredailyreport_21.png"
  - "resources/images/ct_images/customazuredailyreport_4.png"
  - "resources/images/ct_images/customazuredailyreport_5.png"
  - "resources/images/ct_images/customazuredailyreport_6.png"
  - "resources/images/ct_images/customazuredailyreport_7.png"
  - "resources/images/ct_images/customazuredailyreport_8.png"
  - "resources/images/ct_images/customazuredailyreport_9.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Custom Azure Daily Report

This guide walks you through building a custom Azure Daily Report. The resulting report will look
similar to the image below:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_1.png)

## Edit Report

The **Azure EA Detailed Bill Raw** table needs some modifications before we can build out the
Azure Daily report.

## Adding Formulas

Before you can build your Daily Report, you need to add new formulas to your **Azure EA Detailed
Bill Raw** table.

| Column Name | Formula |
| --- | --- |
| Application | =If(Trim(Resource Group)="","UNKNOWN",Upper(Resource Group)) |
| Business Unit | =Account Name |
| Cost Average | =ExtendedCost/Day Last |
| Date Last Day | =DateFormat(Epoch Last Day,"yyyy-MM-dd") |
| Day Last | =Value(Large(Day)) |
| Department | =Subscription Name |
| Epoch Date | =Days(Date) \* 24 \* 3600 |
| Epoch Last Day | =Large(Epoch Date) |
| Epoch Last Day Before | =Epoch Last Day - (24 \* 3600) |
| Is Last Two Days | =If(Epoch Last Day=Epoch Date OR Epoch Last Day Before=Epoch Date,"Yes","No") |
| IT Resource Tower | =If(Lookup(Lookup,Cloud Service Provider Lookup,Lookup,Tower)="","Unmapped",Lookup(Lookup,Cloud Service Provider Lookup,Lookup,Tower)) |
| Lookup | =Meter Category && {Meter Sub-Category} && Meter Name |
| Pcode | =If(Find(".",Pcode Temporary,3)>0,Pcode Temporary,Left(Pcode Temporary,8)) |
| Pcode Temporary | =Mid(Tags,Find("P.",Tags),11) |
| Provider | ="Microsoft Azure“ |
| Service Category | =If(Lookup(Lookup,Cloud Service Provider Lookup,Lookup,Service Category)="","Unmapped",Lookup(Lookup,Cloud Service Provider Lookup,Lookup,Service Category)) |
| Service Name | =If(Lookup(Lookup,Cloud Service Provider Lookup,Lookup,Service Name)="","Unmapped",Lookup(Lookup,Cloud Service Provider Lookup,Lookup,Service Name)) |
| Service Type | =If(Lookup(Lookup,Cloud Service Provider Lookup,Lookup,Service Type)="","Unmapped",Lookup(Lookup,Cloud Service Provider Lookup,Lookup,Service Type)) |
| Cost Center (Column Override) | =If(Trim(Cost Center)="","Unknown",$\_) |
| Day (Column Override) | =IF(Len(TRIM(Day))=1,"0"&TRIM(Day),TRIM(Day)) |

Additionally, if you have any tags to parse out, you can create a column for each tag.

|  |  |
| --- | --- |
| Environment Name | =IF(FIND("Environment", Tags)>0, split((RIGHT(Tags,LEN(Tags)-FIND("Environment", Tags)-(LEN("Environment")+2))),1,""""), "") |

See [this article](../configuration/tagazuretoschema.html#Parse)
for a detailed explanation on how to use the formula.

## Model the Table

You will need to add a model step in the Transform Pipeline. Modeled tables are necessary for
creating metrics, which we will do next.

## Object Identifier

Depending on the attributes you want to report on, you will need to add the respective columns to
the object identifier. For the purposes of this guide, here are the necessary columns in the object
identifier needed for the report to function at the proper granularity:

## Create calculated metrics

Remember to set the Table Format to Currency for these metrics.

| Metric Name | Formula |
| --- | --- |
| Cloud Invoice Cost MTD | =Cloud Invoice |
| Previous Month Invoice Cost | =PreviousMonth(Cloud Invoice) |
| Average Daily Cost MTD | =Azure EA Detailed Bill Raw.Cost Average |

## Create Reports

You will need to create two new reports: Daily Transparency and Daily Transparency Details. Daily
Transparency will drill to Daily Transparency Detail in the form of a modal pop-up.

## Daily Transparency Report

The basic report is made up of 3 KPIs, a group of 3 Charts and 1 Table, and Slicers as needed.
For this example, 5 common slicers are shown.

KPIs
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_4.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_5.png)

Slicers
:   Slicers can be added as needed to fit your use case/business needs. Here are some examples of
    things you could slice by.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_6.png)

Chart Group
:   The following report components are placed in a group. This allows you to add a pivot that will
    be applied to each chart to view spend by different categories.

Pivot
:   A pivot can be added as needed to fit your use case/business needs. Here are some examples of
    things you could pivot on.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_7.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_8.png)

Charts
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_9.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_10.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_11.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_12.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_13.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_14.png)

    Note:

    If you would like the Daily Invoice Cost Chart to be organized by Day rather than the
    ExtendedCost, you will need to add a Sort to the chart on IT Resource Tower.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_15.png)

Table
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_16.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_17.png)

Charts Grouped
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_18.png)

Daily Transparency Details Report
:   The Details Report gives an expanded view of daily costs by what you are pivoting on.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_19.png)

Table
:   The base table is composed of two columns:

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_20.png)

Column Picker
:   Add columns that make sense for your use case/business needs.

Slicers
:   Add slicers that make sense for your use case/business needs.

Create Drill-To
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_21.png)

    When creating the drill in this report, make sure you add a drill to each pivot you have. For
    this example, that would mean pivoting on IT Resource Tower, Application, Service Category, Customer
    Group, and Business Unit then adding the drill to each column as it appears in the table.
