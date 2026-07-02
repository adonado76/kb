---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Configure Coupa for Apptio"
breadcrumb:
  - "Costing Standard"
  - "Technology Integrations"
  - "Vendor Insights Coupa"
  - "Vendor Insights Coupa Getting Started"
source_path: "cost-transparency/technology-integration/config-coupa.html"
images:
  - "resources/images/vi_images/vi/coupa/coupa1.jpg"
  - "resources/images/vi_images/vi/coupa/coupa2.jpg"
  - "resources/images/vi_images/vi/coupa/coupa3.jpg"
  - "resources/images/vi_images/vi/coupa/coupa4.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configure Coupa for Apptio

This document will provide instructions to configure Coupa to enable integration between Apptio
and Coupa.

The audience for this document is the Coupa administrator, who will be changing
the settings in Coupa.

Technology Business Management (TBM) provides technology leaders with
standards and validated best practices to communicate the cost, quality, and value of IT investments
to their business partners. Apptio is the industry creator and leader of TBM with its own
proprietary Apptio TBM taxonomy (ATUM).

Apptio ’s suite of solutions fuels digital
transformation by translating technology costs across the entire IT portfolio (including on-premises
systems, vendors, projects, and cloud systems) into a holistic, business-centric view. Customers
leverage this view to set future targets, measure business results and drive investment decisions.

By integrating Coupa with Apptio , together, they support process improvements that impact
an organization’s bottom line according to TBM standards.

**Integration overview**

There are different levels of integration that can be achieved. They are the following:

- Pull in existing Coupa data into Apptio without any change
- Configure the Apptio TBM taxonomy (IT tower and cost pool) in Coupa
- Display the Apptio TBM taxonomy to users at the time of submitting a requisition

To bring in the Coupa data into Apptio directly, Apptio ’s Coupa Datalink (Classic) Connector is
used to pull the Coupa data directly into Apptio . Afterward, the data is integrated into Apptio ’s
Costing Stnadard and Vendor Insights products. The Coupa Datalink (Classic) Connector will use OAuth
to authenticate to Coupa and retrieve the Coupa data using Coupa’s Rest API.

Below are the steps to configure Coupa for different levels of integration:

- Retrieve Coupa data into Apptio using the Coupa Datalink (Classic) Connector. This involves
  creating credentials used by the Apptio Coupa Datalink (Classic) Connector to pull the data from
  Coupa.
- Get IT Tower and Cost Pool details from Coupa users to make the data available in Apptio . This
  involves creating custom fields for users to select the IT Tower and Cost Pool details while
  creating Coupa objects (ex: requisitions, invoices, etc.).
- View TBM Taxonomy from Coupa. This involves creating a policy that will be displayed for
  certain types of expenses.

The IT Tower and Cost Pool details can either be configured by adding the details via custom
fields on the Coupa Item objects directly, or by assigning the Tower and Cost pools to the Coupa
commodity tree so that they default from all items generically. Deciding the best approach should be
discussed during the implementation workshop.

**Retrieved Coupa data**

Vendor Insights needs the following list of data from the system:

- Suppliers
- Contracts
- Requisitions
- Purchase Order
- Invoices

**Instructions**

**Task 1: Create credentials**

To configure Apptio ’s Coupa Datalink (Classic) Connector to pull Coupa data into Apptio ,
follow the steps in  [Coupa
Connector Guide](../../datalink-classic/datalink/connectorguides/c-coupa.html)  .

**Task 2: Create IT Tower and Cost Pool custom fields**

In Apptio , in order to know which vendors and costs are associated with which IT tower and cost
pools in the Apptio ’s TBM taxonomy (ATUM), the data is retrieved from Coupa when the user selects
the appropriate value while creating a requisition or an invoice.

The values can be configured so that they default from the item directly, or from the Coupa
commodity generically. A decision will need to be taken from the implementation team on which method
to use:

1. [COMMODITIES] Defaulting from the Commodity Tree will ensure consistency across the whole Coupa
   procurement platform and will ensure that the IT tower and cost pools default from every item in all
   of the users’ requisitions.   
    This will also allow punchout commodities to default from
   the selection from punchout catalogs. However, this may require some thought from the implementation
   team on mapping UNSPSC codes to the Coupa Commodity tree.   
    Please refer to the success
   page:  [Coupa Success Portal](https://success.coupa.com/support/docs/core_apps/procurement/catalogs_and_items/catalogs/unspsc_codes "(Opens in a new tab or window)")  .
2. [ITEMS] Defaulting from each item in Coupa will ensure that each item will be defined with the
   exact IT tower and cost pools. This will require that ALL items will have to be mapped. If an item
   is not mapped, it will have to be manually amended in Coupa before the requisition is complete.

For the user to select the IT tower and cost pool, the following needs to be set up in Coupa:

- The lookup list for IT towers and cost pools
- The lookup values for IT towers and cost pools lookup lists
- The custom fields for IT towers and cost pools in the following Coupa objects:
  - Either, Items if [ITEMS] is to be configured, or Commodities if [COMMODITIES] is to be
    configured
  - Requisitions
  - Purchase Orders
  - Invoices
- The default IT tower and cost pool values for items

**Task 2.1: Create lookups**

Custom fields will look up the values from lookup lists. Therefore, one lookup list is needed
for each custom field and as a result, the following lookup lists are needed:

- Apptio cost pools
- Apptio towers

This list of cost pools and towers has two levels so that the user can select the specific
sub-cost pool and sub-tower for the purchased item.

**Detailed steps**  :

1. Navigate to  **Lookups**  (Setup > Company Setup > Lookups >
   Create).
2. Create Lookup  **Apptio Cost Pools**  (set Level 1 and Level 2).

   | Field | Value |
   | --- | --- |
   | Name | Apptio Cost Pools |
   | Description | Cost sub-pools for IT |
   | Active | Check |
   | Content Groups | Everyone |
   | Level 1 Name | Apptio Cost Pool |
   | Level 2 Name | Apptio Cost Sub-Pool |
3. Create Lookup  **Apptio Tower**  (set Level 1 and Level 2).   
     

   | Field | Value |
   | --- | --- |
   | Name | Apptio Towers |
   | Description | Sub-towers for IT |
   | Active | Check |
   | Content Groups | Everyone |
   | Level 1 Name | Apptio Tower |
   | Level 2 Name | Apptio Sub-Tower |

**Task 2.2: Load Lookup values**

The values for the Apptio Cost Pools and Apptio Towers Lookup lists need to be uploaded into
Coupa. The Apptio Cost Pools list must contain the hierarchy of possible cost pools and cost
sub-pools values. The Apptio Towers list must contain the hierarchy of possible Towers and Sub-Tower
values.

The values that will be uploaded should be the values used in your Apptio instance, which
usually is the ATUM taxonomy. To get a copy of the standard ATUM taxonomy list to upload, reach out
to the Apptio . The individual with access to configure Apptio can then export the list of IT towers
and cost pools from Apptio from the following tables:

| Apptio table name | Description |
| --- | --- |
| Cost Pool Reference List | List of cost pools and cost sub-pools |
| IT Resource Tower Reference List | List of towers and sub-towers |

There may be a different version of the ATUM taxonomy that is being used and therefore it is
important to retrieve the same version that is being employed to configure Apptio .

This exported list needs to be formatted into the Coupa’s lookup value format.

In order to enforce users to provide the Apptio Cost Pools and Apptio Tower values for all newly
purchased items, the custom fields for cost pools and towers will be required fields. This may not
make sense for items that are not related to technology spend, such as markers or chairs. Therefore,
another option, such as Non-Tech Spend, should be added to the lookup value list so that the user
can select this value.

**Detailed steps**  :

1. Navigate to  **Lookup Values**  (Setup > Company Setup > Lookup Values
   > Load from file ).
2. Load  **Apptio Cost Pool**  data using the standard  **Coupa Lookup
   Value**  format (Choose File > Start Upload).

   | Field | Value |
   | --- | --- |
   | Lookup | Apptio Cost Pools |
   | Parent | [Cost Pool parent value] |
   | Name | [Cost Pool or Cost Sub-Pool name] |
3. Load  **Apptio Tower**  data using the standard  **Coupa Lookup
   Value**  format (Choose File > Start Upload).   
     

   | Field | Value |
   | --- | --- |
   | Lookup | Apptio Towers |
   | Parent | [IT Tower parent value] |
   | Name | [IT Tower or IT Sub-Tower name] |

**Task 2.3: Add custom fields**

For users to select the Apptio Cost Pools and Apptio Towers values while submitting a new Coupa
object, custom fields need to be added to the existing Coupa objects.

Add these custom fields to the following Coupa objects if [ITEMS] if to be configured:

| Coupa object | Section | Custom field prompt | Custom field name |
| --- | --- | --- | --- |
| Item | Items | Apptio Cost Sub-Pool | apptio\_cost\_sub\_pool |
| Item | Items | Apptio Sub-Tower | apptio\_sub\_tower |
| Requisition | Items | Apptio Cost Sub-Pool | apptio\_cost\_sub\_pool |
| Requisition | Items | Apptio Sub-Tower | apptio\_sub\_tower |
| Purchase Orders | Lines | Apptio Cost Sub-Pool | apptio\_cost\_sub\_pool |
| Purchase Orders | Lines | Apptio Sub-Tower | apptio\_sub\_tower |
| Invoices | Lines | Apptio Cost Sub-Pool | apptio\_cost\_sub\_pool |
| Invoices | Lines | Apptio Sub-Tower | apptio\_sub\_tower |

Add these custom fields to the following Coupa objects if [COMMODITIES] if to be
configured:

| Coupa object | Section | Custom field prompt | Custom field name |
| --- | --- | --- | --- |
| Commodities | N/A | Apptio Cost Sub-Pool | apptio\_cost\_sub\_pool |
| Commodities | N/A | Apptio Sub-Tower | apptio\_sub\_tower |
| Requisition | Items | Apptio Cost Sub-Pool | apptio\_cost\_sub\_pool |
| Requisition | Items | Apptio Sub-Tower | apptio\_sub\_tower |
| Purchase Orders | Lines | Apptio Cost Sub-Pool | apptio\_cost\_sub\_pool |
| Purchase Orders | Lines | Apptio Sub-Tower | apptio\_sub\_tower |
| Invoices | Lines | Apptio Cost Sub-Pool | apptio\_cost\_sub\_pool |
| Invoices | Lines | Apptio Sub-Tower | apptio\_sub\_tower |

Create a content group specifically called  **APPTIO**  . This content group
should be assigned to Apptio Power Users or IT Commodity Approvers to ensure that these users can
see and edit the Sub-Tower and Cost Sub-Pool values. The intention is that regular end users do not
need to see these fields as they are mapped from the default values either from the [ITEMS] or
[COMMODITIES].

**Detailed steps**  :

1. Navigate to  **Custom Fields**  (Setup > Company Setup > Custom
   Fields).
2. For  **[ITEMS]**  , add custom fields to the  **Item** 
   object in the  **Items**  section.
   1. Add a custom field for  **Apptio Cost Sub-Pool**  .
   2. Add a custom field for  **Apptio Sub-Tower**  .

   | Field | Value - for cost pools | Value - for IT towers |
   | --- | --- | --- |
   | Prompt | Apptio Cost Sub-Pool | Apptio Sub-Tower |
   | Field Name | apptio\_cost\_sub\_pool | apptio\_sub\_tower |
   | Type | Lookup | Lookup |
   | Who can see this custom field? | APPTIO | APPTIO |
   | Lookup | Apptio Cost Pools | Apptio Towers |
   | Active | Check | Check |
   | Editable | Check | Check |
   | Show in Catalog | Check | Check |
   | Required | Check | Check |
3. For  **[COMMODITIES]**  , add custom fields to  **Commodities** object.
   1. Add a custom field for  **Apptio Cost Sub-Pool**  .
   2. Add a custom field for  **Apptio Sub-Tower**  .
   3. | Field | Value - for cost pools | Value - for IT towers |
      | --- | --- | --- |
      | Prompt | Apptio Cost Sub-Pool | Apptio Sub-Tower |
      | Field Name | apptio\_cost\_sub\_pool | apptio\_sub\_tower |
      | Type | Lookup | Lookup |
      | Who can see this custom field? | APPTIO | APPTIO |
      | Lookup | Apptio Cost Pools | Apptio Towers |
      | Active | Check | Check |
      | Editable | Check | Check |
      | Required | Check | Check |
4. Add custom fields to the  **Requisition**  object in the  **Items** section.
   1. Add a custom field for  **Apptio Cost Sub-Pool**  .
   2. Add a custom field for  **Apptio Sub-Tower**  .

      | Field | Value - for cost pools | Value - for IT towers |
      | --- | --- | --- |
      | Prompt | Apptio Cost Sub-Pool | Apptio Sub-Tower |
      | Field Name | apptio\_cost\_sub\_pool | apptio\_sub\_tower |
      | Type | Lookup | Lookup |
      | Who can see this custom field? | APPTIO | APPTIO |
      | Lookup | Apptio Cost Pools | Apptio Towers |
      | Defaults From [ITEMS] | Item: Apptio Cost Sub-Pool | Item: Apptio Sub-Tower |
      | Defaults From [COMMODITIES] | Commodity: Apptio Cost Sub-Pool | Commodity: Apptio Sub-Tower |
      | Active | Check | Check |
      | Editable | Check | Check |
      | Required | Check | Check |

      **NOTE**  : Ensure that the  **Defaults From**  is from the
       **Item: …**  for  **[ITEMS]**  configuration or **Commodities: …**  for the  **[COMMODITIES]**  configuration.
5. Add custom fields to the  **Purchase Orders**  object, in the **Lines**  section.
   1. Add a custom field for  **Apptio Cost Sub-Pool**  .
   2. Add a custom field for  **Apptio Sub-Tower**  .
6. Add custom fields to the  **Invoices**  object in the  **Lines** section.

   | Field | Value - for cost pools | Value - for IT towers |
   | --- | --- | --- |
   | Prompt | Apptio Cost Sub-Pool | Apptio Sub-Tower |
   | Field Name | apptio\_cost\_sub\_pool | apptio\_sub\_tower |
   | Type | Lookup | Lookup |
   | Who can see this custom field? | APPTIO | APPTIO |
   | Lookup | Apptio Cost Pools | Apptio Towers |
   | Defaults From | requisition line: Apptio Cost Sub-Pool | requisition line: Apptio Sub-Tower |
   | Active | Check | Check |
   | Editable | Check | Check |
   | Required | Check | Check |

   1. Add a custom field for  **Apptio Cost Sub-Pool**  .
   2. Add a custom field for  **Apptio Sub-Tower**  .

| Field | Value - for cost pools | Value - for IT towers |
| --- | --- | --- |
| Prompt | Apptio Cost Sub-Pool | Apptio Sub-Tower |
| Field Name | apptio\_cost\_sub\_pool | apptio\_sub\_tower |
| Type | Lookup | Lookup |
| Who can see this custom field? | APPTIO | APPTIO |
| Lookup | Apptio Cost Pools | Apptio Towers |
| Defaults From | order line: Apptio Cost Sub-Pool | order line: Apptio Sub-Tower |
| Active | Check | Check |
| Editable | Check | Check |
| Required | Check | Check |

**Task 2.4: Link items to default Apptio cost pools & towers**

**NOTE**  : This is only required if the [ITEMS] configuration is followed where
each item will require Apptio cost pool & Apptio sub-towers assigning against them.

When a user selects an item to purchase, providing a default value for the Apptio Cost Pool and
Apptio Tower values makes it easier for the user while submitting a requisition or an invoice. Link
items to default Apptio Cost Pool and Apptio Tower values so that the default value will appear
while creating a new requisition like below.

**Detailed steps**  :

1. Navigate to  **Lookup Values**  (Setup > Suppliers > Items > Load
   from file).
2. Update existing items to include Apptio  **Cost Pools**  and Apptio
    **Towers**  values.
   - Apptio Cost Sub-Pool
   - Apptio Sub-Tower

**Task 2.5: Create a custom view in Requisition**

To view all requisitions and their associated Apptio tower and Apptio cost pool, create a
new custom view.

**Detailed steps**  :

1. Navigate to  **Custom Fields**  (Requisitions > Requisitions Lines >
   View > Create View).
2. Create a new view and click  **Save**  .

| Field | Value |
| --- | --- |
| Name | Apptio Tower |
| Visibility | Everyone |
| Editable by All | Check |
| Start with view | All |
| Conditions | Apptio Sub-Tower is not blank |
| Columns | Created By (Header)   Req #   Req Line #   Item   Supplier   Line Total   Status (Header)   Commodity   Apptio Cost Sub-Pool   Apptio Sub-Tower   Actions |

**Task 3: Create a TBM Taxonomy policy**

To allow the user to view the Apptio TBM Taxonomy as a policy while creating a new requisition
that includes technology spend, create a new policy to display Apptio ’s TBM Taxonomy.

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa4.jpg)

**Detailed steps**  :

1. Navigate to  **Policies**  (Setup > Procurement > Buying Policies >
   Create).
2. Create a new policy for  **Apptio TBM Taxonomy**  and save.

**Further design considerations**

As all the custom fields have a content group of APPTIO, the customer during implementation will
need to decide which Power Users or IT Commodity Approvers can see/edit the APPTIO specific
requisitions.

These users should have the content group APPTIO assigned to them.

There should also be an approval step to ensure that these Power User(s) can edit and amend the
requisition in question as part of the Approval step. Go to  **Setup -> Groups** to add a new approver.

Add the APPTIO approvers to this approval group by editing their user profiles.

Create  **Approval**  steps for  **Requisition**  and
 **Invoice**  (if required) to ensure that the Apptio user group approves the
Apptio -related IT spend.

An example  **Approval**  step could look like:

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa1.jpg)![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa2.jpg)

When a requisition is submitted with Apptio -related spend, the Apptio user group will
be added for approval:

![img](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/coupa/coupa3.jpg)

**NOTE**  : These design considerations should be discussed with the customer to
ensure that their approval policies align with the approach. This is a recommendation on how this
process could work.
