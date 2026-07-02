---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Configure the Coupa DataLink Connector"
breadcrumb:
  - "Costing Standard"
  - "Technology Integrations"
  - "Vendor Insights Coupa"
  - "Vendor Insights Coupa Getting Started"
source_path: "cost-transparency/technology-integration/configure_the_datalink_coupa_connector.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configure the Coupa DataLink Connector

◆ Applies to: Datalink (Classic) 4.8.7 and later

[Overview](#overview "(Opens in a new tab or window)")

[Prerequisites](#prerequisites "(Opens in a new tab or window)")

[Instructions](#instruction_overview "(Opens in a new tab or window)")

- [Task 1: Configure the connector](#task_1:_configure_the_connector "(Opens in a new tab or window)")
- [Task 2: Define the query information](#task_2:_define_the_query_information "(Opens in a new tab or window)")
- [Task 3: Define the properties](#_task_3:_define_the_properties "(Opens in a new tab or window)")
- [Task 4: Configure the Coupa Connector Apptio Destination settings](#task_4:_configure_the_coupa_connector__apptio_destination_settings "(Opens in a new tab or window)")
- [Task 5: Configure connector email notifications](#task_5:_configure_connector__email_notifications "(Opens in a new tab or window)")
- [Task 6: Test the connector](#task_6:_test_the_connector_ "(Opens in a new tab or window)")
- [Task 7: Save the connector configuration](#task_7:_save_the_connector__configuration "(Opens in a new tab or window)")
- [Task 8: Execute or cancel the connector run](#task_8:_execute_or_cancel_the_connector__run "(Opens in a new tab or window)")
- [Task 9: View execution history](#task_9:_view_execution_history "(Opens in a new tab or window)")
- [Task 10: Validate Output in TBM Studio](#task_10:_validate_output_in_tbm_studio "(Opens in a new tab or window)")

[Troubleshoot issues with the connector](#troubleshoot_issues_with_the_connector_ "(Opens in a new tab or window)")

[Appendix](#appendix "(Opens in a new tab or window)")

- [Retrieval mode best practices](#retrieval_mode_best_practices "(Opens in a new tab or window)")
- [Recommendation for retrieval options](#recommendation_for_retrieval_options "(Opens in a new tab or window)")
- [JSON properties and Coupa objects](#json_propteries_and_coupa_objects "(Opens in a new tab or window)")
- [Warning about account segment columns in tables](#warning_about_account_segment_columns_in_tables "(Opens in a new tab or window)")

**Overview**

Use the Datalink (Classic) Coupa Connector to export Coupa data, then import it into your Apptio
instance to generate reports in Apptio Vendor Insights .

**Instructions**

**Task 1: Configure the connector**

1. Open the Datalink (Classic) Agent, then click  New Connector  .
2. Click the
   Coupa
   Connector.
3. Enter a
   Connector Name
   .
     
     
   **Example**
   : Coupa – Initial Data – PO Line
4. Optionally, select
   Add this Connector to a Connector group
   .
     
     
   **Example name**
   : Coupa – Initial Data
     
     
   For information on connector groups, see
   [Group multiple connectors](../../datalink-classic/datalink/group-connectors.html "(Opens in a new tab or window)")
   .

**Task 2: Define the query information**

For information on defining the query and specifically about authentication, see  [Define the query information](../../datalink-classic/datalink/connectorguides/c-coupa.html) .

**Task 3: Define the properties**

1. Select a  Retrieval Mode  .   
    If you select  Initial Data (Data
   starting from)  , provide additional information regarding the  Start Month  and 
   Start Year  .

   **Examples**

   - Retrieval Mode : Initial Data (Data starting from)
   - Start Month: January
   - Start Year: 2019

   **Retrieval mode options**

   Configuration steps differ for each
   retrieval mode:
   - **Initial Data (All data)**  - Retrieve all data up to the connector run date.
     This destination transformation is set to overwrite the previous data.
   - **Initial Data (Data starting from)**  - Retrieve data starting from a set month
     and year up to the connector run date (>= [start month] / 01 / [start year]). This destination
     transformation is set to overwrite the previous data.
   - **Delta Data (Starting from the beginning of last month)**  - Retrieve data from
     the beginning of the previous month up to the connector run date (>=[last month’s month] / 01
     / [last month’s year]). This destination transformation is set to append the new data to the
     previous data.   
       
      See [Appendix: Retrieval mode best practices](#retrieval_mode_best_practices "(Opens in a new tab or window)")  for more information.
2. Select a Coupa object. You can access and import the following types of Coupa API data and
   filter criteria (in addition to the Retrieval Mode  data range) into your Apptio instance:

   | Coupa object | Default status filter |
   | --- | --- |
   | Suppliers | active, inactive |
   | Contracts | published, inactive |
   | Purchase Orders | all statuses |
   | Purchase Order Lines | all statuses |
   | Purchase Order Line Accounts | all statuses |
   | Invoices | approved, voided |
   | Invoice Lines | approved, voided |
   | Invoice Line Accounts | approved, voided |

   Note: Invoice Lines and Invoice Line Accounts are filtered by the status of their parent
   invoice.
3. Select a Status Filter

**Task 4: Configure the Coupa Connector Apptio Destination settings**

Link your connector to your Apptio destination. From within the connector, click  Apptio **Destination** 
 on the left menu to jump to these settings. If the connector is a part of a connector group,
the  Apptio  **Destination** 
 settings for  Apptio Instance  ,  Domain  ,  Project  , and 
Branch  are disabled and instead inherited from the group settings.

| Field | Description | Example |
| --- | --- | --- |
| Apptio  **Version** | Select R12 with Front Door . | R12 with Front Door |
| Apptio  **Instance** | Select from the list of valid Acess Administration applications. | Costing Standard (https://acme.apptio.com) |
| **Domain** | Enter the domain name of the destination Apptio instance. | acme.com |
| Project | Enter the name of the destination project. | Costing Standard |
| **Table** | Enter the name of the destination table.   This is the name of the table only. It's not the URL or path information. If the table does not exist, it will be created. | Coupa Raw – Initial – PO Line |
| **Source System** | Enter **Coupa** as the name of the source system for the data. | Coupa |
| **Time Period** | Select **Specific Time** . | **Specific Time** |
| **Specific Period** | Select the  Specific Month  ,  Calendar Type  , and  Specific Year  .     It's recommended that you use one of the  **Initial Data**  retrieval modes in the  **Define the properties**  section to populate your Apptio instance with historical data. This data is placed in the time period specified by the Specific Time settings. | Unselect |
| Validation | Select this checkbox to validate the uploaded data using the existing dataset. | Select |

If the columns do not match, the uploaded data will be held in a staging area but will not be
added to the dataset. An email is sent to Datalink (Classic) Admin users notifying them that the
upload did not pass validation. In this case, the Admin can go to the TBM Studio  Data  tab
and manually approve the upload. It's a best practice to validate the data before you upload it.

**Advanced Options**

| Field | Description | Example |
| --- | --- | --- |
| Data Encoding | Select the character encoding to use with queries.     This option is available only when the destination Apptio instance is R12. | **Auto-Detect** |
| Category | Enter a category for the table.     This option is available only when the destination Apptio instance is R12. | z\_Coupa Raw |
| Branch | If you are using the branching feature in TBM Studio R12, enter a branch name to upload data into that branch.     For more information, see  [Branch projects](../../studio/admin/bp-branching-projects.htm "(Opens in a new tab or window)")  .  - This feature requires R12.5 or later. If using an earlier version of R12, the setting is   ignored, and the data is loaded into the trunk. - If the branch name is misspelled or no longer exists (for example, the branch is closed, and a   subsequent build completes), an error is reported. |  |
| Transformation | 1. Select a value appropriate for the retrieval mode you selected:  - Initial Data (All data)   - Set to   Overwrite   the previous data. - Initial Data (Data starting from)   - Set to   Overwrite   the previous data. - Delta Data (Starting from the beginning of last month)   - Set to   Append   the new data to the previous data. | **Overwrite** |

  

**Task 5: Configure connector email notifications**

After you configure email notifications for your Datalink (Classic)  Agent  , you can
configure email notifications for each connector. If you have not configured your  SMTP 
settings, see [Configure agent email notifications](../../datalink-classic/datalink/config-datalink-agents.html#agentemail "(Opens in a new tab or window)")  . You can specify that an email notification be sent
when a connector succeeds or fails.

1. Click
   Notify
   or
   Notify & Archive
   in the left menu to jump to the email configuration settings. Otherwise, scroll down to the
   Notify
   or
   Notify & Archive
   section.
2. Select your email preferences.
3. In the
   To
   box, enter one or more email addresses, separated by a comma or semicolon.
4. Enter a subject in the
   Subject
   box.

**Task 6: Test the connector**

Click
Test
in the upper-right corner to test the connector.

If there is an error, it will be flagged and you can then jump directly to that part of the connector's definition. Clicking
Test
saves any changes made to the connector.

**Task 7: Save the connector configuration**

Click
Save
in the upper-right corner to save the connector.

If there is information missing from the configuration, it will be flagged for you.

**Task 8: Execute or cancel the connector run**

- To run the connector, open the Datalink (Classic) Agent, click  Actions  next to the
  connector, then click  Run Now  .
- To cancel a currently running connector, open the Datalink (Classic)  Agent  , click
   Actions  next to the connector, then click  Cancel Run  .

**Task 9: View execution history**

View a report of execution results that lists the sources, destination, target period, execution start and end time, an explanation of the results, and the number of uploaded bytes for each run of the connector.

1. Open the Datalink (Classic)  Agent  , click  Actions  next to the connector,
   then click  View Execution History  .   
     
    **NOTE**  : By default,  Execution History  displays run information for the previous
   three months.
2. (Optional) Change the values in the
   From
   and
   Until
   fields, then click
   Get Execution Records
   to view up to 12 months of history.

**Task 10: Validate Output in TBM Studio**

Ensure that the table with the specified table name was successfully created.

**Troubleshoot issues with the connector**

If the Connector fails during execution, try clearing the
Validation
checkbox. Run the Connector, then recheck the
Validation
checkbox for future execution runs.

**NOTE**  : For Datalink (Classic) 4.8.8 (new-master-12000 build) and later, the `execution ID`  is not present in log files.

**Appendix**

**Retrieval mode best practices**

When first setting up the Coupa integration with Apptio , it's recommended that you use an 
Initial Data  retrieval mode to populate Apptio with your required historical data. The initial
data will populate the time period specified using the  Specific Time  options in the 
Apptio destination  ,  Time Period  setting. To learn more, see [Configure the Apptio destination settings](#task_4:_configure_the_coupa_connector__apptio_destination_settings "(Opens in a new tab or window)")  .

The  Delta Data   option is designed to be the retrieval mode for scheduled Connector
runs. This option serves to retrieve records that have been updated in Coupa, and then append them
to the same table in the same time period. In this case, you can then use the TBM Studio  Remove
Duplicates  feature to help ensure that only the latest version of a given record is used in
Apptio .

**NOTE**
: Coupa recommends using the
Initial Data (Set Start Date)
option for initial data loads to avoid transferring unnecessary data volumes. Although
Initial Data (All Data)
may be appropriate for
Suppliers
and
Contracts
.

Expected values

The following table shows the values expected when pulling data from Coupa:

| Coupa object | Initial pull - data filter | Default status filter | Initial pull- destination time period | Initial pull -   where to put data (transformation) | Delta pull - data filter | Delta pull - destination time period | Delta pull - where to put data (transformation) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Supplier | Initial data (all data) | active, inactive | First period of current year | Overwrite | Delta data (starting from the beginning of last month) | Previous period | Append |
| Contract | Initial data (all data) | published, inactive | First period of current year | Overwrite | Delta data (starting from the beginning of last month) | Previous period | Append |
| PO, PO Line, PO Line Account | Initial data (all data) | all statuses | First period of current year | Overwrite | Delta data (starting from the beginning of last month) | Previous period | Append |
| Invoice, Invoice Line, Invoice Line Account | Initial data (data starting from) | approved, voided | Previous period | Overwrite | Delta data (starting from the beginning of last month) | Previous period | Append |

**Recommendation for retrieval options**

It's recommended that you use one of the  Initial Data  retrieval modes to populate
your Apptio instance with historical data. This data is placed in the time period specified by the
 Specific Time  settings. To learn more, see  [Define the properties](#_task_3:_define_the_properties "(Opens in a new tab or window)")  .

**Example**
: Specific Time

**Example**
: Specific Period: Jan:FY2019

**JSON properties and Coupa objects**

The JSON properties will be pulled relative to the Coupa object being queried. For
Purchase Order Line Account
and
Invoice Line Account
objects, the root object for each record will be account-allocation if the given account is a member of an account allocation. Otherwise, the root object will be account.

**Example**
: The additional field
Some Field Name: some.path
for an
Invoice Line Account
object would pull its value from
`invoice.invoice-lines.account-allocations`
for accounts that are members of an account allocation, and
`invoice.invoice-lines.account`
for accounts that are not members of an account allocation.

**Warning about account segment columns in tables**

In Datalink (Classic) 4.8.15 and later, account segment columns in tables uploaded by the
Datalink (Classic) Coupa Connector for  Purchase Order Line Accounts  and  Invoice
Line Accounts  adhere to the following new naming conventions:

- Account Segment 01-09 remain the same (a 0 precedes numbers 1-9 )
- Account Segment 010 and above no longer require a 0 before the number
    
    
  **Example**
  : Account 010 is now Account 10, and Account 011 is now Account 11

When appending to a table that used the previous naming convention (Account 010 instead of
Account 10), the new, renamed account segments columns are added to the table. Table records that
existed before Datalink (Classic) 4.8.15 continue to store account segment data using the previous
naming convention.
