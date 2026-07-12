---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Step 10: Merge all other components"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step10.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Step 10: Merge all other components

Repeat Step 9 to continue merging up to 5 individual upgrade branches (at one time) and
subsequent Trunk (in Development) check-ins in the same order recommended in [Step 6: Upgrade all other components in the Upgrade branch](step6.html):

- Merge 1 (up to 5 merge items)
  - **Project Settings**: Change to the new template version, such as v104.

    Note: This must be the first item in the first merge.

    Verify in Trunk that Project Settings
    changed in Development and Staging.
  - **TBM Review**: Disable the component.

    Verify in Trunk that the TBM Review component is no
    longer installed for Development and Staging.
  - **ATUM v2.0**: Disable the component.

    Verify in Trunk that ATUM v.2.0 component no longer
    installed for Development and Staging.
  - **CTF- Cost Source**: Revert the calculated metrics and upgrade the component.

    Verify in
    Trunk that no upgrade arrow is displayed on the CTF- Cost Source component in Development and
    Staging.
  - **Params**: Change to the Service Costing home page.

    Go to the Costing Standard
    application. You should see the new landing page for the version you selected. (Learn more)

    Note: This step is only necessary if you installed the TBM Review component available in
    v103.
- Merge 2 (up to 5 merge items)
  - **CT- Quality**: Upgrade the component.

    Verify in Trunk that there's no upgrade arrow on
    the CT- Quality component in Development and Staging.
  - **CT- Labor**: Upgrade the component.

    Verify in Trunk that there's no upgrade arrow on the
    CTF- Labor component in Development and Staging.
  - **CTF- IT Towers**: Revert the calculated metrics and upgrade the component.

    Verify in
    Trunk that there's no up arrow on the CTF- IT Towers component in Development and Staging.
  - **CTF- Time Tracking**: Upgrade the component.

    Verify in Trunk that there's no upgrade
    arrow on the CTF- Time Tracking component in Development and Staging.
  - **CTF- Projects**: Upgrade the component.

    Verify in Trunk that there's no upgrade arrow on
    the CTF- Projects component in Development and Staging.
- Merge 3 (up to 5 merge items)
  - **CTF- Cloud Service**: Revert the calculated metrics and upgrade the component.

    Verify in
    Trunk that there's no upgrade arrow on the CTF- Cloud Services component in Development and
    Staging.
  - **CTF- Amazon Web Services**: Upgrade the component.

    Verify in Trunk that there's
    noupgrade arrow on CTF- AWS component in Development and Staging.
  - **CTF- Azure**: Upgrade the component.

    Verify in Trunk that there's no upgrade arrow on
    the CTF- Azure component in Development and Staging.
  - **CT Apps- Applications**: Revert the calculated metrics and upgrade the component.

    Verify
    in Trunk that there's no upgrade arrow on the Applications component in Development and
    Staging.
  - **CT- Business Units**: Revert the calculated metrics and upgrade the component.

    Verify in
    Trunk that there's no upgrade arrow on the CT- Business Units component in Development and
    Staging.

## Related information

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
