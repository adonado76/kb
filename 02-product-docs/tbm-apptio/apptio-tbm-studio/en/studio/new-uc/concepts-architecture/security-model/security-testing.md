---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Security Testing and Validation"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Security Best Practices"
source_path: "studio/new-uc/concepts-architecture/security-model/security-testing.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Security Testing and Validation

Validating your security configuration is as important as configuring it in the first place. Use
these techniques to ensure your security works as intended.

**Testing Techniques**

1. **Preview Filter:** In the RLS pipeline step, use the preview filter to enter a user’s email
   and see exactly which rows they would see in a specific table.
2. **User Impersonation:** Administrators can impersonate any user to view reports and tables
   from that user’s perspective. This tests the full stack: roles, report permissions, and RLS
   together.
3. **Role Switching:** If you have multiple roles available, switch between them to verify that
   report visibility and component access change as expected. Remember to refresh your browser after
   switching.
4. **Cross-Report Validation:** After configuring RLS, open every report that uses the secured
   data to verify filtering works correctly—including drill-through targets.

**Common Security Misconfigurations**

|  |  |  |
| --- | --- | --- |
| **Misconfiguration** | **Risk** | **Prevention** |
| RLS applied to summary but not detail tables | Users see filtered summaries but unfiltered data when drilling down | Apply RLS to every table reachable through drill-through navigation |
| Relying on RLS for Admin users | Admin users can bypass RLS through Studio mode | Use Admin role only for users who genuinely need full system access |
| Missing RLS on one model step | Data visible at one tier but not others, creating inconsistent views | Add RLS step to every model step in the pipeline that requires filtering |
| Mapping table not updated after org changes | New employees or transferred employees see wrong data | Establish a process to update mapping tables whenever organizational changes occur |
| Over-permissioned API accounts | Automated processes have broader access than needed | Create dedicated custom roles for API accounts with minimal permissions |

**Parent topic:** [Security Best Practices](../../../../studio/new-uc/concepts-architecture/security-model/security-best-practices.html)
