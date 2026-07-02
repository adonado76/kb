---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Master Report Content"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Master Reports"
source_path: "studio/new-uc/reference/report-studio-reference/master-report-content.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Master Report Content

**Components Suitable for Master Reports**

Master reports can contain all the components available in regular reports. However, certain
components are better suited for masters:

|  |  |  |
| --- | --- | --- |
| **Component** | **Recommended Use** | **Considerations** |
| **Group Boxes** | Layout structure, visual containers | Lose grouping functionality in child reports |
| **Buttons** | Navigation between reports | Wiki text uses child report context |
| **Tabbed Components** | Multi-section layouts | Add all tab content in master; child content overlays all tabs |
| **Notes** | Instructions, disclaimers, static text | Static only; cannot be edited in child |
| **Headers/Footers** | Branding, titles, page numbers | Headers support dynamic text; footers do not |

**Common Master Report Elements**

**Headers and Footers**

Headers can be added to master reports to display on all pages or only on the first page. You can
format header text using HTML format tags and include dynamic text. For example, use
`<%=CurrentDate()%>` to display the current period. Footers can be fully
customized, though unlike headers, footers do not support dynamic text.

**Navigation Elements**

Buttons and links in master reports provide navigation between reports. When you add a button to
a master report that uses Wiki text, and you have not specified a Data URL for the button, the
application will use the current report (the child report) as the context when users interact with
it.

**Branding (Logos and Colors)**

Administrators can define custom color palettes at the environment level to align reports with
organizational branding guidelines. These color palettes can be applied to report collections and
individual reports. Color palettes are defined through **Settings > Custom Color Palette** and
are available to Apptio Admin, Admin, and Partner Admin roles. Each color palette contains 12
colors, with up to 10 custom palettes available.

**Group Boxes as Layout Containers**

Group boxes are particularly useful in master reports for creating visual sections and
boundaries. However, note that group boxes added to a master report lose their component grouping
functionality when the master is applied to a child report. In child reports, group boxes from the
master serve only as visual borders around content areas.

**Parent topic:** [Master Reports](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
