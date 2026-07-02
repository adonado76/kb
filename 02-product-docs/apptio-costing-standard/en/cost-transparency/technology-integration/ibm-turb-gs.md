---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "IBM Turbonomic Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Technology Integrations"
  - "IBM Turbonomic"
source_path: "cost-transparency/technology-integration/ibm-turb-gs.html"
images:
  - "resources/images/ct_images/trb-arch-1.jpg"
  - "resources/images/ct_images/trb-arch-addr.jpg"
  - "resources/images/ct_images/trb-arch-et.jpg"
  - "resources/images/ct_images/trb-cnfg-1.jpg"
  - "resources/images/ct_images/trb-cnfg-2.jpg"
  - "resources/images/ct_images/trb-cnfg-3.jpg"
  - "resources/images/ct_images/trb-cnfg-4.jpg"
  - "resources/images/ct_images/trb-cnfg-5.jpg"
  - "resources/images/ct_images/trb-cnfg-6.jpg"
  - "resources/images/ct_images/trb-comp-1.jpg"
  - "resources/images/ct_images/trb-framework.jpg"
  - "resources/images/ct_images/trb-model-alloc.jpg"
  - "resources/images/ct_images/trb-prereq-1.jpg"
  - "resources/images/ct_images/trb-prerq.jpg"
  - "resources/images/ct_images/trb-stp-10.jpg"
  - "resources/images/ct_images/trb-stp-3b.jpg"
  - "resources/images/ct_images/trb-stp-4.jpg"
  - "resources/images/ct_images/trb-stp-6rc.jpg"
  - "resources/images/ct_images/trb-stp3a.jpg"
  - "resources/images/ct_images/trb-stp6.jpg"
  - "resources/images/ct_images/trb-stp6filt.jpg"
  - "resources/images/ct_images/trb-stp7-oi.jpg"
  - "resources/images/ct_images/trb-stp7b.jpg"
  - "cost-transparency/technology-integration/clip_image002_69970998.gif"
  - "cost-transparency/technology-integration/clip_image004_1503612513.gif"
  - "cost-transparency/technology-integration/clip_image006_-595341153.gif"
  - "cost-transparency/technology-integration/clip_image008_-537983876.gif"
  - "cost-transparency/technology-integration/clip_image010_-1349679255.gif"
  - "cost-transparency/technology-integration/clip_image012_672310785.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# IBM Turbonomic Getting Started

The integration between IBM Turbonomic and IBM Apptio is currently a one-way
integration where data flows only from IBM Turbonomic into IBM Apptio Costing. The steps below
provide the details on the steps involved to get this integration started.

## Prerequisites

To initiate the integration between IBM Turbonomic and IBM Apptio, the following
prerequisites must be configured:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-prerq.jpg)

**Setup of IBM Apptio Datadrop** 

The integration of IBM Turbonomic data
into IBM Apptio utilizes IBM Apptio’s Datadrop, a cloud-based secure file transfer
protocol (SFTP) server.

For detailed setup instructions, refer to  [Configure a
Datadrop connection](../../datalink/datalink_datadrop.dita "(Opens in a new tab or window)")  .

**Setup in IBM Turbonomic**

Once the IBM Apptio Datadrop is provisioned, proceed with the following steps to
configure IBM Apptio as a target in IBM Turbonomic:

1. Navigate to IBM Turbonomic and select  **Settings**  from the left-hand column.
2. Select  **New Target**  at the top right corner.
3. Choose  *IT Management*  as the  **Target Category**  .
4. From the available  **Target Types**  , select  *IBM Apptio*  . ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-prereq-1.jpg)
5. In the configuration window, enter data in the required fields:
   - **Address**  : Enter the target host name or IP address associated with the
     IBM Apptio account.Example: `datadrop.apptio.com`
   - **Display Name**  : Provide a display name of your choice for this target.
   - **Port**  : Set the port number to 22.
   - **User Name**  : Enter the username associated with this IBM Apptio account.
   - **Turbonomic Host Name**  : Specify the source instance address of IBM
     Turbonomic.
6. Create keys to connect Turbo and Apptio Datadrop
   1. **Create public/private key pair in .PEM format**
      1. Download OpenSSL here: [https://sourceforge.net/projects/openssl-for-windows/](https://sourceforge.net/projects/openssl-for-windows/ "(Opens in a new tab or window)")
      2. Run following commands separately in OpenSSL command line:
         - genrsa -out private-key.pem
         - rsa -in private-key.pem -pubout -out public-key.pem

           ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image002_69970998.gif)
   2. **Configuring Turbonomic keys**
      1. Paste private PEM key text into Turbonomic. *Sample as per
         below:*

         ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image004_1503612513.gif)

         Note: The private key cannot have a passphrase. If a
         tool like Putty is being used to generate the private key than it’s likely
         in the wrong PPK format.
      2. Download PGP public key from settings section of datalink

         ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image006_-595341153.gif)
      3. Paste PGP public key into the GPG key in Turbonomic
   3. **Configuring Datadrop Keys**
      1. Datadrop only accepts OpenSSH formatted keys, so we need to convert from
         private key in earlier step.
      2. Download putty RSA / DSA key generation utility: [https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html "(Opens in a new tab or window)")
      3. Launch key generator and load your private key in .PEM format. This will
         create a Public Key in OpenSSH format. *Sample as per below:*

         ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image008_-537983876.gif)
      4. Copy the public key and paste into Public Key of your turbo user name within
         settings of Datadrop

      Sample of fully populated Apptio Target Type window in Turbonomic:

      ![A screenshot of a white box Description automatically generated](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image010_-1349679255.gif)
      ![A screenshot of a computer Description automatically generated](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image012_672310785.gif)

## Components Install

To enable the integration between IBM Turbonomic and IBM Apptio, three components need to
be installed.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-comp-1.jpg)

Note: Ensure that the Components Version in Project Settings is set to Version 120. After the
components are installed, you can revert the Component Version to the desired or previous
template.

## Hybrid IT Optimization component

The first component to install is the NEW  *Hybrid IT Optimization*  component. This
component introduces a set of new Master Datasets, metrics (both modeled and calculated),
and model allocations. These elements are designed to support an architecture that enables
modeling and reporting on Hybrid IT Infrastructure optimizations.

As this component is intended for existing customers, it may require customization of
certain table lookups, metrics, and allocations to align with the existing Apptio model
within the new Hybrid IT Optimization framework.

For more detailed information about the component, refer to the description provided when
navigating to the component in the system.

## Turbonomic – Actions component

While the first component,  *Hybrid IT Optimization*  , establishes the framework,
the second component, Turbonomic – Actions, installs the necessary Tables and Master
Datasets to enable seamless integration of  *IBM Turbonomic Action*  data—via
Datadrop—into IBM Apptio’s TBM Studio.

Note: The  *Hybrid IT Optimization*  component must be installed first, as the Turbo
Actions Master table relies on lookup dependencies to three editable tables included with
the  *Hybrid IT Optimization*  component.

For more details on the content of this component, refer to the description provided when
navigating to the component.

## Hybrid IT Optimization - Reporting component

The third and final component is the  *Hybrid IT Optimization - Reporting* 
component. This component installs two reports that visualize actionable insights from the
integration. It provides:

- IT Finance and the Technical Service Owner (IT Provider) with a Potential and Realized
  Savings view from a cost perspective.
- Solution/Application Owner (IT Consumer) with a Potential and Realized Savings view
  from a charge perspective.

For more details on the content of this component, refer to the description provided when
navigating to the component.

## Architecture

The following diagram illustrates the data flow from IBM Turbonomic to IBM Apptio's
Datalink. The steps are outlined below:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-arch-1.jpg)

1. **IBM Turbonomic Setup and Data Discovery**  : IBM Turbonomic performs its normal
   setup and discovers data for each target added. A full list of supported targets is
   available  [here](https://www.ibm.com/docs/en/tarm/8.13.0?topic=documentation-target-configuration "(Opens in a new tab or window)")  . Turbonomic discovers resources, monitors utilization,
   and recommends actions. The diagram shows a few sample targets in blue.
2. **IBM Apptio Target Type Configuration**  : Set up the IBM Apptio Target Type in IBM
   Turbonomic as per the prerequisites. This setup pushes data from IBM Turbonomic to IBM
   Apptio's Datadrop. Ensure IBM Apptio’s Datadrop has been configured correctly.
   Instructions for setting up Datadrop/SFTP Server on the Apptio side can be found in the
   [Apptio Help Center](#).
3. **File Loading and Refreshing**  : Files in JSON format are loaded daily into
   Apptio's cloud-based Datadrop/SFTP server. The payload consists of four datasets: Pending
   and Executed Actions for both On-Prem and Cloud environments. Each day, four new files
   will appear in the Datadrop viewer repository. For details on file content, refer to the
   Data Payload section.
4. **Datalink Connectors Setup**  : Create Datalink connectors to pull data from the
   Datadrop repository into TBM Studio:
   - For Pending Actions, set the upload behavior to "OVERWRITE." Each daily file from
     IBM Turbonomic shows the latest Pending Actions, so it should overwrite the previous
     file in TBM Studio.
   - For Executed Actions, set the upload behavior to "APPEND." The file contains
     Executed Actions for the last 24 hours, so append the data to create a Month-To-Date
     view.
   - TBMA can schedule connector runs (Daily, Weekly, or Monthly). To automate the
     process, assign the table destination names directly to the datasets created by the
     IBM Apptio Framework.
5. **Data Integration into TBM Studio** : After running the connectors, the payload will be stored in the following TBM Studio tables:
   - Turbo Cloud Pending Actions
   - Turbo On-Prem Pending Actions
   - Turbo Cloud Executed Actions
   - Turbo On-Prem Executed Actions

## IBM Apptio Framework

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-framework.jpg)

The framework diagram provides an overview of the Hybrid IT Optimization architecture
powered by IBM Turbonomic’s Pending and Executed Actions. It introduces new tables and
master datasets from an IBM Turbonomic perspective (installed via the IBM Turbonomic –
Actions component) and from a broader Hybrid IT Optimization perspective (installed via the
Hybrid IT Optimization component).

This architecture relates new data points to existing data in the IBM Apptio model. There
are 12 configuration steps, with red bubbles indicating user-required configurations and
orange bubbles for automated/pre-configured steps. These steps are detailed in the
Configuration section.

## IBM Apptio Model Allocations

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-model-alloc.jpg)

The IBM Apptio framework provides an overview of new tables and datasets, while the
diagram above focuses on new model metrics and allocations:

**Hybrid Cost/Hybrid Charge**

These are new, parallel metrics that leverage existing cost/charge models, focusing solely
on the infrastructure layer's total cost. The existing metrics are not reused to avoid
double allocations and conflicts.

Users need to create drivers for these models. Once allocations to the new infrastructure
model object are set up, the remaining model will follow the depicted flow.

**Action Count**

New standalone metrics for month-to-date (MTD) and year-to-date (YTD) reporting on Pending
and Executed Action counts.

**Potential Savings/Realized Savings**

These are key metrics in the Hybrid IT Optimization framework.

- Potential Savings are based on Pending Actions.
- Realized Savings are based on Executed Actions. Both metrics are divided into two
  dimensions, Cost and Charge
  - **Cost**  : For Cloud, the $ Savings are sourced directly from IBM Turbonomic.
    For On-Prem, the savings are calculated using the action value change (e.g., 12 vCPU
    reduced to 2 vCPU, yielding a 10 vCPU savings) and the unit cost of the technical
    services. Adjustments are made based on the % Addressable set by the user.
  - **Charge**  : This follows a similar approach, using the price of the
    technical services and adjusting based on the % Addressable set by the user. These
    savings are targeted for the Business-Facing Service or Application Consumer.

**Level of Addressable**

Users must set and edit the % Addressable for both unit cost and price. Setting this
percentage impacts both cost and charge savings calculations. The breakdown of savings is
split into:

- Direct Savings
- Delayed Savings
- Cost Avoidance

Users have full autonomy to define the allocation of % Addressable across these
categories. This can be set via the Workbench Tab on the Infrastructure Optimization –
Provider View report.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-arch-addr.jpg)

Columns in light grey are expected to be appended to the Editable Table, sourced from the
existing Service Catalogue, while the columns in white are to be defined by the user.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-arch-et.jpg)

## Data Payload

As described in the prerequisites, the data flow initiates in IBM Turbonomic. Once the IBM
Apptio Target Type is configured, the data, including Turbo Pending and Turbo Executed
Actions, is transferred to IBM Apptio's Datadrop. From there, Datalink Connectors transmit
the data to IBM Apptio’s TBM Studio for further processing.

The following four files will be loaded

- Turbo On Prem Pending Actions
- Turbo On Prem Executed Actions
- Turbo Cloud Pending Actions
- Turbo Cloud Executed Actions

The files are distinguished by two key dimensions:

- **Action State**  : Either PENDING or EXECUTED.
- **Delivery**  : Either CLOUD or ON-PREM.

The key distinction lies in the data being transmitted. For CLOUD, only aggregated data is
sent, which includes 14 columns, in contrast to the 25 columns sent for On-Prem data. The
primary reasons for this difference in granularity are as follows:

- On-Prem data is quantified using the IBM Apptio model and data, as IBM Turbonomic does
  not provide financial details for On-Prem environments. To perform these calculations, a
  higher level of granularity is required, which is why detailed columns, such as Entity Id
  and Action Id, are included. In contrast, Cloud data already comes with pre-calculated $
  Savings, as determined by IBM Turbonomic, eliminating the need for such granular details.
- IBM Apptio is not designed to store granular Cloud data—that's the purpose of the
  Cloudability product. Similar to how CSP Cloud Bills are ingested without including the
  most detailed information (e.g., Resource Id), this integration also avoids sending
  granular Cloud optimization data.

The sets of 25 columns for On-Prem data and 14 columns for Cloud data were carefully
selected through a collaborative effort between IBM Apptio and IBM Turbonomic. This exercise
focused on identifying the most important columns that would be valuable for both modeling
and reporting in the integration.

## Configuration

As highlighted in the  [Architecture](architecture.html) 
section, the technical integration involves 12 distinct steps. This section outlines each
step in detail. Anything marked in  **Red**  requires user configuration, while
**Orange** indicates an automated step.

![Configuration](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-1.jpg)

**Step 0**  : Prerequisites Setup

Ensure that both  **IBM Apptio Datadrop**  and the  **IBM Apptio Target Type in IBM
Turbonomic**  are configured. These setups are explained in the earlier sections. Once
these are in place, the data files will flow daily into Datadrop. The files are visible in
your Datadrop Viewer within Datalink, as shown in the screenshot below.

![Datadrop Viewer](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-2.jpg)

Next, create a new Datalink Connector using the Datadrop Connector type.

![Datadrop Connector](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-3.jpg)

![Connections](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-4.jpg)

Set the Transform option as follows:

- OVERWRITE for Pending Actions
- APPEND for Executed Actions

Ensure the connector retrieves the time period dynamically from the file name by selecting
the "File Name Month and Year" option.

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

: Discuss archiving options with your Customer Success Manager or
the DAT Team.

1. After setting up the Datalink connectors, the data feed will automatically flow into TBM Studio tables: Turbo On Prem Pending Actions, Turbo Cloud
   Pending Actions, Turbo On Prem Executed Actions, Turbo Cloud Executed Actions. These
   tables are pre-created during the component installation, and the data payload will follow
   the same column syntax. On the first run, perform a sanity check to ensure the data format
   and content are correct.
2. The datasets will flow into the Turbo Actions Feed table automatically, combining the
   Pending and Executed Actions for further processing.
3. As data enters the Turbo Actions Feed table, it will link to existing Apptio data
   models, especially for On-Prem data quantification. This step involves:
   1. Appending Infrastructure Master Datasets (e.g., Servers Master Data) into the
      Infrastructure Feed table.

      ![Infrastructure Master Datasets](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp3a.jpg)
   2. Creating new drivers for Hybrid Cost and Hybrid Charge models, linking cost and
      charge from the existing models to the new Infrastructure model object.

      ![Hybrid Cost and Hybrid Charge models](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-3b.jpg)
4. Once the existing Apptio Infrastructure datasets are appended, validate the
   Out-of-the-Box (OOTB) lookup between the Turbo Actions Feed table and the Infrastructure
   Table. This lookup links Entity Name from Turbo with Infra Name from Apptio. This step is
   highlighted in Red because the OOTB lookup may need customization to maximize data connection.

   ![OOTB](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-4.jpg)
5. The T  *urbo Actions Feed*  data will automatically append to the  *Turbo Actions
   Master*  dataset. The  *Feed*  table pre-filters and normalizes the data, while
   the  *Master*  table is where main calculations, such as savings, take place.
6. The  *Hybrid IT Optimization*  component creates a set of editable Workbench
   tables, which are exposed through the reporting interface. Key tables to configure
   include:
   - **Target & Settings**  : Ensure COIN Targets are set according to internal
     agreements.

     ![Target & Settings](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp6.jpg)
   - **Filters**  : Exclude any Actions or Entity Types that do not impact potential
     or realized savings.

     ![Filters](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp6filt.jpg)
   - **Rate Card**  : The most important editable table is the Unit Rate Card. Set
     the Addressable Percentage (%) and its detailed breakdowns; otherwise, the system will
     default to using the full Total Cost of Ownership (TCO)-based Unit Cost and Price
     columns.

     ![Rate Card](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-6rc.jpg)
7. As part of the  *Hybrid IT Optimization*  component, several additional tables are
   automatically created. One of these tables is the "  *Infrastructure Not Found in
   Optimization*  " table, which provides insight into the portion of the complete
   Apptio-loaded infrastructure set that has Turbo optimizations applied. This data is
   visualized in the Provider View report in two areas::
   - **Optimization Impact**  : The extent to which infrastructure is optimized or
     impacted.

     ![Optimization Impact](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp7-oi.jpg)
   - **Infra without any Actions**  : Infrastructure without pending or executed
     actions.

     This may occur because the infrastructure is either not
     within the scope of Turbo optimization or it is already fully optimized.

     ![ Infra without any Actions ](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp7b.jpg)
8. The  *Infrastructure Optimization Detailed*  object is allocated to *Infrastructure Optimization*  . The framework includes both a detailed object and a
   summarized object to optimize reporting and drill-down capabilities. Both objects are
   installed as part of the  *Hybrid IT Optimization*  component.
9. To enable reporting from the application (consumer) perspective, infrastructure data
   must be related to the applications. This step allocates model metrics to the
   Infrastructure Relationships object.
10. Append the existing Apptio infrastructure  *Relationship*  data into the new
    Infrastructure Relationships object. This is done for efficiency rather than expanding the
    previous dataset. ![Relationship](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-10.jpg)

    If the relationship to the Infrastructure consumer exists within
    the same dataset (e.g., Server Master Dataset), it is appended to the model at this
    stage for efficiency, rather than expanding the original Infrastructure dataset.
11. The  *Hybrid IT Optimization*  component includes pre-built allocation lines that
    automatically transfer all model metrics from the Infrastructure Relationship model object
    to the Applications object. This enables out-of-the-box (OOTB) Consumer view reporting
    from the Applications perspective.
12. This final step provides a placeholder for customers to extend reporting beyond
    applications, allowing onward allocations to Business Services or Business Units as
    needed. This supports additional reporting on optimization opportunities and savings.
