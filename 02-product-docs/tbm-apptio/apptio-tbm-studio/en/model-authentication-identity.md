---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Authentication and Identity"
breadcrumb:
  - "Concepts and Architecture"
  - "Security Model"
  - "Authentication and Identity"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/security-model/authentication-identity.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Authentication and Identity

Authentication is the first layer of security. It verifies that a user is who they claim to be before granting any access to TBM Studio.

## Authentication Methods

TBM Studio supports multiple authentication methods, managed through the Enhanced Access Administration (EAA) platform.

Username and Password

The most basic authentication method. Users log in with an email address and password. Domain administrators configure password policies through the Domain Security dialog, including:

- Minimum and maximum password age (a value of -1 means unlimited)
- Password complexity requirements
- Account lockout policies

A value of -1 in the Min password age and Max password age fields means “unlimited.” Leave the Min password age field set to -1 unless your organization requires a minimum age between password changes.

Single Sign-On (SSO)

For organizations that use enterprise identity providers, TBM Studio supports SSO integration. When SSO is enabled, users authenticate through the corporate identity provider rather than entering a separate TBM Studio password. SSO is configured at the user level—setting a user’s password to “SSO” (in any case) triggers the user to authenticate through the SSO provider.

API Key Authentication

For programmatic access (data uploads, downloads, and integrations), TBM Studio supports API key authentication through Enhanced Access Administration. API keys consist of a public key and a secret key. They are the preferred authentication method for API access because they provide better security than username/password pairs and can be scoped to specific permissions.

Best Practice: API Authentication

Use API keys rather than username/password for all automated integrations. API keys can be granted minimal permissions (such as upload-only access) following the principle of least privilege. See Section 5.5 (API Reference) for detailed API key setup.

## User Identity in TBM Studio

- Session tokens: After authentication, the system issues a token (such as the Apptio-opentoken) that is used for subsequent requests without requiring repeated authentication.
- Session timeout: Sessions expire after a period of inactivity, configured at the domain level. When a session expires, the user must re-authenticate.
- Impersonation: Administrators can impersonate another user to verify their permissions and troubleshoot access issues. This is a valuable testing tool for validating security configurations.

Impersonation is a powerful administrative tool. Use it only for testing and troubleshooting purposes. When impersonating a user, you see exactly what that user would see, including their RLS restrictions and report permissions.
