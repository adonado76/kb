---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Configure a ServiceNow Egress connection"
breadcrumb: []
source_path: "data_studio/configure-servicenow-egress.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configure a ServiceNow Egress connection

The egress connectors enable the flow of Total Cost of Ownership (TCO) app data between
Apptio and ServiceNow.

To display application TCO insights in the relevant ServiceNow dashboards, you can use the
ServiceNow certified Apptio integration. The integration brings detailed, transparent, and
defensible cost structures to application and service offerings within ServiceNow. It is compatible
with the Quebec, Paris, and Orlando releases of ServiceNow.

There are two ServiceNow integrations:

- ServiceNow Egress connector enables to push data from Apptio to ServiceNow.
- ServiceNow Ingress connector enables to push data from ServiceNow to Apptio.

  [Datalink
  ServiceNow Ingress connector](../../datalink/c-servicenow-about-connector.htm "(Opens in a new tab or window)")

## To configure a ServiceNow Egress connection

1. On the ServiceNow platform, install the Apps and Services TCO app.

   [Learn more about installing the Apps & Services TCO app](#ConfigureaServiceNowEgressconnection__InstalltheApptioAppsandServicesTCOintegrationontheServiceNowplatform)
2. In TBM Studio, set up the apps TCO reports.

   [Learn more about setting up
   the apps TCO reports](#ConfigureaServiceNowEgressconnection__SetuptheappsservicesTCOreportsinTBMStudio)
3. In Datalink, configure the Datalink egress connector.

   [Learn more
   about configuring the Datalink egress connector](#ConfigureaServiceNowEgressconnection__ToconfigureaServiceNowEgressconnection)

When you configure the ServiceNow Egress connection, you can view the Apptio TCO data in
ServiceNow.

[Learn more about viewing the Apptio TCO data in ServiceNow](#ConfigureaServiceNowEgressconnection__ToconfigureaServiceNowEgressconnection)

## Install the Apptio Apps and Services TCO integration on the ServiceNow platform

Note: Installing the integrating is a prerequisite to running the egress connector.

To use the Apps & Services Total Cost of Ownership integration ServiceNow app, users need to
have the x\_appti\_app\_servic.user role. Administrators with the x\_appti\_app\_servic.admin role can
also view the support UI page, delete any data in staging or custom tables, and run the integration.

1. In ServiceNow, navigate to Plugins.
2. On the Plugins home page, select Find in Store.
3. In the ServiceNow app store, search for Apptio Application and Services IT TCO.
4. Select Install.

Learn more about the app dependencies from the [application documentation in the ServiceNow Store](https://store.servicenow.com/sn_appstore_store.do#!/store/application/88307d7d1b7b6010f78ba8e22a4bcbad/1.0.0?referer=%2Fstore%2Fsearch%3Flistingtype%3Dallintegrations%25253Bancillary_app%25253Bcertified_apps%25253Bcontent%25253Bindustry_solution%25253Boem%25253Butility%25253Btemplate%26q%3Dapptio&sl=sh "(Opens in a new tab or window)").

## Set up the apps & services TCO reports in TBM Studio

You need to create reports in Apptio which are tailored to the destination table in ServiceNow.
ServiceNow allows Application TCO to be represented with different breakdowns. Because Apptio can
only perform two to three object drills, with reporting elements from a maximum of two objects, you
need to create two reports, configured with the columns listed below:

- [Application TCO (including Cost Pool composition)](#ConfigureaServiceNowEgressconnection__Applicat)
- [Application TCO (including IT Resource Tower composition)](#ConfigureaServiceNowEgressconnection__Applicat2)

[Learn more about
creating reports in TBM Studio](../reports/create-a-report.htm "(Opens in a new tab or window)")

## Application TCO report (including Cost Pool composition)

This report is a drill-down from Applications to Cost Source.

Mandatory columns

Note: You need to follow the exact syntax shown.

- Cost Model: hard code to Business Application Costing
- Fiscal period: use the following formula:

  ```
  = "FY"& CurrentDate("YY") &": "&"Q"&
          gettimeoffset("Quarter","Start","Year") +1
  ```
- Breakdown Id: hard code to Business Unit <--> Business Application
- Business Application: Application Name (from Applications)

  Note: Needs to match the name field
  from the `cmdb_ci_business_app` ServiceNow table.
- Bucket: Cost Pool (from Cost Source)
- Sub-bucket: Cost Sub Pool (from Cost Source)
- Business Unit: hard code to `Check Apptio`
- Amount: `= QuarterToDate(Cost)`

## Optional columns

- Approved for ServiceNow Egress: you can use this as a filter on the report to filter out Apps
  you do not want to share with the ServiceNow Community. This needs to be added as a flag to the
  Applications object.

## Application TCO (including IT Resource Tower composition)

This report is a drill-down from Applications to IT Resource Towers.

Mandatory columns

Note: You need to follow the exact syntax shown.

- Cost Model: hard code to Business Application Costing
- Fiscal period: use the following formula:

  ```
  = "FY"& CurrentDate("YY") &": "&"Q"&
          gettimeoffset("Quarter","Start","Year") +1
  ```
- Breakdown Id: hard code to `Business Application <--> IT Shared Service`
- Business Application: Application Name (from Applications)

  Note: Needs to match the name field
  from the `cmdb_ci_business_app` ServiceNow table.
- IT Shared Service: IT Resource Tower Name (from IT Resource Towers)
- Business Unit: hard code to `Check Apptio`
- Amount: `= QuarterToDate(Cost)`

## Optional columns

- Approved for ServiceNow Egress: you can use this as a filter on the report to filter out Apps
  you do not want to share with the ServiceNow Community. This needs to be added as a flag to the
  Applications object.

## Configure the connection

Obtain an OAuth 2.0 token
:   If you are using OAuth 2.0 authentication for your connector, you need to obtain a token from
    ServiceNow before you configure it, as follows:

    1. Register Datalink as a client application with your ServiceNow OAuth 2.0 source.
    2. Make a note of the Client\_ID and Client\_Secret
       values.
    3. Enter a redirect URL. Use the URL which applies to your region:
       - NA: [datalink.apptio.com/apptioconnect/app](http://datalink.apptio.com/apptioconnect/app "(Opens in a new tab or window)")
       - EU: [datalink-eu.apptio.com/apptioconnect/app](http://datalink-eu.apptio.com/apptioconnect/app "(Opens in a new tab or window)")
       - APAC: [datalink-au.apptio.com/apptioconnect/app](http://datalink-au.apptio.com/apptioconnect/app "(Opens in a new tab or window)")

Create the connection
:   1. Open Datalink and select New Connection.
    2. Enter a Connection Name, then select Next.
    3. Select ServiceNow Apps & Services TCO Egress connector, then select Next.
    4. Select the agent.

    You can either choose a cloud-based or on-premise agent for your egress connection. To configure
    an on-premise agent, see [Configure an on-premises Datalink Agent for ServiceNow](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=db52ac1b-a916-40e2-a6cf-6d4fb63d36c4&Step=1&ReturnUrl=%2fcommunities%2fcommunity-home%2flibrarydocuments%2fviewdocument%3fDocumentKey%3ddb52ac1b-a916-40e2-a6cf-6d4fb63d36c4%26Step%3d1%26ReturnUrl%3d%252fcommunities%252fcommunity-home%252flibrarydocuments%252fviewdocument%253fDocumentKey%253ddb52ac1b-a916-40e2-a6cf-6d4fb63d36c4%2526Step%253d1%2526CommunityKey%253dd640115c-5870-485f-947d-fdb02dcbf248%2526ReturnUrl%253d%25252fcommunities%25252fcommunity-home%25252flibrarydocuments%25253fCommunityKey%25253dd640115c-5870-485f-947d-fdb02dcbf248%2526Action%253dnew "(Opens in a new tab or window)").

    Tip: On-premise agents generally experience faster loading times than cloud-based
    agents.

Configure authentication
:   1. Select the authentication type to connect to your ServiceNow instance: Basic or OAuth
       2.0.

       ![](../../resources/images/datalink_images/sn-egress-connector.png)

       Note: You
       can only use OAuth 2.0 authentication with cloud agents.
    2. Enter the ServiceNow base URL (for example, https://{instance}.service-now.com).
    3. Enter your authentication details:
       - If you are using basic authentication, enter the user name and password.
       - If you are using OAuth 2.0 authentication, do the following:
         1. Enter the token information:
            - In **Authorization URL**, enter the URL used for OAuth 2.0 authorization (for example,
              https://{instance}.service-now.com/oauth\_auth.do).
            - In **Token URL**, enter the URL for retrieving and refreshing access tokens (for example,
              https://{instance}.service-now.com/oauth\_token.do).
            - In the **Client ID** and **Client Secret** fields, enter the client ID and client secret
              you obtained from ServiceNow.

              [Learn more about obtaining an OAuth 2.0 token](https://help.apptio.com/en-us/studio/data%20studio/configure-servicenow-egress.htm?state=ec394c57-8eaa-41ed-8ec5-1e9319c4ba68#Obtain "(Opens in a new tab or window)")
         2. If you want to limit the level of access granted to the access token, specify the Scope as READ
            and WRITE or READ access.
         3. Select **Get Access Token**.

         Datalink encrypts the access token and uses it while running the connector.

       Note: When the OAuth 2.0 access token expires, Datalink automatically tries to refresh
       it.

Enter report details
:   1. In Fill in the Report details, select the BIIT host where the Costing Standard report resides.
       If you have just one BIIT instance, Datalink selects it automatically.
    2. Select the Costing Standard reports you want to upload to ServiceNow, from the reports you set
       up in Set up the apps & services TCO reports in TBM Studio.
    3. Enter Costing Standard report URLs for each of the reports, as follows:
       1. Navigate to Costing Standard and open the report.
       2. Right-click on the report and select Show API URI.
       3. Copy the report URL in JSON format from into the Datalink Report URL field for the report.
    4. Select the time period for the reports. You can choose the current or previous month, or a
       custom time period.
    5. Select Next.

Schedule the connection
:   Select your schedule option and fill in the details:

    - Schedule by time
    - Schedule by event, for example, run the connection after a specific connection has
      executed.

Save the connection
:   Select Complete in the bottom right corner to save the connection. Datalink adds the connector
    to the list.

Run the connection
:   To run the connection, select the arrow in the Run column next to the connection in the list.
    After successful execution of the connection, the TCO data from TBM Studio is pushed to your
    ServiceNow instance.

## View the Apptio TCO data in ServiceNow

To get the most out of your TCO data, we recommend you install table
`itfm_allocation_breakdown` in your ServiceNow instance. Installing the table gives
you access to the following dashboards, where you can analyze spend on Apps and Services:

- Application TCO
- Business Application Costing

You can install the table with one of several plugins, for example:

- `com.snc.financial_management`
- `com.snc.financial_management_for_apm`
- `com.snc.financial_management_for_spm`

Note: These plugins are paid plugins. For information about costing and to request help with
installing the plugin, contact your ServiceNow representative. Installing the plugins is not
mandatory for the app and the egress connector to run.

Custom dashboards
:   The egress connector creates the TCO data in Apptio custom table
    `x_appti_app_servic_apptio_tco`. You can use this table to create custom dashboards
    to display TCO insights. Learn more about creating custom dashboards in the [ServiceNow
    documentation](https://docs.servicenow.com/ "(Opens in a new tab or window)")
