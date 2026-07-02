---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Vendor Credentials Email Alerts and Banners"
breadcrumb:
  - "Cloudability Premium"
  - "Administration"
  - "Vendor Credentials"
source_path: "admin/email-alerts.html"
images:
  - "images/CLDYBanner.jpeg"
  - "images/PremiumBanner.jpeg"
  - "images/Rightsizng_vendorcreds_banner.png"
  - "images/SampleVCemail.jpeg"
  - "images/SampleVCemailPremium.png"
  - "images/email_alerts.png"
  - "images/email_alerts1.png"
  - "images/email_alerts2.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Vendor Credentials Email Alerts and Banners

Cloudability supports enabling email alerts on the Vendor Credentials page. These
email alerts will trigger an email with the summary of the account status.

Admins can opt in
to these alerts using the **Email Alerts** button.

![Email Alerts](../../../../03-media/cloudability-premium/images/email_alerts1.png)

Click **Email Alerts**to open Email Alerts window. Set these alerts based on your preferred cadence.

![Email alerts](../../../../03-media/cloudability-premium/images/email_alerts.png)

These email
alerts get triggered based on your time zone preference. To learn more, see [Setting up Time Zone Preferences](../product/manage-profile.html).

You can unsubscribe these alerts using the **Edit
Alert** window.

![Email alerts](../../../../03-media/cloudability-premium/images/email_alerts2.png)

**Sample Email for Cloudability Customers (except Premium)**

![](../../../../03-media/cloudability-premium/images/SampleVCemail.jpeg)

**Sample Email for
Cloudability Premium Customers**

![](../../../../03-media/cloudability-premium/images/SampleVCemailPremium.png)

These email
alerts will display the account status from Cloudability and Turbonomic (for Cloudability Premium
Customers)

Banners on Vendor Credentials

Banners will be
shown on the data sources which are credentialed in Cloudability.

These banners, which act as
quick filters, highlight the number of invalid and incomplete accounts where action is
needed.

**Banners for Cloudability Customers (except Premium)**

![](../../../../03-media/cloudability-premium/images/CLDYBanner.jpeg)

**Banners for Cloudability Premium
Customers**

![](../../../../03-media/cloudability-premium/images/PremiumBanner.jpeg)

Note: To
turn off the banners or the email alerts button for the organization, reach out to the support team.

**Banners for Cloudability Premium - Rightsizing**

![](../../../../03-media/cloudability-premium/images/Rightsizng_vendorcreds_banner.png)

Note: The banner shows the number of CSP accounts that haven’t been re-credentialed yet as well as
those with errors, without which the Turbonomic optimization engine won’t be able to recommend
optimization actions. The call for action is to ensure the specific accounts indicated need to be
re-credentialed and verified to ensure the complete set of optimisation actions are presented in
Cloudability.

Note: In case you face any issues, escalate to your organisation's Cloudability Administrator. If
you are an administrator, please reach out to your IBM CSM/TAM who can assist you in
re-credentialing your accounts to ensure Cloudability has necessary permissions.

**Parent topic:** [Vendor Credentials](../admin/vendor-credentials.html)
