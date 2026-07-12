---
tbm_concept: "Data Integration — Cloud Providers (conexión segura con AWS, Azure, GCP, Oracle Cloud e IBM Cloud como fuente primaria de datos de costo y consumo)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connecting-aws-customer-integration-guide.md
  - kb/02-product-docs/apptio-cloudability-standard/en/guide-aws-linked-account-credentialing.md
  - kb/02-product-docs/apptio-cloudability-standard/en/guide-aws-credentialing-using-bulk-actions.md
  - kb/02-product-docs/apptio-cloudability-standard/en/guide-aws-tags.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cacig-aws-obtaining-memory-metrics-ec2-instances-windows-linux.md
  - kb/02-product-docs/apptio-cloudability-standard/en/guide-frequently-asked-questions-connecting-aws.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-microsoft-azure.md
  - kb/02-product-docs/apptio-cloudability-standard/en/azure-connecting-ea-cost-management-exports.md
  - kb/02-product-docs/apptio-cloudability-standard/en/azure-connecting-ea-cost-details-api.md
  - kb/02-product-docs/apptio-cloudability-standard/en/azure-connecting-mca-cost-management-exports.md
  - kb/02-product-docs/apptio-cloudability-standard/en/azure-connecting-mca-cost-details-api.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cma-set-up-advanced-credentials-azure-rightsizing-reserved-instance-planning.md
  - kb/02-product-docs/apptio-cloudability-standard/en/azure-set-up-memory-metrics-collection.md
  - kb/02-product-docs/apptio-cloudability-standard/en/azure-tags.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-google-cloud.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloud-gcp-credentialing-using-bulk-actions.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloud-set-up-gcp-monitoring-agent-rightsizing.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloud-gcp-tags-labels.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloud-setting-up-custom-pricing-support-gcp.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloud-setting-up-commitment-portfolio-gcp.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-oracle-cloud.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloud-federating-user-oci-credentialing.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-cloud.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cloud-setup-credentials-using-cloudability-method.md
  - kb/02-product-docs/apptio-cloudability-standard/en/cc-setup-cloud-credentials-using-deployable-architecture-da-app.md
last_updated: "2026-07-09"
---
# Data Integration — Cloud Providers — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Todo lo que Cloudability puede ofrecer — dashboards, insights, optimización, gobernanza, planeación — depende de una sola condición previa: que los datos reales de facturación y consumo de cada proveedor de nube lleguen de forma completa, segura y confiable. Esta categoría documenta el trabajo de credencialización más técnico de todo el producto, con un patrón consistente mantenido a través de cinco proveedores distintos: AWS, Azure, Google Cloud, Oracle Cloud e IBM Cloud.

## Cómo lo resuelve IBM Cloudability Standard

**AWS — el flujo mejor documentado, con dos mecanismos de credencialización.** El flujo estándar requiere acceso a la consola de AWS con privilegios administrativos (creación de S3 y permisos IAM). Además del flujo individual por cuenta enlazada, existe **credencialización por lotes (bulk actions)** para organizaciones con múltiples cuentas AWS, evitando repetir el proceso cuenta por cuenta. Capacidades complementarias documentadas: manejo de etiquetas AWS, y obtención de métricas de memoria en instancias EC2 (Windows y Linux) — un dato que AWS no expone por defecto en sus métricas estándar de CloudWatch, y que requiere configuración adicional para que Rightsizing pueda usarlo.

**Azure — la integración más compleja, con una decisión arquitectónica de dos ejes.** Primer eje: tipo de acuerdo comercial — **EA (Enterprise Agreement)** vs. **MCA (Microsoft Customer Agreement)** — cada uno con su propio flujo de credencialización. Segundo eje: mecanismo de extracción de datos — **Cost Management Exports** (archivos de detalle granular de facturación y uso, requiere recopilar Enrollment/Billing Account ID, Tenant ID, Subscription ID, y detalles de la cuenta de almacenamiento donde Azure deposita los exports) vs. **Cost Details API** (mecanismo alternativo que crea un Service Principal dentro de la cuenta Azure del cliente, vía un script de PowerShell generado por Cloudability y ejecutado en Azure Cloud Shell, que le asigna automáticamente el rol "Enrollment Reader" o "Billing Account Reader" según corresponda). En ambos casos, la verificación final ocurre en Cloudability (Settings → Vendor Credentials → Azure → Re-Verify), con un ícono verde o rojo indicando éxito o error, y una recomendación explícita de reintentar tras 15 minutos si la verificación falla. **Advanced Credentials** habilita capacidades adicionales específicas: Rightsizing y Reserved Instance Planning. La recolección de métricas de memoria en Azure requiere instalar el Azure Monitor Agent (vía PowerShell o CLI, con comandos distintos para Linux y Windows) y configurar una Data Collection Rule — con el detalle técnico preciso de que Cloudability solo considera las métricas *Memory Available Bytes + Memory Committed Bytes* (Windows) o *mem/available + mem/used* (Linux) para el cálculo de utilización de memoria.

**Google Cloud — soporta GCP Standard Billing**, con credencialización por lotes igual que AWS, un agente de monitoreo dedicado para habilitar Rightsizing, manejo de tags/labels, soporte de precios personalizados (custom pricing) y configuración específica del Commitment Portfolio para GCP.

**Oracle Cloud (OCI)** — credencialización vía federación de usuario, un mecanismo distinto a los tres proveedores anteriores.

**IBM Cloud y un método de credencialización genérico** — un método propio de Cloudability para credencializar cuentas, más una alternativa vía **Deployable Architecture (DA) App** — sugiriendo que IBM está estandarizando el modelo de credencialización hacia un mecanismo más moderno de infraestructura-como-código, en paralelo al método clásico.

## Por qué importa en una conversación con el cliente

La decisión EA vs. MCA vs. Cost Details API en Azure es la pregunta de discovery técnico más importante de todo este capítulo — confirmarla temprano evita que el equipo de implementación prepare la guía equivocada, dado que cada combinación requiere datos y pasos completamente distintos.

La obtención de métricas de memoria (tanto en AWS como en Azure) es un prerrequisito técnico poco visible pero crítico para cualquier conversación de Rightsizing — sin esta configuración adicional, las recomendaciones de dimensionamiento de Cloudability quedan limitadas a CPU y red, sin considerar memoria, lo cual puede llevar a recomendaciones de right-sizing incompletas o imprecisas.

La credencialización por lotes (bulk actions) en AWS y GCP es un argumento de eficiencia operativa concreto para cualquier cliente con un número grande de cuentas de nube — vale la pena preguntar cuántas cuentas AWS/GCP tiene el cliente antes de asumir que la credencialización se hará cuenta por cuenta.

## Documentos fuente

- Connecting with AWS - Customer Integration Guide — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connecting-aws-customer-integration-guide.md`
- AWS Linked Account Credentialing — `kb/02-product-docs/apptio-cloudability-standard/en/guide-aws-linked-account-credentialing.md`
- AWS Credentialing Using Bulk Actions — `kb/02-product-docs/apptio-cloudability-standard/en/guide-aws-credentialing-using-bulk-actions.md`
- AWS Tags — `kb/02-product-docs/apptio-cloudability-standard/en/guide-aws-tags.md`
- Obtaining Memory Metrics for EC2 Instances (Windows/Linux) — `kb/02-product-docs/apptio-cloudability-standard/en/cacig-aws-obtaining-memory-metrics-ec2-instances-windows-linux.md`
- FAQ: Connecting AWS — `kb/02-product-docs/apptio-cloudability-standard/en/guide-frequently-asked-questions-connecting-aws.md`
- Connect Microsoft Azure — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-microsoft-azure.md`
- Connecting EA via Cost Management Exports — `kb/02-product-docs/apptio-cloudability-standard/en/azure-connecting-ea-cost-management-exports.md`
- Connecting EA via Cost Details API — `kb/02-product-docs/apptio-cloudability-standard/en/azure-connecting-ea-cost-details-api.md`
- Connecting MCA via Cost Management Exports — `kb/02-product-docs/apptio-cloudability-standard/en/azure-connecting-mca-cost-management-exports.md`
- Connecting MCA via Cost Details API — `kb/02-product-docs/apptio-cloudability-standard/en/azure-connecting-mca-cost-details-api.md`
- Advanced Credentials for Azure Rightsizing/RI Planning — `kb/02-product-docs/apptio-cloudability-standard/en/cma-set-up-advanced-credentials-azure-rightsizing-reserved-instance-planning.md`
- Azure Memory Metrics Collection — `kb/02-product-docs/apptio-cloudability-standard/en/azure-set-up-memory-metrics-collection.md`
- Azure Tags — `kb/02-product-docs/apptio-cloudability-standard/en/azure-tags.md`
- Connect Google Cloud — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-google-cloud.md`
- GCP Credentialing Using Bulk Actions — `kb/02-product-docs/apptio-cloudability-standard/en/cloud-gcp-credentialing-using-bulk-actions.md`
- GCP Monitoring Agent for Rightsizing — `kb/02-product-docs/apptio-cloudability-standard/en/cloud-set-up-gcp-monitoring-agent-rightsizing.md`
- GCP Tags & Labels — `kb/02-product-docs/apptio-cloudability-standard/en/cloud-gcp-tags-labels.md`
- Custom Pricing Support for GCP — `kb/02-product-docs/apptio-cloudability-standard/en/cloud-setting-up-custom-pricing-support-gcp.md`
- Commitment Portfolio Setup for GCP — `kb/02-product-docs/apptio-cloudability-standard/en/cloud-setting-up-commitment-portfolio-gcp.md`
- Connect Oracle Cloud — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-oracle-cloud.md`
- OCI Federating User Credentialing — `kb/02-product-docs/apptio-cloudability-standard/en/cloud-federating-user-oci-credentialing.md`
- Connect (IBM) Cloud — `kb/02-product-docs/apptio-cloudability-standard/en/cloudability-connect-cloud.md`
- Setup Credentials Using Cloudability Method — `kb/02-product-docs/apptio-cloudability-standard/en/cloud-setup-credentials-using-cloudability-method.md`
- Setup Cloud Credentials Using Deployable Architecture (DA) App — `kb/02-product-docs/apptio-cloudability-standard/en/cc-setup-cloud-credentials-using-deployable-architecture-da-app.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
