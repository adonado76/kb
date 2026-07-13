---
concept: "Governance (aplicación proactiva de políticas FinOps directamente en el flujo de trabajo de desarrollo, vía integración con GitHub/Terraform)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/governance-getting-started.md
  - kb/02-product-docs/apptio-cloudability-standard/en/governance-setup-cloudability.md
  - kb/02-product-docs/apptio-cloudability-standard/en/github-com-cloud-app-installation.md
  - kb/02-product-docs/apptio-cloudability-standard/en/github-enterprise-server-on-prem-app-installation.md
  - kb/02-product-docs/apptio-cloudability-standard/en/hcp-terraformterraform-enterprise.md
  - kb/02-product-docs/apptio-cloudability-standard/en/configure-github-actions-terraform-community.md
  - kb/02-product-docs/apptio-cloudability-standard/en/deployment-configurations.md
  - kb/02-product-docs/apptio-cloudability-standard/en/preferences-configuration.md
  - kb/02-product-docs/apptio-cloudability-standard/en/create-manage-policies.md
  - kb/02-product-docs/apptio-cloudability-standard/en/pull-requests-approval-workflow.md
  - kb/02-product-docs/apptio-cloudability-standard/en/resource-recommendations.md
  - kb/02-product-docs/apptio-cloudability-standard/en/usage-configuration-based-cost-estimation.md
  - kb/02-product-docs/apptio-cloudability-standard/en/governance-troubleshooting.md
last_updated: "2026-07-09"
---
# Governance — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Todo lo documentado hasta ahora en Optimize es **reactivo**: analiza gasto ya generado y recomienda ajustes. Governance es fundamentalmente distinto — es **preventivo**: aplica políticas FinOps directamente en el flujo de trabajo de desarrollo, antes de que la infraestructura se despliegue, interceptando pull requests de Terraform que violen reglas de costo o etiquetado.

## Cómo lo resuelve IBM Cloudability Standard

**Cuatro permisos específicos de Governance, cada uno mapeado a un rol distinto:**
- **GovernanceFeatureViewOnly** — ver todas las páginas de Governance (incluido en el rol "Cloudability User").
- **GovernanceFeatureConfigurationFullAccess** — configuración completa (incluido en "Cloudability Admin" y "Cloudability Governance Automation User").
- **GovernanceFeaturePolicyFullAccess** — configuración de políticas (incluido en "Cloudability Governance Policy Admin").
- Un cuarto rol para aprobación de PR ("Cloudability Governance PR Approver"), que puede desbloquear un PR bloqueado por incumplir el nivel de enforcement "Gated".

**Arquitectura de integración, con caminos distintos según la plataforma Terraform del cliente.** Todos los caminos requieren instalar la **IBM Cloudability GitHub App** primero (con permisos de administrador de la organización o repositorio de GitHub), soportando tanto GitHub.com (cloud) como GitHub Enterprise Server (on-prem). A partir de ahí, dos rutas de configuración:
- **HCP Terraform / Terraform Enterprise** — no requiere GitHub Actions; en su lugar, se configura un **Run Task** dentro del workspace de Terraform, usando una clave HMAC y URL de endpoint provistas por Cloudability. El Run Task evalúa los planes de Terraform y da retroalimentación en tiempo real (riesgos de costo, tags faltantes, recursos no conformes) **antes del despliegue**.
- **Terraform Community** — requiere configurar variables/secretos a nivel de organización en GitHub (API keys de Frontdoor, URL de Frontdoor, ID de ambiente, URL del API de Cloudability), e invocar la GitHub Action de Cloudability Governance dentro de flujos de trabajo CI/CD propios.

**Create and Manage Policies — el motor de reglas.** Al menos un tipo documentado explícitamente: **Tagging Policies** (exigir tags requeridos, ej. "Environment: Production"), con la estructura sugiriendo que existen tipos adicionales de política más allá del etiquetado.

**Pull Requests — Approval Workflow.** Requiere que el propietario del repositorio de GitHub configure una regla de protección de rama que exija que los checks de Governance pasen antes de fusionar — un PR que no cumple el nivel de enforcement "Gated" queda bloqueado, desbloqueable solo por alguien con el rol PR Approver.

**Resource Recommendations — sugerencias de configuración más económica en el momento del PR.** Cuando Governance detecta que un recurso nuevo (EC2, RDS) tiene una alternativa de configuración equivalente (mismo CPU/memoria) a menor costo, publica la recomendación como comentario directo en el pull request — ej. "Upgrade RDS instance from db.m5.8xlarge to db.m6g.8xlarge to save costs while maintaining performance." Si no hay una alternativa más económica, simplemente no se publica ninguna recomendación.

**Usage and Configuration-Based Cost Estimation — estimación de costo directamente desde la configuración de Terraform**, con la opción de refinar la estimación aportando parámetros de uso esperado para servicios que lo requieren (AWS Lambda, SQS, entre otros) — si no se proveen valores personalizados, se usa un valor de uso por defecto.

## Por qué importa en una conversación con el cliente

Governance es el argumento de venta más fuerte para clientes con cultura de ingeniería de plataforma madura (DevOps/GitOps) — mientras el resto de Cloudability responde "¿cuánto gastamos y dónde podemos ahorrar retrospectivamente?", Governance responde "¿cómo evitamos que el gasto ineficiente se despliegue en primer lugar?" — un cambio de postura de FinOps reactivo a FinOps preventivo (shift-left).

La arquitectura de integración dual (Run Task para HCP/TFE, GitHub Actions para Terraform Community) es la pregunta de discovery técnico correcta antes de cualquier propuesta de implementación de Governance — confirmar qué plataforma Terraform usa el cliente determina completamente el camino de configuración.

Resource Recommendations directamente en el PR es un argumento de adopción de desarrollador poderoso: en vez de que un ingeniero descubra semanas después (vía un reporte de costo) que eligió una instancia subóptima, recibe la sugerencia en el mismo momento en que está revisando su código — el tipo de retroalimentación inmediata que genera adopción orgánica de buenas prácticas FinOps sin fricción organizacional.

## Documentos fuente

- Governance - Getting Started — `kb/02-product-docs/apptio-cloudability-standard/en/governance-getting-started.md`
- Setup Cloudability Governance — `kb/02-product-docs/apptio-cloudability-standard/en/governance-setup-cloudability.md`
- GitHub.com (Cloud) App Installation — `kb/02-product-docs/apptio-cloudability-standard/en/github-com-cloud-app-installation.md`
- GitHub Enterprise Server (on-prem) App Installation — `kb/02-product-docs/apptio-cloudability-standard/en/github-enterprise-server-on-prem-app-installation.md`
- HCP Terraform/Terraform Enterprise — `kb/02-product-docs/apptio-cloudability-standard/en/hcp-terraformterraform-enterprise.md`
- Configure GitHub Actions for Terraform Community — `kb/02-product-docs/apptio-cloudability-standard/en/configure-github-actions-terraform-community.md`
- Deployment Configurations — `kb/02-product-docs/apptio-cloudability-standard/en/deployment-configurations.md`
- Preferences Configuration — `kb/02-product-docs/apptio-cloudability-standard/en/preferences-configuration.md`
- Create and Manage Policies — `kb/02-product-docs/apptio-cloudability-standard/en/create-manage-policies.md`
- Pull Requests - Approval Workflow — `kb/02-product-docs/apptio-cloudability-standard/en/pull-requests-approval-workflow.md`
- Resource Recommendations — `kb/02-product-docs/apptio-cloudability-standard/en/resource-recommendations.md`
- Usage and Configuration-Based Cost Estimation — `kb/02-product-docs/apptio-cloudability-standard/en/usage-configuration-based-cost-estimation.md`
- Troubleshooting — `kb/02-product-docs/apptio-cloudability-standard/en/governance-troubleshooting.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
