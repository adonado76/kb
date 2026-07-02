---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Account groups"
breadcrumb:
  - "Cloudability Premium"
  - "Setup"
  - "Organize Your Cloud Spend"
source_path: "admin/account-groups-spend.html"
images:
  - "images/am_sort_accounts.jpg"
  - "images/create_and_assign_account_groups_1.jpg"
  - "images/create_and_assign_account_groups_2.jpg"
  - "images/create_and_assign_account_groups_3.jpg"
  - "images/create_and_assign_account_groups_4.jpg"
  - "images/create_and_assign_account_groups_5.jpg"
  - "images/create_and_assign_account_groups_6.jpg"
  - "images/create_and_assign_account_groups_7.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Account groups

Accounts and Account Groups enable you to edit and group accounts that are accessed with
Cloudability. They also function like tags for AWS accounts, Azure Subscriptions and GCP projects.
They allow you to assign a key/value pair where Account Group is the key and Account Group Entry
maps the value. For example, you might create an Account Group of Environment and use Account Group
Entries to assign a value of "Production", "Staging" or "Development" to individual cloud accounts
in Cloudability.

Groups are used to categorize your accounts according to different variables. You can designate
the key values for your groups; you might, for example, have groups called "Region, "Product," and
"Department." This will allow you to categorize individual accounts according to which region,
product, and department they're associated with.

Setting up Account Groups

1. Navigate to  Organize > Account Groups .

   ![account groups setup screenshot](../../../../03-media/cloudability-premium/images/create_and_assign_account_groups_1.jpg)

   When you first navigate to the page, you'll see all of the accounts that you access with
   Cloudability listed by Account, Account Number, and Vendor.
2. Select  Edit Account Groups  to the upper right corner of the page.

   ![account management screenshot](../../../../03-media/cloudability-premium/images/create_and_assign_account_groups_2.jpg)

   This will bring up a pane where you can designate the key values for your groups. You might,
   for example, have groups called Region, Product, and Department. This will allow you to categorize
   individual accounts according to which region, product, and department they're associated with.

   ![create and assign account groups screenshot](../../../../03-media/cloudability-premium/images/create_and_assign_account_groups_3.jpg)

Assign Account Groups 

Select the Pencil icon to the far right of any account to edit the name and assign it to groups.

![assign account groups screenshot](../../../../03-media/cloudability-premium/images/create_and_assign_account_groups_4.jpg)

You can edit these details for multiple accounts at once by selecting them with the check
box, then selecting  Edit Accounts.

![edit accounts screenshot](../../../../03-media/cloudability-premium/images/create_and_assign_account_groups_5.jpg)

You can now map your account manually to account groups in Cloudability.

Filter accounts 

At the top of the  Account Management  page, select  Add
Filter  to filter by account group.

![add filter screenshot](../../../../03-media/cloudability-premium/images/create_and_assign_account_groups_6.jpg)

Search for accounts 

Click **Search Accounts** to search for specific accounts.

![search screenshot](../../../../03-media/cloudability-premium/images/create_and_assign_account_groups_7.jpg)

Sort accounts 

Select the column headers to sort your accounts.

![selcting collumn headers screenshot](../../../../03-media/cloudability-premium/images/am_sort_accounts.jpg)

Adding Credentials 

Select  Categorize accounts  in the page header. This will navigate you
to the **Vendor Credentials** page to edit credentials for your accounts.

**Parent topic:** [Organize Your Cloud Spend](../admin/tag-data.html)
