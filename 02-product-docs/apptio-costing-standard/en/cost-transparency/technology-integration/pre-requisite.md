---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Pre-Requisite Configurations"
breadcrumb: []
source_path: "cost-transparency/technology-integration/pre-requisite.html"
images:
  - "resources/images/ct_images/trb-prereq-1.jpg"
  - "resources/images/ct_images/trb-prerq.jpg"
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
# Pre-Requisite Configurations

To initiate the integration between IBM Turbonomic and IBM Apptio, the following prerequisites must be configured:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-prerq.jpg)

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
4. From the available  **Target Types**  , select  *IBM Apptio*  . ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-prereq-1.jpg)
5. In the configuration window, enter data in the required fields:
   - **Address**  : Enter the target host name or IP address associated with the IBM Apptio
     account.Example: `datadrop.apptio.com`
   - **Display Name**  : Provide a display name of your choice for this target.
   - **Port**  : Set the port number to 22.
   - **User Name**  : Enter the username associated with this IBM Apptio account.
   - **Turbonomic Host Name**  : Specify the source instance address of IBM Turbonomic.
6. Create keys to connect Turbo and Apptio Datadrop
   1. **Create public/private key pair in .PEM format**
      1. Download OpenSSL here: [https://sourceforge.net/projects/openssl-for-windows/](https://sourceforge.net/projects/openssl-for-windows/ "(Opens in a new tab or window)")
      2. Run following commands separately in OpenSSL command line:
         - genrsa -out private-key.pem
         - rsa -in private-key.pem -pubout -out public-key.pem

           ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image002_69970998.gif)
   2. **Configuring Turbonomic keys**
      1. Paste private PEM key text into Turbonomic. *Sample as per below:*

         ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image004_1503612513.gif)

         Note: The private key cannot
         have a passphrase. If a tool like Putty is being used to generate the private key than it’s likely
         in the wrong PPK format.
      2. Download PGP public key from settings section of datalink

         ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image006_-595341153.gif)
      3. Paste PGP public key into the GPG key in Turbonomic
   3. **Configuring Datadrop Keys**
      1. Datadrop only accepts OpenSSH formatted keys, so we need to convert from private key in earlier
         step.
      2. Download putty RSA / DSA key generation utility: [https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html "(Opens in a new tab or window)")
      3. Launch key generator and load your private key in .PEM format. This will create a Public Key in
         OpenSSH format. *Sample as per below:*

         ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image008_-537983876.gif)
      4. Copy the public key and paste into Public Key of your turbo user name within settings of
         Datadrop

      Sample of fully populated Apptio Target Type window in Turbonomic:

      ![A screenshot of a white box Description automatically generated](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image010_-1349679255.gif)
      ![A screenshot of a computer Description automatically generated](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image012_672310785.gif)
