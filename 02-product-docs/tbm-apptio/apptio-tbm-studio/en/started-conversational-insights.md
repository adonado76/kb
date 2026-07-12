---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Conversational Insights"
breadcrumb:
  - "Getting Started"
  - "Conversational Insights"
source_path: "SSWRJM/studio/new-uc/getting-started/conversational-insights.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Conversational Insights

Conversational Insights is now available in Public Preview for Costing and Billing. Customers can now opt in to enable the assistant directly within their production environments. The following features are included in this solution:

- Role-based access model : Administrators can assign one of three access levels—Admin, Power User, or End User. Admins can grant users access to query either the entire cost model or only the reports that they can access. End Users can ask questions about data available within the report collections that they are authorized to access. Power Users provide an intermediate level of access, enabling customers to expand data visibility without granting full administrator privileges. This model preserves the report-based data segregation implemented by many customers while providing flexibility in managing data access.
- Reporting-layer context: Users can ask questions about the report that they currently have open or any reports that they are authorized to access. Responses are generated directly from report data and use familiar report terminology, eliminating the need for knowledge of the underlying cost model.
- Session context awareness: The assistant automatically uses the current product, project, date range, and selected environment as context when generating responses. Users can override the default context and specify a different scope when needed.
- Persistent chat history: Users can start new conversations and search, resume, rename, or delete previous conversations from a dedicated chat history panel.
- Silent and verbose response modes: Users can choose between silent mode, which returns only the response, and verbose mode, which includes intermediate steps. An expandable How I got this answer view is available to provide additional traceability and support troubleshooting.
- Entity descriptions and aliases for administrators (AI Configurations in TBM Studio): Administrators can add custom descriptions and aliases for projects, model objects, model metrics, calculated metrics, and reports. This enables the assistant to understand organization-specific terminology, omit deprecated or unused metrics from default discovery, and provide more accurate responses.
- Smart handling of ambiguous questions: When a query is too vague, the assistant prompts users for additional information instead of making assumptions. This approach helps improve response accuracy and reduces unnecessary searches across model objects.
- In-app feedback: You can provide thumbs-up or thumbs-down feedback on responses and optionally include comments. Feedback is routed to the product team to support ongoing improvements.
- Skills (reusable output templates): Skills define how the assistant formats responses for specific types of questions, enabling consistent output for recurring use cases. The Public Preview includes predefined Skills for common costing scenarios, and administrators can create custom markdown-based Skills that specify when a Skill applies and how responses are structured. The assistant automatically selects the most relevant Skill for a query, or users can invoke a Skill by name.
