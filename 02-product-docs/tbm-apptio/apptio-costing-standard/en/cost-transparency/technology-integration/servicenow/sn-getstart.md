---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "ServiceNow Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Technology Integrations"
  - "ServiceNow"
source_path: "cost-transparency/technology-integration/servicenow/sn-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# ServiceNow Getting Started

The integration between IBM Apptio and ServiceNow is a bi-directional integration
designed to connect operational and configuration data from ServiceNow with IBM Apptio’s
financial models; and to surface Apptio’s cost and TCO insights back into ServiceNow.

This approach enables organizations to establish ServiceNow as the operational system of
record (CMDB, CSDM, Discovery, EA, DPM) while using IBM Apptio as the financial system of
record for technology cost, TCO, and allocation logic. The result is a unified, trusted view
of cost, consumption, and value across Applications, Services, and Digital Portfolios.

The integration is delivered through two complementary paths:

- **Ingress**: Bringing ServiceNow data into IBM Apptio using prescriptive Datalink
  connectors
- **Egress**: Pushing IBM Apptio TCO insights back into ServiceNow using certified IBM
  Apptio applications from the ServiceNow Store

1. **Readiness Assessment**

   Before kicking off the technical integration, consider
   reaching out to our Professional Services organization to run the Apptio ServiceNow
   Readiness Assessment.

   This assessment will help validate CMDB completeness, CSDM
   alignment, discovery coverage, and data quality before integration.

   Its objective
   is to identify which areas are ready for Integration, which key use cases this will
   support and thereby which business benefits/value can be expected.
2. **Ingress: Bringing ServiceNow Data into Apptio**

   Ingress focuses on sourcing
   high-quality operational, configuration, and relationship data from ServiceNow into IBM
   Apptio to power accurate and consumptive cost modelling.
3. **What Data Is Ingested**

   Using prescriptive IBM Apptio Datalink connectors, IBM Apptio ingests data from key
   ServiceNow data stores, including:
   - CMDB Configuration Items (Infrastructure, Applications, Services)
   - Service (Service Catalog) and Application relationships aligned to CSDM
   - Operational data such as tickets, incidents, and task volumes (where applicable)
   - Organizational and ownership metadata (e.g., Departments, Cost Centers)

   This data forms the structural foundation for Application TCO, Service TCO,
   and chargeback/showback in IBM Apptio.

   Six out-of-the-box Datalink connectors bring
   in data across 33 ServiceNow Tables.

   Note: A 7thcustom connector can be used to bring in any additional tables, as needed.

   Tip: When setting up these Datalink connectors, leverage the Default tick box.
   This will auto-select the most important fields necessary for allocation and reporting
   purposes in IBM Apptio; while still giving flexibility to add or remove fields as
   needed.

   |  |  |  |
   | --- | --- | --- |
   | **Datalink Connector** | **IBM Apptio component** | **Tables in ServiceNow** |
   | ServiceNow Financials | Fixed Assets | alm\_asset |
   | General Reference | cmn\_location |
   | cmn\_costcenter |
   | cmn\_department |
   | Projects | pm\_project |
   | ServiceNow Infra Assets - Lower | Data Center | cmdb\_ci\_datacenter |
   | cmdb\_ci\_computer\_room |
   | cmdb\_ci\_zone |
   | cmdb\_ci\_rack |
   | Network | cmdb\_ci\_netgear |
   | Storage | cmdb\_ci\_storage\_device |
   | cmdb\_ci\_storage\_volume |
   | cmdb\_ci\_msd |
   | cmdb\_ci\_storage\_server |
   | End User Devices | cmdb\_ci\_computer |
   | ServiceNow Infra Assets - Upper | Mainframe | cmdb\_ci\_mainframe |
   | cmdb\_ci\_mainframe\_lpar |
   | Servers | cmdb\_ci\_server |
   | Database | cmdb\_ci\_database |
   |  | cmdb\_ci\_db\_instance |
   | ServiceNow Infra Relationships | Infra Relationships | cmdb\_rel\_ci |
   | svc\_ci\_assoc |
   | ServiceNow Service Desk | Tickets | incident |
   | problem |
   | change\_request |
   | sc\_request |
   | task\_ci |
   | ServiceNow Apps & Services | Middleware | cmdb\_ci\_app\_server |
   | cmdb\_ci\_app |
   | Applications | cmdb\_ci\_business\_app |
   | Services | service\_offering |
   | cmdb\_ci\_service |
   | cmdb\_ci\_business\_capability |
   | **6 Connectors** | **15 Components** | **33 Tables** |

   To get started with configuration of the Datalink Ingress connectors, consult the
   following documentation: [Datalink ServiceNow Ingress connector - IBM
   Documentation](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-datalink-servicenow-ingress-connector "(Opens in a new tab or window)")
4. **Wire data into the IBM Apptio Cost Model**

   Once the data has been ingested using the Datalink Ingress connectors, leverage our
   Professional Services organization to assist with wiring in the new data feeds from
   ServiceNow into the respective IBM Apptio master datasets and model objects. Based upon
   the use cases and data included via the integration, they can assist with
   unwiring/rewiring the model and help validate the up-levelled configuration and reporting.
5. **Egress: Publishing Apptio TCO Insights Back to ServiceNow**

   Egress focuses on exposing IBM Apptio’s trusted financial Costing insights directly
   within ServiceNow, where architects, service owners, and digital leaders already work.

   **Certified Apptio Apps on the ServiceNow Store**

   IBM Apptio provides **two certified applications** available on the ServiceNow
   Store to support egress use cases:
   - **IBM Apptio Application TCO for ServiceNow Enterprise Architecture (EA)**

     Surfaces Application TCO, cost drivers, and trends directly in ServiceNow EA to
     support application rationalization and modernization decisions.
   - **IBM Apptio Service TCO for ServiceNow Digital Portfolio Management (DPM)**

     Embeds Service TCO insights into ServiceNow DPM, enabling Digital Product and
     Service Owners to plan, build, run, and cost their portfolios using a single
     solution.

   **How Egress Works**

   1. **Install the Certified IBM Apptio Apps**

      Install the appropriate IBM Apptio application(s) from the ServiceNow Store based on
      your EA and/or DPM use cases.
   2. **Create TCO Reports in IBM Apptio**

      Build Application and Service TCO reports in IBM Apptio TBM Studio, including the
      required breakdowns and metrics.
   3. **Configure the Datalink Egress Connector**

      Use IBM Apptio Datalink to securely push TCO data from IBM Apptio into ServiceNow.
   4. **Review Insights in Native ServiceNow Dashboards**

      IBM Apptio TCO metrics appear directly within ServiceNow EA and DPM workspaces,
      providing financial context without users needing to leave ServiceNow.To get started with the configuration of Egress, consult the following documentation:
   [Configure a ServiceNow Egress connection (apps and
   services) - IBM Documentation](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-configure-servicenow-egress-connection-apps-services "(Opens in a new tab or window)")

   Note: In addition to the two, prescriptive Egress Use Cases, one can also leverage the
   generic connector to push any IBM Apptio data into ServiceNow. To get started, consult the
   following documentation:[Configure a ServiceNow Egress connection (generic) - IBM
   Documentation](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-configure-servicenow-egress-connection-generic "(Opens in a new tab or window)")
