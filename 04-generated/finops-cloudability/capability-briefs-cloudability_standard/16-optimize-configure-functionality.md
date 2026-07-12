---
tbm_concept: "Optimize — Configure Optimization Functionality (credenciales requeridas por proveedor para habilitar recomendaciones de compromiso en AWS y Azure)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/optimize-configure-optimization-functionality.md
  - kb/02-product-docs/apptio-cloudability-standard/en/functionality-supplementary-credentialing-help-commitment.md
  - kb/02-product-docs/apptio-cloudability-standard/en/functionality-configuring-commitment-management.md
  - kb/02-product-docs/apptio-cloudability-standard/en/functionality-using-commitment-preferences-configure-actionable-opportunities.md
last_updated: "2026-07-09"
---
# Optimize — Configure Optimization Functionality — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Antes de que cualquier recomendación de compromiso funcione, las credenciales de la cuenta de nube deben tener permisos específicos habilitados — sin esto, el resto de la funcionalidad de Optimize documentada en los capítulos anteriores simplemente no genera datos. Este capítulo es la guía de credenciales técnicas requeridas, específica por proveedor.

## Cómo lo resuelve IBM Cloudability Standard

**Requisito de rol de administrador**, aplicable a toda la configuración de credenciales: ver o habilitar credenciales requiere derechos de administrador de Cloudability — un usuario sin ese rol debe contactar al administrador principal de su organización.

**Credenciales para AWS, con dos permisos específicos documentados:**
- **`ec2:GetReservedInstancesExchangeQuote`** — requerido específicamente para generar recomendaciones de intercambio de Convertible Reserved Instances (CRIs), verificable en Settings → Vendor Credentials con un indicador visual (checkmark verde vs. otro estado). Habilitarlo requiere regenerar y aplicar una plantilla CloudFormation, con un tiempo de propagación documentado explícitamente: **aproximadamente 1 hora** después de aplicar y verificar la plantilla antes de que las recomendaciones aparezcan.
- **`savings plans:DescribeSavingsPlans`** — requerido para ver el inventario de Savings Plans ya adquiridos, verificable en la pestaña "Reservations" del panel de detalle de credenciales.

**Credenciales para Azure, con una restricción de tipo de cuenta más estricta que AWS.** Commitment Recommendations para Azure requiere acceso a la API de Azure Cloud, la cual **limita el acceso a cuentas empresariales (Enterprise Agreement)** — un cliente sin cuenta empresarial o sin acceso al Azure Enterprise Portal no puede usar esta funcionalidad y debe contactar a su representante de cuenta de Azure. Los permisos requeridos (Billing Reports y Advanced Features) solo necesitan habilitarse a nivel de la **cuenta maestra (enrollment)**, no en cada cuenta vinculada (subscription) — aunque el documento recomienda habilitarlos en ambos niveles como mejor práctica.

## Por qué importa en una conversación con el cliente

Verificar el estado real de estos permisos específicos (`ec2:GetReservedInstancesExchangeQuote`, `savings plans:DescribeSavingsPlans`, Billing Reports/Advanced Features en Azure) debería ser un paso obligatorio de discovery técnico antes de prometer cualquier funcionalidad de recomendación de compromisos — sin esto, el cliente puede llegar a la conclusión equivocada de que el producto "no genera recomendaciones", cuando en realidad es un problema de credenciales fácilmente corregible.

La restricción de Azure a cuentas Enterprise Agreement es una limitación de alcance importante a confirmar temprano — un cliente de Azure sin ese tipo de cuenta simplemente no podrá usar Commitment Recommendations para Azure, independientemente de qué tan bien esté configurado el resto de Cloudability.

El tiempo de propagación de aproximadamente 1 hora tras aplicar una plantilla CloudFormation es un detalle operativo pequeño pero valioso para gestionar expectativas durante cualquier sesión de configuración en vivo con el cliente — evita la percepción de que "no funcionó" cuando en realidad solo falta esperar la propagación.

## Documentos fuente

- Configure Optimization Functionality (índice) — `kb/02-product-docs/apptio-cloudability-standard/en/optimize-configure-optimization-functionality.md`
- Supplementary Credentialing Help for Commitment Functionality — `kb/02-product-docs/apptio-cloudability-standard/en/functionality-supplementary-credentialing-help-commitment.md`
- Configuring Commitment Management — `kb/02-product-docs/apptio-cloudability-standard/en/functionality-configuring-commitment-management.md`
- Using Commitment Preferences to Configure for Actionable Opportunities — `kb/02-product-docs/apptio-cloudability-standard/en/functionality-using-commitment-preferences-configure-actionable-opportunities.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
