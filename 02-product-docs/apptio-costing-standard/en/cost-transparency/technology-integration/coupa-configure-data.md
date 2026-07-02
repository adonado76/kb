---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Configure Coupa Data for Apptio"
breadcrumb:
  - "Costing Standard"
  - "Technology Integrations"
  - "Vendor Insights Coupa"
  - "Vendor Insights Coupa Getting Started"
source_path: "cost-transparency/technology-integration/coupa-configure-data.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configure Coupa Data for Apptio

**Overview**

Once the Coupa data is exported and available in BIIT, the data needs to be transformed to be
used by Vendor Insights . This document provides instructions to prepare the Coupa data to be
integrated into Vendor Insights .

When data is imported from Coupa via the Datalink (Classic) Connector:

- The data is exported to individual tables, one per Coupa object, by initial and delta retrieval
  modes.
- Both the initial data and the delta data are appended to each Coupa object's transform table.
- A  Remove Duplicates  step is used to determine the latest Coupa data.
- The cost center and department associated with the expense is looked up from the HR data using
  the Coupa requestor's email.
- Line item amounts are added together to determine the invoice or PO total amount.
- These transform tables are then mapped Vendor Insights ' Master Data Sets (MDS) to allow Vendor Insights ' reports to be generated.

**Prerequisites**

The following data must exist:

- Supplier – initial
- Supplier – delta
- Contracts – initial
- Contracts – delta
- Purchase Orders – initial
- Purchase Orders – delta
- Purchase Order Lines – initial
- Purchase Order Lines – delta
- Purchase Order Line Accounts – initial
- Purchase Order Line Accounts – delta
- Invoices – initial
- Invoices – delta
- Invoice Lines– initial
- Invoice Lines – delta
- Invoice Line Accounts – initial
- Invoice Line Accounts - delta

**NOTE**  : If the full initial data is retrieved each month, then the delta data is not needed.

**Instructions**

**Task 1: Retrieve HR data**

Retrieve the following fields from your HR system:

- Full Name
- Email
- Cost Center
- Cost Center Name
- Cost Center Owner
- Department
- Department Description

**Task 2: Create the HR reference table**

HR data is used to determine the cost center and department associated with each expense. The
Coupa requester's email is used to determine the cost center and department. HR data provides
supplemental data to ensure that any data that may not exist in a Coupa out-of-the-box
implementation is available in Apptio .

1. Create a table and upload the  **HR**   raw table:
   - **Table name**  - HR Data Raw
   - **Category**  - z\_Vendor Insights\_Raw
   - **Data source**  - File upload
   - **Initial data source**  - <HR data>
   - **Usage**  - List of users, email addresses, and the organization hierarchy from the original
     data source
2. Create the following reference master data tables:
   - **Table name**  - HR Data Master Data.
   - **Category**  - z\_Vendor Insights.
   - **Data source**  - File upload.
   - **Initial data source**  - Go to  [[%=GlobalVariables.CompanyName%] Community](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?documentkey=e2b877ae-b6b8-4bf4-9e2f-36e0caec62b3 "(Opens in a new tab or window)")  and download the file called
      HR Data Master Data  .
   - **Usage**  - Master data to append the HR raw data. List of users, email addresses, and the
     organization hierarchy from the original data source.
3. Append the raw tables to the master data tables:
   - **Master data table name**  - HR Data Master Data
   - **Raw data table name**  - HR Data Raw
   - **Mapped columns from the master data table:** 
     - Full Name
     - Email
     - Cost Center
     - Cost Center Name
     - Cost Center Owner
     - Department
     - Department Desc

Example mapping using demo data (mapping from HR data master data to HR data raw):

- Full Name - Full Name
- Email - Email
- Cost Center - Cost Center
- Cost Center Name - Cost Center Name
- Cost Center Owner - Cost Center Owner
- Department - Department
- Department Desc - Department Desc

**Task 3: Create Coupa-Apptio Status Tablematch tables**

Purchase order statuses from Coupa are more granular than the PO burndown report, which expects
Open or Closed PO status.

Go to  [[%=GlobalVariables.CompanyName%] Community](https://community.apptio.com/community/user/apptio/communities/community-home/all-news/viewdocument?DocumentKey=e2b877ae-b6b8-4bf4-9e2f-36e0caec62b3 "(Opens in a new tab or window)")  and download the file called
 Coupa PO Status to Apptio Status Tablematch  .

Create a mapping table, then upload the spreadsheet containing the default status for Coupa's
purchase order object.

| New table: table name | Category | Data source | Initial data source |
| --- | --- | --- | --- |
| Coupa\_Apptio\_Status\_Tablematch | z\_Coupa\_Transform | File upload | Coupa PO Status to Apptio Status Tablematch |

**Task 4: Create Coupa transform tables**

Create transformation tables, append the Coupa raw data, and transform the data. Each of these
transform tables will require several steps to place them into the final format ready to be appended
to the master datasets.

Overview of the steps needed for the transform tables:

1. Create the transform tables.
2. Append the delta data source to the table.
3. Add formulas to ensure all expected fields exist from Coupa.
4. Remove duplicate rows from the table so that only the latest records exist.
5. Add formulas to calculate additional fields needed to map to the Vendor Insights master data
   tables.
6. Map the raw transform table to the appropriate master dataset.

**Task 4.1: Create the transform tables**

Before you create the transform tables, view the raw tables and ensure the  **Type Override** column is populated. If it is not, fill in each cell in the column with the appropriate type
override.

1. Create the following transform tables for each of the Coupa objects to merge initial and delta
   data together and to ensure all necessary fields needed to map to the master data table exist.
   Create each transform table as a new table using the names in the following table.   
    **TIP**  : Learn how to  [create a table in TBM Studio](../../studio/data_studio/create-table.html "Applies to: TBM Studio 12.0 and later")  .   

   | New table: table name | Category | Data source | Initial data source |
   | --- | --- | --- | --- |
   | Coupa\_Transform\_Supplier | z\_Coupa\_Transform | Existing table | <Raw Coupa data (Initial Supplier data)> |
   | Coupa\_Transform\_Invoice\_Line\_Acct | z\_Coupa\_Transform | Existing table | <Raw Coupa data (Initial Invoice Line account data)> |
   | Coupa\_Transform\_Invoice\_Line | z\_Coupa\_Transform | Existing table | <Raw Coupa data (Initial Invoice Line data)> |
   | Coupa\_Transform\_Invoice | z\_Coupa\_Transform | Existing table | <Raw Coupa data (Initial Invoice data)> |
   | Coupa\_Transform\_PO\_Line\_Acct | z\_Coupa\_Transform | Existing table | <Raw Coupa data (Initial PO Line account data)> |
   | Coupa\_Transform\_PO\_Line | z\_Coupa\_Transform | Existing table | <Raw Coupa data (Initial PO Line data)> |
   | Coupa\_Transform\_PO | z\_Coupa\_Transform | Existing table | <Raw Coupa data (Initial PO data)> |
   | Coupa\_Transform\_Contract | z\_Coupa\_Transform | Existing table | <Raw Coupa data (Initial Contract data)> |
2. Click the  **Source**  step, then click  **Existing Table**  .
3. In the  **Existing Table**  step, select the  **Input Table**  values associated with the
   created table (see step 1 for these values).
4. Add the  Append  step to the data transform.
   - Click  **Append Table**  , then select the name of the delta table to append.   
       
      **Example**  : Coupa\_Supplier\_Delta\_Raw)
   - Map the delta field names to the transform tables. Each field should match 1 to 1.
   - (Optional) If there are any additional fields in the delta data that were not part of the
     initial data, then add these additional fields from the delta data to this transform table.
5. Add the  **Formulas**  step, and then add the following formula to all six transform tables:
   - **Column name**  - Key
   - **Type**  - Label
   - **Formula**  -  `=trim(Coupa ID)`
6. Add the  **Remove Duplicates**  step and then select the following:
   - **Key Column**  - Key
   - **Comparison Column**  - Updated At
   - **Comparison Type**  - Largest
7. For the  `Coupa_Transform_PO_New`  table, add the  **Hide and Rename**  step.
   Then, click  **Add Columns**  , and then add the following columns:   

   | Column name | Visible | Rename to |
   | --- | --- | --- |
   | Department | Checked | Department Description |
   | Purchase Order Date | Checked | PO Date Orig |
   | Purchase Order Number | Checked | PO No |
8. Some Coupa fields may be missing because they were not populated or not configured in Coupa. If
   a field does not exist, add the missing field name and populate the field with a blank value. Coupa
   data output may be missing any of the following fields:
   - Cost Center
   - Department
   - Tower
   - Sub-Tower
   - Cost Pool
   - Cost Sub-Pool
9. Formulas are required to merge data from multiple sources and to convert the data format to the
   value needed by the Vendor Insights Master Data tables. Click  **Formulas**  , then add the
   following formulas to the transform tables:

**Task 4.2: Coupa\_Transform\_Supplier**

In this example, all fields with the value "" are not present in
the Coupa raw data.

| Column name | Type | Formula |
| --- | --- | --- |
| Default Commodity | Label | `=if(Vendor Description = "Default Commodity:", "",Default Commodity Ref)` |
| Default Commodity Ref | Label | `=Right(Vendor Description, len(Vendor Description)-find(": ",Vendor Description))` |
| Vendor Service | Label | `=Default Commodity` |
| Parent Vendor ID | Label | **NOTE**  : From the  **Select column to edit**  list, select the data type.    `=Parent Vendor Coupa ID & " - " & Parent Vendor ID` |
| Vendor Location | Label | `=Primary Address City&&Primary Address State&&Primary Address Country` |
| Vendor ID | Label | **NOTE**  : From the  **Select column to edit**  list, select the data type.    `=Coupa ID & " - " & Vendor ID` |
| Count | Numeric | `=1` |
| IT Tower | Label | `=""` |
| IT Sub-Tower | Label | `=""` |
| Primary Address City | Label | `=""` |
| Primary Address Country | Label | `=""` |
| Primary Address State | Label | `=""` |
| Vendor Type | Label | `=""` |

**Task 4.3: Coupa\_Transform\_Invoice\_Line\_Acct**

| Column name | Type | Formula |
| --- | --- | --- |
| Cost Center Name from Line | Label | `={Account Segment 02}` |
| Cost Center Number from Line | Label | `=Lookup(Cost Center Name from Line,HR Data Master Data,Cost Center Name,Cost Center)` |
| PO-Line | Label | `=Purchase Order Number&" - " & PO Line Num` |
| PO Amount | Numeric | `=SumIf(PO Coupa ID,PO Coupa ID, Item Total)` |
| Count | Numeric | `=1` |

**Task 4.4: Coupa\_Transform\_Invoice\_Line**

Cost center data can come from Coupa via a custom field, an Account
segment field, or it may require you look up the data using the HR data. The cost center value needs
to be mapped into the expected field name to be used by other formulas.

In the following example, the cost center name is stored in the  **Account Segment 02** 
field in the Coupa raw data. If the value is blank, then the cost center number needs to be looked
up from a reference table (HR Data Master Data).

If cost center data does not exist in Coupa raw data, then use the formula  `=""` .

| Column name | Type | Formula |
| --- | --- | --- |
| Account ID | Label | `=Trim(Account ID If)` |
| Account ID If | Label | `=left(Account,Find(" - ",Account))` |
| Account ID Ref | Label | `=right(Account,len(Account)- Find(" - ",Account)-2)` |
| Account Desc | Label | `=trim(Account Desc If)` |
| Account Desc If | Label | `=if(Account CONTAINS " - ",Account Desc Ref,Account)` |
| Account Desc Ref | Label | `=right(Account,len(Account)- Find(" - ",Account)-2)` |
| Count | Numeric | `=1` |
| Cost Center Name from Line | Label | `={Account Segment 02}` |
| Cost Center Number from Line | Label | `=Lookup(Cost Center Name from Line,HR Data Master Data,Cost Center Name,Cost Center)` |
| Invoice Coupa ID str | Label | `=trim(Invoice Coupa ID)` |

**Task 4.5: Coupa\_Transform\_Invoice**

| Column name | Type | Formula |
| --- | --- | --- |
| Cost Center | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Center Number from Line)` |
| Cost Center Name | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Center Name from Line)` |
| Cost Center Owner | Label | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Cost Center Owner)` |
| Tower | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Tower)` |
| Sub-Tower | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,{Sub-Tower})` |
| Cost Pool | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Pool)` |
| Cost Sub-Pool | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Sub Pool)` |
| Department | Label | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Department)` |
| Department Description | Label | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Department Desc)` |
| Account | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Account ID)` |
| Account Description | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Account Desc)` |
| Invoice Date Abridged | Date format:   mm   dd   yyyy | `=Dateformat(Split(Invoice Date,1,"T"),"MM/dd/yyyy")` |
| Invoice Date Abridged Text | Label | `=Invoice Date Abridged` |
| Description | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Invoice Line Description)` |
| Contract Coupa ID | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Contract Coupa ID)` |
| Parent Vendor Coupa ID | Label | `=Lookup(Vendor Coupa ID,Coupa_Transform_Supplier,Coupa ID,Parent Vendor Coupa ID)` |
| PO No | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,PO No)` |
| PO Coupa ID | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,PO Coupa ID)` |
| Invoice Number | Label | `=if(Invoice ID="", "Coupa Invoice ID: "&Coupa ID, Invoice ID)` |
| Purchase Order Number | Label | `=if(PO Coupa ID="" OR PO No ="","",PO Coupa ID & " - " & PO No)` |
| Vendor ID | Label | **NOTE**  : From the  **Select column to edit**  list, select the data type.    `=Vendor Coupa ID & " - " & Vendor ID` |
| Vendor Name | Label | **NOTE**  : From the  **Select column to edit**  list, select the data type. |
| Accounts Payable ID | Label | `=Coupa ID` |
| Count | Numeric | `=1` |

**Task 4.6: Coupa\_Transform\_PO\_Line\_Acct**

| Column name | Type | Formula |
| --- | --- | --- |
| Cost Center Name from Line | Label | `={Account Segment 02}` |
| Cost Center Number from Line | Label | `=Lookup(Cost Center Name from Line,HR Data Master Data,Cost Center Name,Cost Center)` |
| PO-Line | Label | `=Purchase Order Number&" - " & PO Line Num` |
| PO Amount | Numeric | `=SumIf(PO Coupa ID,PO Coupa ID, Item Total)` |
| Count | Numeric | `=1` |

**Task 4.7: Coupa\_Transform\_PO\_Line**

| Column name | Type | Formula |
| --- | --- | --- |
| Cost Center Name from Line | Label | `={Account Segment 02}` |
| Cost Center Number from Line | Label | `=Lookup(Cost Center Name from Line,HR Data Master Data,Cost Center Name,Cost Center)` |
| PO-Line | Label | `=Purchase Order Number&" - " & PO Line Num` |
| PO Amount | Numeric | `=SumIf(PO Coupa ID,PO Coupa ID, Item Total)` |
| Count | Numeric | `=1` |

**Task 4.8: Coupa\_Transform\_PO**

| Column name | Type | Formula |
| --- | --- | --- |
| Cost Center | Label | `=Lookup(Coupa ID,Coupa_Transform_PO_Line,PO Coupa ID,Cost Center Number from Line)` |
| Cost Center Name | Label | `=Lookup(Coupa ID,Coupa_Transform_PO_Line,PO Coupa ID,Cost Center Name from Line)` |
| Cost Center Owner | Label | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Cost Center Owner)` |
| Tower | Label | `=Lookup(Coupa ID,Coupa_Transform_PO_Line,PO Coupa ID,Tower)` |
| Sub-Tower | Label | `=Lookup(Coupa ID,Coupa_PO_Line,PO Coupa ID,{Sub-Tower})` |
| Cost Pool | Label | `=Lookup(Coupa ID,Coupa_Transform_Invoice_Line,Invoice Coupa ID,Cost Pool)` |
| Cost Sub-Pool | Label | `=Lookup(Coupa ID,Coupa_Transform_PO_Line,PO Coupa ID,Cost Sub Pool)` |
| Department | Label | `=Lookup(Cost Center,HR Data Master Data,Cost Center,Department)` |
| Department Description | Label | **NOTE**  : From the  **Select column to edit**  list, select the data type. |
| Amount | Numeric | `=Requisition Total Amount` |
| Amount\_derivedFromPOLine | Numeric | `=Lookup(Coupa ID, Coupa_Transform_PO_Line,PO Coupa ID,PO Amount)` |
| Purchase Order Date | Date format:   mm   dd   yyyy | `=Dateformat(Split(PO Date Orig,1,"T"),"MM/dd/yyyy")` |
| PO-1 | Label | `=PO No&" - 1"` |
| PO-2 | Label | `=PO No&" - 2"` |
| PO-3 | Label | `=PO No&" - 3"` |
| PO-4 | Label | `=PO No&" - 4"` |
| PO-1 Lookup | Label | `=Lookup({PO-1},Coupa_Transform_PO_Line,{PO-Line},Item Name)` |
| PO-2 Lookup | Label | `=Lookup({PO-2},Coupa_Transform_PO_Line,{PO-Line},Item Name)` |
| PO-3 Lookup | Label | `=Lookup({PO-3},Coupa_Transform_PO_Line,{PO-Line},Item Name)` |
| PO-2 If | Label | `=if({PO-2 Lookup}="", "","; " & {PO-2 Lookup})` |
| PO-3 If | Label | `=if({PO-3 Lookup}="", "","; " & {PO-3 Lookup})` |
| Purchase Order Description | Label | `={PO-1 Lookup}&{PO-2 If}&{PO-3 If}` |
| Status Upper | Label | `=Upper(Status)` |
| Purchase Order Status | Label | `=Lookup(Status Upper,Coupa_Apptio_Status_Tablematch,Coupa Status,Apptio Status)` |
| Purchase Order Number | Label | `=PO No` |
| Vendor ID | Label | `=Vendor Coupa ID & " - " & Vendor ID` |
| Vendor Name | Label | **NOTE**  : From the  **Select column to edit**  list, select the data type. |
| Prior Monetary Amount | Numeric | `=Accounts Payable Raw Historic:Prior Years Monetary Amount[PO=Purchase Order Number]` |
| Requester | Label | **NOTE**  : From the  **Select column to edit**  list, select the data type. |
| Count | Numeric | `=1` |

**Task 4.9: Coupa\_Transform\_Contract**

| Column name | Type | Formula |
| --- | --- | --- |
| Cost Center Number | Label | `=""` |
| Cost Center Number Lookup | Label | `=if(Cost Center Number!="",Cost Center Number,Cost Center HR Lookup)` |
| Cost Center HR Lookup | Label | `=Lookup(Contract Owner Email,HR Data Master Data,Email,Cost Center)` |
| Department Lookup | Label | `=if(Cost Center Number!="",Department CC HR Lookup,Department Email HR Lookup)` |
| Department CC HR Lookup | Label | `=Lookup(Cost Center Number,HR Data Master Data,Cost Center,Department)` |
| Department Email HR Lookup | Label | `=Lookup(Contract Owner Email,HR Data Master Data,Email,Department)` |
| Count | Numeric | `=1` |
| Contract Start Date | Date format:   mm   dd   yyyy | `=DateFormat(split(Start Date,1,"T"),"MM/dd/yyyy")` |
| Contract End Date | Date format:   mm   dd   yyyy | `=DateFormat(split(End Date,1,"T"),"MM/dd/yyyy")` |
| Vendor Coupa ID str | Label | `=Trim(Vendor Coupa ID)` |
| Vendor Manager | Label | `=Lookup(Vendor Coupa ID str,Vendor Master Data,Vendor ID,Vendor Manager)` |
| Vendor Type | Label | `=Lookup(Vendor Coupa ID str,Vendor Master Data,Vendor ID,Vendor Type)` |
| Parent Contract | Label | **NOTE**  : From the  **Select column to edit**  list, select the data type. |
| Renewal Plans | Label | `""` |
| Cost Center Owner | Label | JHL Cost Center Owner (look up via contract owner email) |

For the  **Coupa\_Transform\_Invoice**  table:

1. Add the  **Date Partition**  step to the data transform.
2. Select the  **Dates are represented in rows**  checkbox.
3. From the  **Start Date Column**  list, select  **Invoice Date Abridged Text**  . Leave
   the  **End Date Column**  list blank.

**Task 4.10: Create a mapping table (PO-to-Contract)**

In addition to the previous transform tables, a mapping table is needed to link the purchase
order with the contract data for Vendor Insights .

1. Create the following transform table as a new table.   
    **TIP**  : Learn how to  [create a table in TBM Studio](../../studio/data_studio/create-table.html "Applies to: TBM Studio 12.0 and later")  .
   - **Table name**  - Coupa\_Transform\_PO-to-Contract
   - **Category**  - z\_Coupa\_Transform
   - **Data source**  - Existing table
   - **Data source**  - Coupa\_Transform\_PO\_Line
2. Click the  **Source**  step, then click  **Existing Table**  .
3. In the  **Existing Table**  step, select the  **Input Table**  value **Coupa\_Transform\_PO\_Line**  .
4. Add the  Filter  step and then add two filters using the following parameters:
   - Column name -  **Contract Coupa ID**  , Filter value -  **Is Not Null**
   - Column name -  **PO Coupa ID**  , Filter value -  **Is Not Null**
5. Add the  **Group**  step, then add the grouping  **PO-Contract Coupa ID**  .
6. Add the  **Formulas**  step, then add the following formulas:

   | Column name | Type | Formula |
   | --- | --- | --- |
   | Contract ID | Label | `=Contract Coupa ID & " - " & Contract ID` |
   | Purchase Order Number | Label | `=PO Coupa ID & " - " & Purchase Order Number` |
7. Save your changes.
