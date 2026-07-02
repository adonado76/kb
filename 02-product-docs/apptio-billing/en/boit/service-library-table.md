---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Add data to the Service Library table"
breadcrumb: []
source_path: "boit/service-library-table.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Add data to the Service Library table

The Service Library table includes information about the services offered by your
organization. You can add data to the table by uploading the data from another source, such as an
Excel spreadsheet. Upload the data to a separate table, and then append the table to the Service
Library table. See [Upload a data file](../studio/data_studio/upload-data-file.html "Applies to: TBM Studio 12.0 and later. TBM Studio accepts data from flat files in comma-, tab-, pipe-, tilde-, colon-, and semi-colon-separated formats. Before you can upload data, you must create a table where the data will be loaded, if it does not already exist.") for more information.

If the original service library data was appended to the All Business Services table, then
append the same raw data file to the Service Library table. Do not append All Business Services
directly into Service Library; instead, append only the raw file. See [Append data](../studio/data_studio/append-data.html "Applies to: TBM Studio 12.0 and later") for more
information .

Required Service Library data

- **Price** - The internal price set for the business service. Used in
  Billing Standard when using Price x Quantity calculations.
- **Pricing Methodology** - The approach used when calculating he Billing Standard showback or chargeback values.
- **Published** - Indicates if a line item should be included in
  chargeback bills. Values: Yes, No.
- **Service Category** - Represents the second level in the Services
  taxonomy (hierarchy). Recommended values: Development, Operations, Security & Compliance,
  Strategy & Planning
- **Service ID** - A unique identifier for the service.
- **Service Name** - The name of the service. This represents the third
  level in the Services taxonomy (hierarchy).
- **Service Offering** - The service option represented by this item. This
  represents the fourth level in the Services taxonomy (hierarchy). Service options offer a choice to
  the business unit consumers within a service. For example, laptop offerings might include:
  Ultraportable Laptop, Workstation Laptop, and Standard Laptop. Email offerings might include: Gold,
  Silver, and Bronze.
- **Service Type** - This represents the first level in the Services
  taxonomy (hierarchy). Recommended values: Business Application Services, Delivery Services,
  Infrastructure Services, End User Services, and Platform Services.
- **Unit of Measure** - The unit used to track and apportion the cost of a
  business service to one or more business units. Business units consume units of a service. For
  example: email boxes, application users, allocated storage, etc.

Recommended Service Library data

- **Description** - A consumer friendly description of the service. If the
  Long Description field is filled in, that description will be used in place of this description.
- **Lifecycle Stage** - The current status of a service. Typical values
  are: In-Service, Out of Service, Sunset, Onboarding
- **Long Description** - A more detailed description of the service. If
  this field is filled in, the text will be used instead of the text in the Description field.

Optional Service Library data

- **Service Manager** - The primary IT person responsible for provisioning
  and operating the business service.
- **Service Owner** - The IT person responsible for the overall delivery
  of the business service. Responsibilities include the strategy, definition, selection, and financial
  performance of the service.

**Recommended Service Hierarchy**

The TBM Council recommended Service Hierarchy can be accessed here: [TBM Taxonomy
v2.0](../atum/tbm-taxonomy-v2-definition/intro-taxonomy.html)
