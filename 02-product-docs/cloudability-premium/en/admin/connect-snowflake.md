---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Connect Snowflake"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
source_path: "admin/connect-snowflake.html"
images:
  - "images/snowflake_1.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connect Snowflake

You can connect your Snowflake account to Cloudability to enable the ingestion of Snowflake
granular cost data for warehouses along with Snowflake warehouse and account level tags.

Note: It takes 4 to 24 hours before your initial cost and usage data appears in Cloudability.

If
you are purchasing Snowflake via a cloud provider marketplace and adding cost and usage data for
Snowflake with this integration, you will see costs displayed twice in Cloudability reporting. As an
example, if you purchased Snowflake via the AWS Marketplace, you would have:

- The high-level line item for AWS.
- The line items with detailed Snowflake costs and  **AWS Marketplace**  listed as  **Seller.**

You will need to set up filters or views to hide your Marketplace costs. Marketplace costs
are excluded from billing.

**Prerequisites**

- Admin access to Cloudability for Vendor Credentials.
- Access to Snowflake Org 1.0 or 2.0 (2.0 recommended) for granular cost data.
- Account Admin permissions in the Snowflake 1.0.
- Global Org Admin permissions for Snowflake 2.0.
- For enabling Snowflake Tags

  - Org 2.0 Billing account with Enterprise Edition or higher
  - SNOWFLAKE.ORGANIZATION\_USAGE.[TAG\_REFERENCES](https://docs.snowflake.com/en/sql-reference/organization-usage/tag_references "(Opens in a new tab or window)") view enabled. This is a premium view and may incur
    additional Snowflake costs. To reduce costs, you can ask Snowflake to disable all premium views
    except for the one we need (unless you need any of these premium views)

Note: You can run the query below in your Snowflake console to check whether tag values are visible:
*SELECT \* FROM SNOWFLAKE.ORGANIZATION\_USAGE.TAG\_REFERENCES;*

If Tag References view is not
enabled , granular warehouse level costs will still be available but without the tags information.

**Steps for integration**

**Snowflake**

Access your Snowflake account using appropriate credentials to view account details.

**Find Organization and Account Name** 

1. Navigate to  **Snowsight**  - the web-based SQL editor for Snowflake.
2. Open the account selector from the bottom left menu bar. This displays a list of accounts
   previously accessed.
3. Identify the account name, and then select the account.
4. Hover over the selected account to view additional details.
5. Copy the  **Organization Name**  and the  **Account Name**  details.

   ![snowflake screenshot](../../../../03-media/cloudability-premium/images/snowflake_1.jpg)

**Cloudability** 

1. Navigate to the Cloudability application, and click on  **Vendor Credentials**  under **Settings**  in the left-hand menu.
2. Provide the following information:
   - **Organization Name**  : Paste the previously copied organization name from Snowflake.
   - **Snowflake Account Name**  : Paste the previously copied account name from Snowflake.
   - **Warehouse Name**  : Provide the name of an existing Snowflake warehouse.
   - **Database Name**  (For Cloudability ): Specify a name for the database to be created by
     Cloudability.
   - **User Name**  (for Cloudability ): Specify a name for the user to be created by Cloudability. A
     role with the same name suffixed with the  **\_role**  will also be created.

**Cloudability - Generate Template**

Once all inputs are provided, click  **Vendor Credentials**  >  **Generate Template** 
.

This will generate the template as a text file containing configuration details based on earlier
input variables.

**Snowflake - Input Template** 

1. Copy the content of the generated text file.
2. Paste the content into the appropriate worksheet or configuration file within the Snowflake
   Account. Ensure that you have the  **Account Admin**  role in Snowflake.
3. Run the provided SQL query and wait till all the statements are executed successfully.

**Cloudability - Verify Credentials.** 

1. Return to Cloudability and navigate to the  **Vendor Credentials**  screen.
2. Click  **Verify Credentials**  to confirm the integration status.

   If
   the check box is Green, you have successfully integrated Snowflake.

   Note: Private links are not
   yet supported for Snowflake.

**Frequently Asked Questions**

**I’m a customer with Snowflake already credentialed but without granular data. Do I need to
make changes to view granular Snowflake costs?**

Existing customers will continue to see service level costs without any required changes.

To enable granular data, you must re-credential the same Snowflake accounts.

- On Snowflake Org 1.0: You will receive granular warehouse costs but no tags.

- To access both granular costs and tags, upgrade to Snowflake Org 2.0 and then re-credential.

**Are there any steps I should be aware of before switching to granular snowflake costs**?

If you are already on **Snowflake**
**Org 2.0**, no additional steps are required beyond **re-credentialing**, as Cloudability
requires additional permissions to ingest granular warehouse-level costs and tags.

**Which Snowflake Tags are supported?**

We support Snowflake warehouse and account level tags in the below format:

- cldy:snowflake:account:<tagkey>
- cldy:snowflake:warehouse:<tagkey>

These would need to be mapped in the Tags and Labels page after the first successful data
ingestion.

**Where can I get the IP for whitelisting?**

Please reach out to IBM support team.

**How much historical data can be refetched?**

Granular cost data begins from the month you credential the integration.

For historical months, a refetch is required. Cloudability supports **12 months** of
historical data refetch (including the current month).

Please contact the IBM Support team to request a refetch.

**Why can’t I view tags in Snowflake org 1.0?**

Tag visibility requires:

- A **Snowflake Org 2.0 Billing Account** with Enterprise Edition or higher
- The SNOWFLAKE.ORGANIZATION\_USAGE.[TAG\_REFERENCES](https://docs.snowflake.com/en/sql-reference/organization-usage/tag_references "(Opens in a new tab or window)") premium view enabled

Without these, tag data cannot be ingested.
