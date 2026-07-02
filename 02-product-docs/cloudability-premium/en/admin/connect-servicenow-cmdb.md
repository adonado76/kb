---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Connect to ServiceNow CMDB"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
source_path: "admin/connect-servicenow-cmdb.html"
images:
  - "images/cldy-key-secret.png"
  - "images/cloudability-home-page.png"
  - "images/cloudability-list-page.png"
  - "images/cloudability-workspace.png"
  - "images/connection-credentials.png"
  - "images/create-connection.png"
  - "images/create-new-business-dimension.png"
  - "images/new-api-key.png"
  - "images/new-business-dimension.png"
  - "images/new-dimension-statement.png"
  - "images/new-statement-condition.png"
  - "images/new-statement-group.png"
  - "images/new-statement-template.png"
  - "images/publish-servicenow-business-dimension.png"
  - "images/servicenow-cross-scope.png"
  - "images/workflow-studio.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connect to ServiceNow CMDB

## Overview

The ServiceNow CMDB Integration for Cloudability enables seamless synchronization between your
ServiceNow Configuration Management Database (CMDB) and IBM Cloudability. This integration allows
you to create automated business mappings in Cloudability based on configuration items and
organizational data stored in your ServiceNow CMDB, providing enhanced cloud cost allocation and
governance capabilities.

## Key Benefits

- **Automated Business Mapping**: Automatically create and maintain business mappings in
  Cloudability using your existing ServiceNow CMDB data, reducing manual configuration effort and
  improving accuracy.
- **Centralized Data Management**: Leverage your ServiceNow CMDB as the single source of truth
  for organizational structure, applications, and cost centers that drive your cloud cost
  allocation.
- **Real-time Synchronization**: Keep your Cloudability business mappings up-to-date with
  changes in your ServiceNow CMDB through automated synchronization processes.
- **Enhanced Cost Governance**: Improve cloud cost visibility and accountability by aligning
  cloud resources with your organization's structure as defined in ServiceNow

## Prerequisites

Before installing and configuring the ServiceNow CMDB Integration, ensure you meet the following
requirements:

**ServiceNow Requirements**

- ServiceNow instance (Paris release or later recommended)
- Admin or equivalent privileges to install applications from the ServiceNow Store
- CMDB plugin activated in your ServiceNow instance
- Properly configured CMDB with relevant configuration items (applications, business services, cost
  centers, etc.)

**Cloudability Requirements**

- Active IBM Cloudability account with administrative privileges
- API access enabled in your Cloudability instance
- Valid Cloudability API credentials

## Installation

**Step 1: Download from ServiceNow Store**

1. Log into your ServiceNow instance as an administrator
2. Navigate to **System Applications** > **All Available Applications** > **All**
3. Search for "Cloudability" in the ServiceNow Store
4. Click **Install** and follow the installation prompts
5. Wait for the installation to complete and restart any required services

**Step 2: Post-Installation Setup**

1. **Configure the Cloudability access key**
   - Navigate to IntegrationHub > Connections & Credentials > Connection & Credential
     Aliases![](../../../../03-media/cloudability-premium/images/connection-credentials.png)
   - Search for "Cloudability KeyAccess" and open it
   - Click "New" to add a new Credentials
   - When prompted "What type of Credentials would you like to create?" select "API Key
     Credentials"
   - Input "KeyAccess" as the Name and paste the API Key from Cloudability

     ![](../../../../03-media/cloudability-premium/images/new-api-key.png)
2. **Configure the Cloudability Key Secret**
   - In "Connection & Credential Aliases" search for "Cloudability KeySecret" and open it
   - Click "Create New Connection & Credential"

     ![](../../../../03-media/cloudability-premium/images/cldy-key-secret.png)
   - Add "Cloudability Spoke Connection" as the "Connection Name"
   - Add "<Region Specific Frontdoor Domain>/service/apikeylogin" as the "Connection URL". Replace
     "<Region Specific Frontdoor Domain>" with the appropriate Cloudability Frontdoor domain, for
     example "https://frontdoor.apptio.com/service/apikeylogin"
   - Add the API Secret from the Frontdoor user profile page

     ![](../../../../03-media/cloudability-premium/images/create-connection.png)

**Step 3: Testing the configuration**

- Navigate to Workflow Studio

  ![](../../../../03-media/cloudability-premium/images/workflow-studio.png)
- Navigate to the "Actions" section, find "Cloudability Integration - Get Frontdoor Token" and
  open it
- Click "Test" and then "Run Test"
- When the test is finished running click "View the action execution details"
- If the "Status" variable returns "Success" it means that the credentials were configured
  correctly

**Step 4: Cross-scope privileges configuration**

- Provide cross-scope privileges for the Cloudability app to read data from the tables/views
  specified in the Integration properties. These tables/views are used in the Business Dimension
  creation page. Please refer to the ServiceNow [document](https://www.servicenow.com/docs/bundle/xanadu-application-development/page/build/applications/reference/c_CrossScopePrivilegeRecord.html "(Opens in a new tab or window)"). The example below shows the required configuration.
  Read permission is sufficient for the app.

  ![](../../../../03-media/cloudability-premium/images/servicenow-cross-scope.png)

## Navigation

You can access the Cloudability Business Mapping application through a workspace or through the
All menus list.

![](../../../../03-media/cloudability-premium/images/cloudability-workspace.png)

All user functions are available from the workspace, and this is the recommended method for
accessing the application.

Administrator functions are not available in the workspace. They must be accessed through the
"All menus" list.

User needs admin access to perform Administrator functions. But for all other user operations
admin access is not required.

The Home page displays a list of published and pending ServiceNow business dimensions.

![](../../../../03-media/cloudability-premium/images/cloudability-home-page.png)

The List page allows you to see lists of ServiceNow business dimensions grouped by status.
Clicking on a list to display the business dimensions with that status value.

![](../../../../03-media/cloudability-premium/images/cloudability-list-page.png)

## Use cases

**1. Create/Update Business Dimensions**

ServiceNow business dimensions allow you to define and modify Cloudability business dimensions
from within ServiceNow utilizing data from the ServiceNow CMDB. You can create new ServiceNow
business dimensions or update existing draft business dimensions. To create a new ServiceNow
business dimension, click on [+] and select New Business Dimension.

![](../../../../03-media/cloudability-premium/images/new-business-dimension.png)

Complete the fields in the form as described in the table below:

![](../../../../03-media/cloudability-premium/images/create-new-business-dimension.png)

|  |  |
| --- | --- |
| **Field** | **Description** |
| Name | Select a Cloudability Business Dimension. |
| Effective Date | Set the date when this ServiceNow business dimension should update Cloudability.  This field is initially set to the current date. |
| Table | Select a ServiceNow table. The data from the table will be used to build out the business dimension statements. |
| Statement template query | Define a query that will be used to filter the data used to build out the business dimension statements. |

Click the Save button to save your changes.

**2. Create/Update Statement Templates**

Statement templates allow you to define dynamic statements for your Cloudability Business
Dimension. They are dynamic in the sense that field values from ServiceNow table rows can be
substituted in the statement value expression or the matching expression.

You can create new or update existing statement templates from a draft business dimension. Open a
draft business dimension. Click on the “Statement Templates” tab.

To create a new statement template, navigate to "Statement Templates" from a given Business
Dimension context and click the “New” button. To update an existing statement template, click on its
"Number" value.

![](../../../../03-media/cloudability-premium/images/new-statement-template.png)

Complete the fields in the form as described in the table below:

![](../../../../03-media/cloudability-premium/images/new-dimension-statement.png)

|  |  |
| --- | --- |
| **Field** | **Description** |
| Use dynamic value | Check this field if you want to use a Cloudability business dimension, account group, tag, or internal measure as the value for this statement |
| Dynamic value | Select a Cloudability business dimension, account group, tag, or internal measure |
| Value | Enter a text value. The text can include variables from the Columns list. |

**Variables as values**

You can add variable (column) values to the Value field by clicking the Columns button. Select
one or more columns and close the dialog box. The column names are automatically copied to your
clipboard. You can paste the clipboard contents into the Value field.

The variables in the Value field must be in the following format:

${<column name>}

If you use the Columns button to select column names they will be properly formatted when you
paste them into the Value field.

**3. Create/Update Statement Groups**

Each statement template is made up of one or more statement groups which are used to form the
statement match expression. Each group will be logically ANDed together when the match expression is
determined. You can create new or update existing statement groups from a statement template on a
draft business dimension. Open a statement template. Click on the “Statement Groups” tab. To create
a new statement group, click the “New” button. To update an existing statement group, click on its
Number value.

![](../../../../03-media/cloudability-premium/images/new-statement-group.png)

Click "Set Conditions" and configure the match conditions applied for a given Statement
Group.

![](../../../../03-media/cloudability-premium/images/new-statement-condition.png)

|  |  |
| --- | --- |
| **Field** | **Description** |
| Dimension | Select a Cloudability business dimension, account group, tag, or internal measure |
| Operator | Select the operator which will be used to compare the Dimension against the Value |
| Value | Enter a text value. The text can include variables from the Columns list. |

**4. Publish a ServiceNow Business Dimension**

To update a Cloudability business dimension from ServiceNow you must first publish the ServiceNow
business dimension. Only business dimensions with a status of “Draft” can be published.

Open a draft business dimension. Click the Publish button.

![](../../../../03-media/cloudability-premium/images/publish-servicenow-business-dimension.png)

The status of the business dimension will be changed to one of two values:

**Published**

If the effective date on the business dimension is current or in the past the status is changed
to “Published” and Cloudability is updated immediately.

**Pending**

If the effective date on the business dimension is in the future the status is changed to
“Pending”. Cloudability is not updated immediately.

When the effective date becomes current the status will change to “Published”, Cloudability will
be updated, and any previously published version will be retired.
