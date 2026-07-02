---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Configure Datalink REST Connector"
breadcrumb:
  - "Planning"
  - "APIs"
source_path: "it-planning/planning/config-data-rest.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configure Datalink REST Connector

The [Datalink REST Connector](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-datalink-rest-service-connector "(Opens in a new tab or window)") allows you to integrate
Apptio Planning with Apptio Costing—or other external systems—by securely exchanging data
through REST APIs.

1. **Connector Type**

   Select: **REST Service / REST Service 2.0**
2. **Destination**

   Before configuring the API connection, define where the data will be
   stored in Apptio:
   - Go to the **Apptio Destination** tab.
   - Configure:
     - **Destination Name:** e.g., New Destination 1
     - **Application:** select the application (e.g., Apptio Costing)
     - **Domain:** e.g., acme.apptio.com
     - **Project:** select the project (e.g., Cost Transparency)
     - **Category:** set to REST
   - Choose the **Time Period** (Current Month, Previous Month, or Custom Calendar).
3. **HTTP Method**

   It can be **GET** or **POST**, depending on the endpoint you are calling:
   - **GET** – for retrieving data (read-only).
   - **POST** – for exporting data (generating a CSV file).
4. **REST URL**

   In the **REST URL** field, enter: [https://app.apptio.com](https://app.apptio.com/ "(Opens in a new tab or window)")

   Note: Ensure the URL matches your region (e.g., app-eu.apptio.com, app-au.apptio.com).

   In the **Enter Resource Path URL** field, add the endpoint from the
   documentation, for example:

   `planning/api/v1/plans/<planId>/expenses/export`

   **Description:** This endpoint exports expense data for a specific
   plan in CSV format.
5. **Authentication**

   **Type:** Select appropriate according to [Datalink REST Service Connector](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-datalink-rest-service-connector "(Opens in a new tab or window)")

   Enter:
   - **Frontdoor Key** (Public Key)
   - **Frontdoor Secret** (Secret Key)

   Check **Need Refresh Token?** → **Yes** (allows multiple runs without
   re-authentication).
6. **Headers**

   Add a header:

   **Key:** apptio-current-environment

   **Value:**<environment value, e.g., GUID>
7. **Query Parameters**

   Add the required parameter. Refer to the API documentation:

   **Key:** type

   **Value:** e.g. SUMMARY

   Other optional
   parameters (e.g., departmentCode, columnDelimiter) can be added in the same section.
8. **Pagination**

   **Set:** No Pagination (or other based on [Datalink REST Service Connector](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-datalink-rest-service-connector "(Opens in a new tab or window)")).
9. **Save & Test**

   Click **Test API** to verify the configuration.

   Save
   the connection and set up a schedule if you want to automate the export.
