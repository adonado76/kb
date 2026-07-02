---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Configurations"
breadcrumb: []
source_path: "cost-transparency/technology-integration/configuations.html"
images:
  - "resources/images/ct_images/trb-cnfg-1.jpg"
  - "resources/images/ct_images/trb-cnfg-2.jpg"
  - "resources/images/ct_images/trb-cnfg-3.jpg"
  - "resources/images/ct_images/trb-cnfg-4.jpg"
  - "resources/images/ct_images/trb-cnfg-5.jpg"
  - "resources/images/ct_images/trb-cnfg-6.jpg"
  - "resources/images/ct_images/trb-stp-10.jpg"
  - "resources/images/ct_images/trb-stp-3b.jpg"
  - "resources/images/ct_images/trb-stp-4.jpg"
  - "resources/images/ct_images/trb-stp-6rc.jpg"
  - "resources/images/ct_images/trb-stp3a.jpg"
  - "resources/images/ct_images/trb-stp6.jpg"
  - "resources/images/ct_images/trb-stp6filt.jpg"
  - "resources/images/ct_images/trb-stp7-oi.jpg"
  - "resources/images/ct_images/trb-stp7b.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configurations

As highlighted in the  [Architecture](architecture.html) 
section, the technical integration involves 12 distinct steps. This section outlines each step in
detail. Anything marked in  **Red**  requires user configuration, while
**Orange** indicates an automated step.

![Configuration](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-1.jpg)

**Step 0**  : Prerequisites Setup

Ensure that both  **IBM Apptio Datadrop**  and the  **IBM Apptio
Target Type in IBM Turbonomic**  are configured. These setups are explained in the earlier
sections. Once these are in place, the data files will flow daily into Datadrop. The files are
visible in your Datadrop Viewer within Datalink, as shown in the screenshot below.

![Datadrop Viewer](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-2.jpg)

Next, create a new Datalink Connector using the Datadrop Connector type.

![Datadrop Connector](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-3.jpg)

![Connections](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-4.jpg)

Set the Transform option as follows:

- OVERWRITE for Pending Actions
- APPEND for Executed Actions

Ensure the connector retrieves the time period dynamically from the file name by selecting the
"File Name Month and Year" option.

![Pending Actions](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-5.jpg)

In the Source System section, use the fixed filename pattern provided by IBM Turbonomic:

**Turbonomic\_<cloud/onprem>\_<executed/pending>\_actions\_<target
name>\_MMDDYYYY.json**

- Given a target name of "ApptioA"
- And current date of "12th Oct 2024"
- And On-prem pending actions data
- Then file drop name is:   
  Turbonomic\_onprem\_pending\_actions\_ApptioA\_10122024.json
- Given a target name of "Apptio\_B"
- And current date of "1st Nov 2024"
- And Cloud executed actions data
- Then file drop name is Turbonomic\_cloud\_executed\_actions\_Apptio\_B\_11012024.json

For the destination, set the table names to:

- Turbo On Prem Pending Actions
- Turbo Cloud Pending Actions
- Turbo On Prem Executed Actions
- Turbo Cloud Executed Actions

![On Prem Pending Actions](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-6.jpg)

: Discuss archiving options with your Customer Success Manager or the
DAT Team.

1. After setting up the Datalink connectors, the data feed will automatically flow into TBM Studio tables: Turbo On Prem Pending Actions, Turbo Cloud Pending Actions,
   Turbo On Prem Executed Actions, Turbo Cloud Executed Actions. These tables are pre-created during
   the component installation, and the data payload will follow the same column syntax. On the first
   run, perform a sanity check to ensure the data format and content are correct.
2. The datasets will flow into the Turbo Actions Feed table automatically, combining the Pending
   and Executed Actions for further processing.
3. As data enters the Turbo Actions Feed table, it will link to existing Apptio data models,
   especially for On-Prem data quantification. This step involves:
   1. Appending Infrastructure Master Datasets (e.g., Servers Master Data) into the Infrastructure
      Feed table.

      ![Infrastructure Master Datasets](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp3a.jpg)
   2. Creating new drivers for Hybrid Cost and Hybrid Charge models, linking cost and charge from the
      existing models to the new Infrastructure model object.

      ![Hybrid Cost and Hybrid Charge models](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-3b.jpg)
4. Once the existing Apptio Infrastructure datasets are appended, validate the Out-of-the-Box
   (OOTB) lookup between the Turbo Actions Feed table and the Infrastructure Table. This lookup links
   Entity Name from Turbo with Infra Name from Apptio. This step is highlighted in Red because the OOTB
   lookup may need customization to maximize data connection.

   ![OOTB](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-4.jpg)
5. The T  *urbo Actions Feed*  data will automatically append to the  *Turbo Actions Master* dataset. The  *Feed*  table pre-filters and normalizes the data, while the  *Master* 
   table is where main calculations, such as savings, take place.
6. The  *Hybrid IT Optimization*  component creates a set of editable Workbench tables, which
   are exposed through the reporting interface. Key tables to configure include:
   - **Target & Settings**  : Ensure COIN Targets are set according to internal agreements.

     ![Target & Settings](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp6.jpg)
   - **Filters**  : Exclude any Actions or Entity Types that do not impact potential or realized
     savings.

     ![Filters](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp6filt.jpg)
   - **Rate Card**  : The most important editable table is the Unit Rate Card. Set the
     Addressable Percentage (%) and its detailed breakdowns; otherwise, the system will default to using
     the full Total Cost of Ownership (TCO)-based Unit Cost and Price columns.

     ![Rate Card](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-6rc.jpg)
7. As part of the  *Hybrid IT Optimization*  component, several additional tables are
   automatically created. One of these tables is the "  *Infrastructure Not Found in Optimization* " table, which provides insight into the portion of the complete Apptio-loaded infrastructure
   set that has Turbo optimizations applied. This data is visualized in the Provider View report in two
   areas::
   - **Optimization Impact**  : The extent to which infrastructure is optimized or impacted.

     ![Optimization Impact](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp7-oi.jpg)
   - **Infra without any Actions**  : Infrastructure without pending or executed actions.

     This may occur because the infrastructure is either not within the scope of
     Turbo optimization or it is already fully optimized.

     ![ Infra without any Actions ](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp7b.jpg)
8. The  *Infrastructure Optimization Detailed*  object is allocated to  *Infrastructure
   Optimization*  . The framework includes both a detailed object and a summarized object to
   optimize reporting and drill-down capabilities. Both objects are installed as part of the  *Hybrid
   IT Optimization*  component.
9. To enable reporting from the application (consumer) perspective, infrastructure data must be
   related to the applications. This step allocates model metrics to the Infrastructure Relationships
   object.
10. Append the existing Apptio infrastructure  *Relationship*  data into the new Infrastructure
    Relationships object. This is done for efficiency rather than expanding the previous dataset. ![Relationship](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-10.jpg)

    If the relationship
    to the Infrastructure consumer exists within the same dataset (e.g., Server Master Dataset), it is
    appended to the model at this stage for efficiency, rather than expanding the original
    Infrastructure dataset.
11. The  *Hybrid IT Optimization*  component includes pre-built allocation lines that
    automatically transfer all model metrics from the Infrastructure Relationship model object to the
    Applications object. This enables out-of-the-box (OOTB) Consumer view reporting from the
    Applications perspective.
12. This final step provides a placeholder for customers to extend reporting beyond applications,
    allowing onward allocations to Business Services or Business Units as needed. This supports
    additional reporting on optimization opportunities and savings.
