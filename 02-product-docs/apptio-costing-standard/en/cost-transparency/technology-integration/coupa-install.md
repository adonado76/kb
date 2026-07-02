---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Install and configure Vendor Insights using Coupa data"
breadcrumb:
  - "Costing Standard"
  - "Technology Integrations"
  - "Vendor Insights Coupa"
  - "Vendor Insights Coupa Getting Started"
source_path: "cost-transparency/technology-integration/coupa-install.html"
images:
  - "resources/images/vi_images/vi/coupa/coupa5.jpg"
  - "resources/images/vi_images/vi/coupa/coupa6.jpg"
  - "resources/images/vi_images/vi/coupa/coupa7.jpg"
  - "resources/images/vi_images/vi/coupa/coupa_8.jpg"
  - "resources/images/vi_images/vi/coupa/coupa_9.jpg"
  - "resources/images/vi_images/vi/coupa/coupa__10.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Install and configure Vendor Insights using Coupa data

**Overview**

This document provides instructions for the TBMA to deploy Vendor Insights using the Coupa data
from the Coupa Datalink (Classic) Connector.

**Prerequisites**

Before installing Vendor Insights components, you must have:

1. TBM Studio 12.6.1 and Datalink (Classic) 4.8 (Build 11122 or greater). If you are not running
   the correct version or have questions about the version you are running, contact Apptio customer
   support for assistance.
2. A new or existing TBM Studio project dedicated to Vendor Insights exists with time settings
   configured, checked in, and calculated in the development environment.**TIP**: Follow the
   same time period used in Costing Standard or create a time period that starts from the beginning of
   the current year.
   - If you would like Vendor Insights to be a stand-alone product, create a new custom project
     type. Otherwise, you can install the Vendor Insights component into an existing project.
3. Coupa has been configured for Apptio . To learn more, see[Configure Coupa for Apptio](coupa-configure-data.html). Otherwise, the following
   fields will not be available from the Coupa Datalink (Classic) Connector:
   - **IT Tower**- Vendor Master Data
   - **IT Sub-Tower**- Vendor Master Data
   - **Cost Pool**- Accounts Payable Master Data, Purchase Order Master Data
   - **Cost Sub-Pool**- Accounts Payable Master Data, Purchase Order Master Data
4. The Datalink (Classic) Coupa Connector has been configured and executed for both the initial
   and delta data for the following Coupa objects. The output of each of the Coupa Connectors should be
   placed into the`z_Coupa_Raw`folder in TBM Studio . To learn more, see[Configure the Coupa Vendor Insights data for Apptio](config-coupa.html).
     
   This results in the following tables:  

   | Coupa object | Retrieval mode | Catalog | Sample output table name |
   | --- | --- | --- | --- |
   | Suppliers | Initial Data Delta Data | z\_Coupa\_Raw z\_Coupa\_Raw | Coupa\_Supplier\_Initial\_Raw Coupa\_Supplier\_Delta\_Raw |
   | Contracts | Initial Data Delta Data | z\_Coupa\_Raw z\_Coupa\_Raw | Coupa\_Contract\_Initial\_Raw Coupa\_Contract\_Delta\_Raw |
   | Purchase Orders | Initial Data Delta Data | z\_Coupa\_Raw z\_Coupa\_Raw | Coupa\_PO\_Initial\_Raw Coupa\_PO\_Delta\_Raw |
   | Purchase Order Lines | Initial Data Delta Data | z\_Coupa\_Raw z\_Coupa\_Raw | Coupa\_PO\_Line\_Initial\_Raw Coupa\_PO\_Line\_Delta\_Raw |
   | Purchase Order Line Accounts | Initial Data Delta Data | z\_Coupa\_Raw z\_Coupa\_Raw | Coupa\_PO\_Line\_Acct\_Initial\_Raw Coupa\_PO\_Line\_acct\_Delta\_Raw |
   | Invoices | Initial Data Delta Data | z\_Coupa\_Raw z\_Coupa\_Raw | Coupa\_Invoice\_Initial\_Raw Coupa\_Invoice\_Delta\_Raw |
   | Invoice Lines | Initial Data Delta Data | z\_Coupa\_Raw z\_Coupa\_Raw | Coupa\_Invoice\_Line\_Initial\_Raw Coupa\_Invoice\_Line\_Delta\_Raw |
   | Invoice Line Accounts | Initial Data Delta Data | z\_Coupa\_Raw z\_Coupa\_Raw | Coupa\_Invoice\_Line\_Acct\_Initial\_Raw Coupa\_Invoice\_Line\_Acct\_Delta\_Raw |

**Instructions**

**Task 1: Install the Vendor Insights components**

1. Open the project in Studio.
2. Click the**Project**tab.
3. Click**Components**.
4. Click**Vendor Insights Foundation**, then click**Install**.
5. Click**Vendor Insights PO**, then click**Install**.
6. Click**Vendor Insights Contracts**, then click**Install**.
7. Check in your project.

You may need to update the visibility settings in Access Administration to see the Vendor Insights project and reports .

**Task 2: Map the Coupa transform tables to the Vendor Insights master
datasets**

Append the following transformation tables to the Vendor Insights master datasets. Because field
names in the transformation tables are identical to those in the Vendor Insights master datasets,
the field names automatically map to each other (unless otherwise noted).

You will map the following Vendor Insights tables to the associated Coupa Transform tables:

| Vendor Insights table | Coupa Transform table |
| --- | --- |
| Vendor Master Data | Coupa\_Transform\_Supplier |
| Accounts Payable Master Data | Coupa\_Transform\_Invoice |
| Purchase Orders Master Data | Coupa\_Transform\_PO |
| Contracts Master Data | Coupa\_Transform\_Contract |
| PO to Contract Master Data | Coupa\_Transform\_PO-to-Contract |

  

For the exception fields, nothing needs to be mapped.

**Task 2.1: Vendor Master Data**

Map the following master data fields to the associated**Coupa\_Transform\_Supplier**fields:

| Master data field | Coupa\_Transform\_Supplier field |
| --- | --- |
| **Parent Vendor ID** | `=Parent Vendor ID` |
| **Parent Vendor Name** | `=Parent Vendor Name` |
| **Vendor Contract** | `=Vendor Contact` |
| **Vendor Description** | `=Vendor Description` |
| **Vendor Name** | `=Vendor Name` |
| **Vendor Service** | `=Vendor Service` |

**Task 2.2: Accounts Payable Master Data**

Map the following master data fields to the associated**Coupa\_Transform\_Invoice**fields:

| Master data field | Coupa\_Transform\_Invoice field |
| --- | --- |
| **Account** | `=Account` |
| **Account Description** | `=Account Description` |
| **Accounts Payable ID** | `=Vendor Contact` |
| **Cost Center** | TBD |
| **Cost Center Name** | `=Cost Center Name` |
| **Cost Center Owner** | `=Cost Pool` |
| **Cost Sub Pool** | `={Cost Sub-Pool}` |
| **Department** | `=Department` |
| **Department Description** | `=Department Description` |
| **Description** | `=Description` |
| **Invoice Date** | `=Invoice Date Orig` |
| **Invoice Number** | `=Invoice Number` |
| **Monetary Amount** | `=Monetary Amount` |
| **Purchase Order Number** | `=Purchase Order Number` |
| **Vendor ID** | `=Vendor ID` |
| **Vendor Key Metafield** | `=Vendor ID` |
| **Vendor Name** | `=Vendor Name` |

**Task 2.3: Purchase Orders Master Data**

Map the following master data fields to the associated**Coupa\_Transform\_PO**fields:

| Master data field | Coupa\_Transform\_PO field |
| --- | --- |
| **Amount** | `Amount` |
| **Cost Center** | `Cost Center` |
| Cost Center Name | `Cost Center Name` |
| **Cost Center Owner** | `Cost Center Owner` |
| **Department** | `Department` |
| **Department Description** | `Department Description` |
| **Prior Monetary Amount** | `Prior Monetary Amount` |
| **Purchase Order Date** | `Purchase Order Date` |
| **Purchase Order Description** | `Purchase Order Description` |
| **Purchase Order Number** | `Purchase Order Number` |
| **Purchase Order Status** | `Purchase Order Status` |
| **Requester** | `Requester` |
| **Vendor ID** | `Vendor ID` |
| **Vendor Name** | `Vendor Name` |

**Task 2.4: Contracts Master Data**

Map the following master data fields to the associated**Coupa\_Transform\_Contracts**fields:

| Master data field | Coupa\_Transform\_Contracts field |
| --- | --- |
| **Contract Amount** | `=Contract Amount` |
| **Contract Description** | `=Contract Description` |
| **Contract ID** | `=Contract Number` |
| **Contract Number** | `=Contract Number` |
| **Contract Owner** | `=Contract Owner` |
| **Contract Owner Email** | `=Contract Owner Email` |
| **Contract Title** | `=Contract Title` |
| **Cost Center Number** | `=Contract Title` |
| **Contract Title** | `=Cost Center Number Lookup` |
| **Cost Pool** | � |
| **Cost Sub Pool** | � |
| **End Date** | `=Contract End Date` |
| **Function** | � |
| **Minimum Committed Spend** | `Minimum Committed Spend` |
| **Parent Contract** | `Parent Contract` |
| **Renewal Plans** | `Renewal Plans` |
| **Start Date** | `=Contract Start Date` |
| **Status** | `=Status` |
| **Vendor ID** | `=Vendor ID` |
| **Vendor Manager** | `=Vendor Manager` |
| **Vendor Name** | `=Vendor Name` |
| **Vendor Type** | `=Vendor Type` |
| **Contract Notify Days** | `=Contract Notify Days` |

  

**Task 2.5: PO to Contract Master Data**

Map the following master data fields to the associated**Coupa\_Transform\_PO-to-Contract**fields:

- **Contract ID**to`=Contract ID`
- **Purchase Order Number**to`=Purchase Order Number`

**Task 3: Configure the Vendor Insights Foundation component**

The Vendor Insights Foundation component contains the datasets, models, and reports used to
rationalize vendors and understand vendor spending. For more information on this component, see
[Install the Vendor Insights Foundation component](task1-install-foundation.html)
. Vendor Insights configuration is required to update the model and map fields that are not
available in Coupa.

The following tables are missing the fields listed. These fields impact reports in Vendor Insights :

Vendor Master Data:

- Vendor Manager
- Vendor Type
- Cost Pool
- Vendor Owner
- IT Resource Tower
- IT Resource Sub-Tower
- Vendor Function
- Vendor Service
- Vendor Location

Accounts Payable Master Data:

- Account
- Account Description
- Cost Sub Pool
- Cost Pool
- Cost Center
- Cost Center Name
- Cost Center Owner
- Department
- Department Description
- Purchase Order Description

Purchase Order Master Data:

- Cost Center
- Cost Center Name
- Department
- Department Description

Contract Master Data:

- Contract Owner
- Function
- Contract Notify Days
- Department
- Contract Criticality
- Vendor Manager

**Task 4: Configure the Vendor Insights PO component**

The Vendor Insights PO component contains the datasets, models, and reports used to manage
purchase orders (POs). For more information on this component, see<task2-install-po.html>. Additional Vendor Insights configuration is required to
update the model and map fields that are not available in Coupa.

**Task 4.1: Configure the Accounts Payable model**

To configure allocations, create a model to allocate cost from the driver (**Accounts Payable
Master Data**) to the resulting destination (**Purchase Orders**). This allocation will
be stored in a metric called**Payable**.

To do this, you will check out the accounts payable model you want to configure, configure the
accounts payable to purchase order allocation, then configure the accounts payable to the vendors
allocation.

1. In the Studio**Project Explorer**, expand the**Vendors Insights**category, then
   click**Accounts Payable**.
2. On the**Home**tab, click**Check Out**.

**Task 4.1.1:
Configure accounts payable to purchase order allocations**

1. Add a**Model**step, then in the**Select a metric list**, select**Payables**
   .
2. Under**Allocations**, click the**(Purchase Orders)**allocation line.
3. On the**ALLOCATION TO**page, expand the**Distributing**section, clear the**Data Relationship**checkbox, then click**Apply**. This removes the previous
   (out-of-the-box) allocation.
4. Re-select the**Data Relationship**checkbox and add the following new allocation:
   - In the Data Relationship sub-section, click the box under**Source Column**, then in the
     **Accounts Payable Master Data**column, select**Purchase Order Number**.
   - In the Data Relationship sub-section, click the box under**Destination Column**, then in
     the**Purchase Order Master Table**column, select**Purchase Order Number**.
   - Click**OK**to save the configuration.
5. Save your changes.

In the following example, the distribution after the configuration includes:

- **Source Column**: ACCOUNTS PAYABLE MASTER DATA - Purchase Order Number
- **Destination Column**: PURCHASE ORDER MASTER DATA - Purchase Order Number  
  **TIP**: When mapping accounts payable and purchase data, use the most granular field that
  uniquely identifies the purchase order data.

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa6.jpg)

**Task 4.1.2: Configure
accounts payable to vendors allocations**

1. In the Studio**Project Explorer**, expand the**Vendors Insights**category, then
   click**Accounts Payable**.
2. Add a**Model**step, then in the**Select a metric list**, select**Payables**
   .
3. Under**Allocations**, click the**(Vendors)**allocation line.
4. On the**ALLOCATION TO**page, expand the**Distributing**section, clear the**Data Relationship**checkbox, then click**Apply**. This removes the previous
   (out-of-the-box) allocation.
5. Re-select the**Data Relationship**checkbox and add the following new allocation:
   - In the**Data Relationship**sub-section, click the box under**Source Column**,
     then in the**Accounts Payable Master Data**column, select**Vendor ID**.
   - In the**Data Relationship**sub-section, click the box under**Destination Column**
     , then in the**Vendor Master Table**column, select**Vendor ID**.
   - Click**OK**to save the configuration.

In the following example, the distribution after the configuration includes:

- **Source Column**: ACCOUNTS PAYABLE MASTER DATA - Vendor ID
- **Destination Column**: VENDOR MASTER DATA - Vendor ID

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa5.jpg)

**Task 4.2: Configure the Purchase Order model**

To configure allocations, create a model to allocate cost from the driver (**Accounts Payable
Master Data**) to the resulting destination (**Purchase Orders**). This allocation will
be stored in a metric called**Payable**. To do this, you will check out the accounts payable
model you want to configure, configure the purchase order to vendor allocation, then configure the
purchase order to the contract's allocation.

1. In the Studio**Project Explorer**, expand the**Vendors Insights**category, then
   click**Purchase Orders**.
2. On the**Home**tab, click**Check Out**.

**Task 4.2.1: Configure
purchase order to vendors allocations**

In these instructions, the purchase order is mapped to the Vendor
using the Vendor ID (best practice). If the Vendor ID does not exist, use**Normalized Vendor Name**.

1. Add a**Model**step, then in the**Select a metric list**, select**Payables**
   .
2. Under**Allocations**, click the**(Vendors)**allocation line.
3. On the**ALLOCATION TO**page, expand the**From**section, click the**X**next
   to the condition to delete the existing condition.  
   ![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa7.jpg)
4. On the**ALLOCATION TO**page, in the**From**section, select the**Send only
   remaining values (after the other rules run)**checkbox.
5. On the**ALLOCATION TO**page, expand the**Distributing**section, clear the**Data Relationship**checkbox, then click**Apply**. This removes the previous
   (out-of-the-box) allocation.
6. Re-select the**Data Relationship**checkbox and add the following new allocation:
   - In the**Data Relationship**sub-section, click the box under**Source Column**,
     then in the**Purchase Orders Master Data**column, select**Vendor ID**.
   - In the**Data Relationship**sub-section, click the box under**Destination Column**
     , then in the**Vendor Master Table**column, select**Vendor ID**.
   - Click**OK**to save the configuration.
7. Save your changes.

In this example, the distribution after the configuration includes:

- **Source Column**: PURCHASE ORDERS MASTER DATA - Vendor ID
- **Destination Column**: VENDOR MASTER DATA - Vendor ID

**Task 4.2.2: Configure
purchase order to contracts allocations**

1. Add a**Model**step, then in the**Select a metric list**, select**Payables**
   .
2. Under**Allocations**, click the**(PO to Contract)**allocation line.
3. On the**ALLOCATION TO**page, expand the**Distributing**section, clear the**Data Relationship**checkbox, then click**Apply**. This removes the previous
   (out-of-the-box) allocation.
4. Re-select the**Data Relationship**checkbox and add the following new allocation:
   - In the D**ata Relationship**sub-section, click the box under**Source Column**,
     then in the**Purchase Orders Master Data**column, select**Purchase Order Number**.
   - In the**Data Relationship**sub-section, click the box under**Destination Column**
     , then in the**PO to Contract Master Data**column, select**Purchase Order Number**.
   - Click**OK**to save the configuration.
5. Save your changes.

In this example, the distribution after the configuration includes:

- **Source Column**: PURCHASE ORDERS MASTER DATA - Purchase Order Number
- **Destination Column**: PO TO CONTRACT MASTER DATA - Purchase Order Number

**Task 4.3: Configure the Purchase
Order to Contract model**

To configure allocations, create a model to allocate cost from the driver (**Accounts Payable
Master Data**) to the resulting destination (**Purchase Orders**). This allocation will
be stored in a metric called**Payable**. To do this, you will check out the purchase order to
contract model you want to configure, then configure the purchase order to the contract's
allocation.

1. In the Studio**Project Explorer**, expand the**Vendors Insights**category, then
   click**PO to Contract**.
2. On the**Home**tab, click**Check Out**.

**Task 4.3.1: Configure allocations (PO to "PO to Contracts")**

To configure PO to Vendor allocations:

1. On the**Model**page, click on the line going to**(PO to Contract)**allocation.
2. On the**ALLOCATION TO**dialog box, expand the**Distributing**section and uncheck
   the**Data Relationship**checkbox to remove the OOTB allocation. Click**Yes**from the
   **Legacy Warning**dialog box.  
   ![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa_8.jpg)
3. On the**ALLOCATION TO**dialog box, expand the**Distributing**section and select
   the**Data Relationship**checkbox to add a new allocation.
4. In the**Source**tab, click**Choose column**and under**Purchase Order Master
   Data**, select**Purchase Order Number**.
5. In the**Destination**tab, click**Choose column**and under**PO to Contract
   Master Data**, select**Purchase Order Number**.
6. Back in the**Model**page, verify that the following distribution is shown:
   - **Source Column**- Purchase Order Master Data - Purchase Order Number
   - **Destination Column**- PO to Contract Master Data - Purchase Order Number![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa_9.jpg)
7. Click**Ok**.
8. Save your changes.

**Task 4.3.2: Configure allocations
("PO to Contracts" to Contracts)**

1. Under**Allocations**, click the**(Contracts)**allocation line.
2. On the**ALLOCATION TO**page, expand the**Distributing**section, clear the**Data Relationship**checkbox, then click**Apply**. This removes the previous
   (out-of-the-box) allocation.
3. Re-select the**Data Relationship**checkbox and add the following new allocation:
   - In the**Data Relationship**sub-section, click the box under**Source Column**,
     then in the**PO to Contract Master Data**column, select**Contract ID**.
   - In the**Data Relationship**sub-section, click the box under**Destination Column**
     , then in the**Contracts Master Data**column, select**Contract Number**.
   - Click**OK**to save the configuration.

The distribution after the configuration includes:

- **Source Column**: PO TO CONTRACT MASTER DATA - Contract ID
- **Destination Column**: CONTRACTS MASTER DATA - Contract Number

**Task 4.4: Configure the Contracts model**

To configure the allocations, create a model to allocate cost from the driver (**Accounts
Payable Master Data**) to the resulting destination (**Purchase Orders**). This
allocation will be stored in a metric called**Payable**.

**Summary of the steps**:

1. Check out the**Applications Master Data**table.
2. Join that table to**Contracts Application Master Data**.
3. Check out the**Contracts**model.
4. Configure the contracts to vendors allocation.
5. Then, configure the contracts to contracts to applications allocation.

**Task 4.4.1: Check out the Contract model**

1. On the**Project Explorer**, expand the**Vendor Insights**category, and then click
   on the**Contracts**model.
2. On the**Home**tab, click**Check Out**to begin to make changes.
3. On the**Model**page, select**Payables**from the**Select a metric**
   drop-down list.

**Task 4.4.2: Configure allocations ("PO to Contracts" to
Contracts)**

1. On the**Model**page, click on the line going**TO (Contracts)**from the**(PO to
   Contract)**driver.
2. On the**ALLOCATION TO**dialog box, expand the**Distributing**section and uncheck
   the**Data Relationship**checkbox to remove the OOTB allocation. Click**Yes**from the
   **Legacy Warning**dialog box.
3. On the**ALLOCATION TO**dialog box, expand the**Distributing**section and select
   the**Data Relationship**checkbox to add a new allocation.
4. On the**Source**tab, click**Choose column**and under**PO to Contract Master
   Data**, select**Contract ID**.
5. In the**Destination**tab, click**Choose column**and under**Contracts Master
   Data**, select**Contract Number**.

   ![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa__10.jpg)

**Task 4.4.3: Join tables**

Users of 12.4x and earlier are required to follow this set of instructions to ensure that the
**Contracts**model allocation will work as expected.

1. In the Studio**Project Explorer**, click**Applications Master Data**.
2. On the**Home**tab, click**Check Out**.
3. Add a**Join**step, click**Add Link**, and then select the following (note that
   joining the master data instead of the raw data is a best practice). The**Join**step will be
   the last step:
   - From the**From Table**list, select**Applications Master Data**
   - From the**From Column**list, select**Applications ID**
   - From the**To Table**list, select**Contracts to Applications Master Data**.
   - From the**To Column**list, select**Application ID**
4. Click**OK**.
5. Click the**Table**step to review the table mapping result.
6. Click**Save**.

**Task 4.4.4: Configure contracts to
vendors allocations**

1. In the Studio**Project Explorer**, expand the**Vendors Insights**category, then
   click**Contracts**.
2. Add a**Model**step, then in the**Select a metric list**, select**Payables**
   .
3. Under**Allocations**, click the**(Vendors)**allocation line.
4. On the**ALLOCATION TO**page, expand the**Distributing**section, clear the**Data Relationship**checkbox, then click**Apply**. This removes the previous
   (out-of-the-box) allocation.
5. Re-select the**Data Relationship**checkbox and add the following new allocation:
   - In the**Data Relationship**sub-section, click the box under**Source Column**,
     then in the**Contracts Master Data**column, select**Normalized Vendor Name**.
   - In the Data Relationship sub-section, click the box under**Destination Column**, then in
     the**Vendor Master Data**column, select**Normalized Vendor Name**.
   - Click**OK**to save the configuration.

The distribution after the configuration includes:

- **Source Column**: CONTRACTS MASTER DATA - Normalized Vendor Name
- **Destination Column**: VENDOR MASTER DATA - Normalized Vendor Name

**Task 4.4.5: Configure contracts to
applications allocations**

1. In the Studio**Project Explorer**, expand the**Vendors Insights**category, then
   click**Contracts**.
2. Add a**Model**step, then in the**Select a metric list**, select**Payables**
   .
3. Under**Allocations**, click the**(Contracts to Applications)**allocation line.
4. On the**ALLOCATION TO**page, expand the**Distributing**section, clear the**Data Relationship**checkbox, then click**Apply**. This removes the previous
   (out-of-the-box) allocation.
5. Re-select the**Data Relationship**checkbox and add the following new allocation:
   - In the**Data Relationship**sub-section, click the box under**Source Column**,
     then in the**Contracts Master Data**column, select**Contract ID**.
   - In the**Data Relationship**sub-section, click the box under**Destination Column**
     , then in the**Contracts to Applications Master Data**column, select**Contract ID**.
   - Click**OK**to save the configuration.

The distribution after the configuration includes:

- **Source Column**: CONTRACTS MASTER DATA - Contract ID
- **Destination Column**: CONTRACTS TO APPLICATIONS MASTER DATA - Contract ID

**Task 5: Configure the
Vendor Insights Contracts component**

Learn more at<task3-install-contracts.html>.
