---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "technology-integration"
title: "Pre-Requisite Configurations"
breadcrumb: []
source_path: "technology-integration/pre-requisite.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Pre-Requisite Configurations

To initiate the integration between IBM Turbonomic and IBM Apptio, the following prerequisites must be configured:

![](../../resources/images/ct_images/trb-prerq.jpg)

## Setup of IBM Apptio Datadrop

The integration of IBM Turbonomic data into IBM Apptio utilizes IBM Apptio’s Datadrop, a
cloud-based secure file transfer protocol (SFTP) server.

For detailed setup instructions, refer to  [Configure a Datadrop connection](../../datalink/datalink_datadrop.dita "(Opens in a new tab or window)") .

## Setup in IBM Turbonomic

Once the IBM Apptio Datadrop is provisioned, proceed with the following steps to configure IBM
Apptio as a target in IBM Turbonomic:

1. Navigate to IBM Turbonomic and select  **Settings**  from the left-hand column.
2. Select  **New Target**  at the top right corner.
3. Choose  *IT Management*  as the  **Target Category**  .
4. From the available  **Target Types**  , select  *IBM Apptio*  . ![](../../resources/images/ct_images/trb-prereq-1.jpg)
5. In the configuration window, enter data in the required fields:
   - **Address**  : Enter the target host name or IP address associated with the IBM Apptio
     account.Example: `datadrop.apptio.com`
   - **Display Name**  : Provide a display name of your choice for this target.
   - **Port**  : Set the port number to 22.
   - **User Name**  : Enter the username associated with this IBM Apptio account.
   - **SSH Private Key**  : Provide the private key used for accessing the IBM Apptio server.
   - **GPG Public Key**  : Enter the public key used for secure access to the IBM Apptio server.
   - **Turbonomic Host Name**  : Specify the source instance address of IBM Turbonomic.
6. ![](../../resources/images/ct_images/trb-prerq-2.jpg)

For more information, refer IBM Turbonomic Documentation  [here](https://www.ibm.com/docs/en/tarm "(Opens in a new tab or window)")  .

**Parent topic:** [Costing Standard](../home.html)
