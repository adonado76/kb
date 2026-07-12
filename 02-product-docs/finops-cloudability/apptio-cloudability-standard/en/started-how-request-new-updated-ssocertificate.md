---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "How to Request a New Or Updated SSO/Certificate"
breadcrumb:
  - "Getting started"
  - "How to Request a New Or Updated SSO/Certificate"
source_path: "SSVCLNQ/chatbot/chatbot-sso.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# How to Request a New Or Updated SSO/Certificate

How to Request a New SSO Install

Overview

1. Submit a Support Ticket: Once support has received the required files and Questions below .
1. Testing and Validation Call: Once you have configured your (IdP) side of the federation, notify your Apptio engineer, Apptio will schedule a call to test Single Sign On (SSO).
1. Enablement Call: If necessary, Apptio will conduct a third call to permanently enable SSO.

More information about Apptio's SSO platform

- Partner / EntityID: urn:federation:apptio
- If you configure "audience restriction" in your SSO, set the value to: urn:federation:apptio "https://federation.apptio.com/apptio-pf-metadata.zip" "https://federation.apptio.com/metadata.xml" "https://federation.apptio.com/sso_certificate.txt" "https://pfidentity.apptio.com/sp/acs.saml2"
- SAML Protocol: SAML 2.0
- Allowable SAML Bindings: POST and Redirect (GET)
- Supported SAML Profiles: SP-initiated (default) and IdP-initiated

Required attributes

- mail: Unique identifier (email address of the user). This must at least look like an email address in the format: user@domain
- fullname: An attribute that contains the First and the Last name. Format can be whatever your internal standard is (e.g. ‘First Last’ or ‘Last, First’ or ‘Last First’ ).

- Apptio can only support integrations with customer SSO systems that are fully SAML 2.0 compliant. Ensure that your system meets this specification.
- If you want to use multi-factor-authentication (a.k.a. MFA or 2FA), it must implemented in your own SSO system. Apptio cannot manage MFA for customers.

How to Request an Updated Certificate

If you have enabled SSO and require certificate renewal, the process is straightforward. To initiate the renewal, submit a support request with the following details:

- A copy of the new metadata file
- Expiry date and time of the certificate

Upon receiving the new file, Apptio will schedule the switch and handle any incidents that may arise during the process. For more information, reach out to technical support team.

Apptio Questions

1. Partner Federation Platform: What SSO Platform are you using and does it support SAML 2.0?
1. Does the TBM Team deploying Apptio intend to use Billing Standard or IT Finance variance report email capabilities? If the TBM Team wants to use these emails which include deep links to specific reports, then it is required that SP-initiated workflow be enabled. This does not exclude the ability to also have an IDP-initiated workflow configured and used, but SP-initiated is a necessary condition for successful use of these emails.
1. Role Management
1. Role management is done inside Apptio by default. Hence, new users are not automatically created and would receive an authorization error. Will this meet your role management requirements?
1. Apptio allows roles to be managed by the identity provider, would you like to also send us a role assertion?

Your provider can send us an assertion in the role attribute. Information on supported roles and permissions across different applications is available in the Apptio Help Center, under Access Administration > Manage user permissions and roles .

1. IdP Initiated: Will you need support for IdP-initiated logins?
1. Login Preference It is important to Apptio to provide a secure Technology Business Management experience for our customers. Our customers who use a single-sign on (SSO) identity provider (IdP) can employ one of two options.\\\
1. User is required to enter their SSO credentials to access Apptio products during any of the following scenarios: Accessing Apptio product URL for the very first time (OR) Accessing Apptio product URL after explicitly logging out (OR) Accessing Apptio product URL after the user session was terminated due to inactivity (60 minutes of continuous inactivity in Apptio)

User authentication to your IdP occurs prior to accessing Apptio . This option allows users to access Apptio as long as there is an established session with your IdP. This requires no additional login steps, unless user does not have an existing session with your IdP. This means that if users closes the browser or navigate away, so long as there is a session with the IdP, when they return they will be instantly logged in without additional requests for credentials.

1. Testing Environment: Will you be using a Staging or UAT Federation environment before configuring this federation in production?
1. Signature and Encryption
1. Sign AuthN Requests? YES/ NO By default Apptio does not expect the AuthN request to be signed
1. Encrypt Entire Assertion? YES/NO By default Apptio does not expect the entire SAML assertion to be encrypted

Next Steps

1. Setup your SP connection with the provided metadata file.
1. Please reply-all to this email and include your metadata file, as well as the answers to the Apptio questions.
1. Once your SP connection is setup, we will schedule a time to conduct a test and validation.

The Apptio support team can also investigate specific slowdowns in your environment with the help of HAR files. To learn how to collect a HAR file, visit Apptio Community page.
