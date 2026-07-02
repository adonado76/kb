---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Upload and map the Costing Standard Foundation data"
breadcrumb: []
source_path: "configuration/uploadmapctf.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Upload and map the Costing Standard Foundation data

After installing the components and configuring time for the project, the next step is to
upload the Costing Standard Foundation data into the application and map it to the master data
tables.

Applies to: Costing Standard on TBM Studio 12.0 and later

When you created the Costing Standard project, the application created the supporting data tables
and master data tables. Several tables are populated with standard entries. Most of the tables are
blank and must be populated with your data.

## Populated data sets

The following data sets contain standard entries:

- Cost Pool Reference List
- IT Resource Tower Reference List

You do not need to upload data into these data sets.

## Blank data sets

The following master data tables are blank and you must populate them with your data:

- Cost Source Master Data
- Fixed Asset Master Data
- Labor Master Data
- Projects Master Data
- Cost Source to IT Resource Master Data

## Load data into a master data table

There are several steps to load data into a master data table:

1. Upload the data into the application as a separate table.
2. If you need to modify the table (e.g.: add columns), add steps to the transform pipeline of the
   table. The goal is to make sure the table includes all of the data you will need when you map the
   data to the master data table. You should not have to use IF statements or Lookups when mapping the
   data set to the master data set.
3. Map the uploaded data set to the master data set.

For details on how to perform these steps, see [Load data into the
Costing Standard application](loaddata.html "Master data tables provide a way to map your data to the data required by the CT application. The information below describes how to load data into the application.") and [Map data to a master data
table](maptomaster.html "After you have uploaded a source data table and transformed it if necessary, you can map it to a master data table. Use the following instructions to map data to a master data table.").

Step-by-step directions for loading your data into each of the master data tables is described in
the following:

- [Populate the Cost Source Master Data table](populatecostsource.html "The Cost Source Master Data table defines the data required for the cost and budget related reports. To populate the table, you must upload cost figures as well as budget figures. To populate the Cost Source Master Data table, upload two data sets: Cost Actuals and Cost Budget. Map the data sets to the Cost Source Master Data table.")
- [Populate the Fixed Asset Master Data table](populatefixedasset.html "The Fixed Asset Master Data table defines the data required to \"light-up\" the cost and budget related reports. To populate the data set, you must upload fixed asset cost figures and map them to the Fixed Asset Master Data table")
- [Populate the Labor Master Data table](populatelabor.html "The Labor Master Data table defines the data required to \"light-up\" the cost and budget related reports. The data provides an in-depth analysis of labor costs for both FTE and contract employees, including comparisons of actual costs and headcount against plan. To populate the Labor Master Data table, upload a labor data table and map it to the Labor Master Data table.")
- [Populate the Cost Source to IT Resource Master Data
  table](populatecostsource2.html "To populate the Cost Source to IT Resource Master Data table, upload a data table that defines the percentage of the other costs to allocate to each cost center. After creating the table, map it to the Cost Source to IT Resource Master Data table.")

## Should I transform the data before or after I import it?

The more closely your data conforms to the master data tables, the easier it will be to map the
data. When possible, generate the required data from your external applications before you import it
into the CTF application. If that is not possible, you can transform the data after you import it.
Both approaches are satisfactory.

## Use mapping tables

If the data you bring into the application does not include the data needed to map the fields to
the target master data table, you will need to create a mapping table to provide the information.
Typically, the mapping data table assigns values to each of the units in a master data table. For
example, you may need to add depreciation, fixed/variable, and discretionary/non-discretionary
information to a general ledger table based on account number. The last three columns in the mapping
table shown belowcan be used to provide this information using the Lookup function.

![](../../resources/images/ct_images/6832_1.png)

Using the table above, you can use the Lookup function to determine the values for each account.
For example, you could use the following formula for the Fixed Variable field:

=Lookup(Account,Chart of Accounts Mapping,Account,{Fixed/Variable})

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
