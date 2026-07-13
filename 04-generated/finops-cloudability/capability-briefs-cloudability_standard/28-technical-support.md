---
concept: "Technical Support (canal de soporte, performance/outages, descuentos personalizados y EDP, y solicitudes de refetch/reprocess de datos)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/support-technical.md
  - kb/02-product-docs/apptio-cloudability-standard/en/support-optimize-cloudability-performance.md
  - kb/02-product-docs/apptio-cloudability-standard/en/support-custom-discounts-enterprise-discount-programs-edp.md
  - kb/02-product-docs/apptio-cloudability-standard/en/edp-configure-enterprise-discount-program-aws.md
  - kb/02-product-docs/apptio-cloudability-standard/en/support-request-refetch-reprocess-in-cloudability.md
last_updated: "2026-07-09"
---
# Technical Support — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

El capítulo de cierre cubre cuatro áreas operativas distintas: el canal formal de soporte, diagnóstico de performance/outages, la mecánica de descuentos empresariales negociados (EDP), y el proceso de corrección retroactiva de datos históricos — cerrando el círculo completo del ciclo de vida operativo de Cloudability.

## Cómo lo resuelve IBM Cloudability Standard

**Canal de soporte formal** vía IBM Support, para abrir y ver casos de soporte.

**Optimize Cloudability Performance — diagnóstico diferenciado entre problema de configuración y outage real.** Buenas prácticas de dashboard documentadas (selección correcta de métricas, número de widgets por dashboard, configuración de permisos de compartición) como primera línea de diagnóstico antes de escalar. **Mass Outage** se define explícitamente como un incidente de producción que afecta al cliente, con proceso dedicado: consultar `status.cloudability.com` primero. Para problemas que no son outage masivo, el formulario de soporte pide explícitamente: ¿está relacionado a algún outage conocido?, ¿revisó la página de estado?, ¿afecta a múltiples usuarios?, ¿es de una página específica o de todo el sistema? — un protocolo de triage estructurado antes de escalar. Archivos HAR disponibles como herramienta de diagnóstico de lentitud específica del ambiente del cliente.

**Custom Discounts and Enterprise Discount Programs (EDP) — cómo los descuentos negociados se propagan a través de todo el producto.** Los descuentos personalizados afectan reporting/análisis de costo, rightsizing, compromisos, y workload planning — no es una configuración aislada, sino una entrada que ajusta el comportamiento de casi todo el producto. Dos métricas de costo dedicadas ya vistas en Data Reference (**Cost Adjusted**, **Cost Adjusted Amortized**) requieren el módulo de custom pricing habilitado. En Rightsizing específicamente, tanto **On-Demand Cost** como **Effective Cost** incorporan las tarifas personalizadas/EDP cuando están habilitadas. Workload Planning soporta precio personalizado por defecto, cayendo a precio Retail para organizaciones sin acuerdo negociado con el proveedor.

**Configure Enterprise Discount Program for AWS — el procedimiento de configuración real, con una advertencia de compatibilidad explícita.** Cloudability implementa los mismos descuentos negociados a nivel de recurso y **en tiempo real**, mientras AWS solo los muestra al final del mes — una ventaja de visibilidad temprana real. Advertencia crítica: **configurar custom pricing no es adecuado para un cliente que ya tiene el Automated Discount Program (ADP) de AWS desplegado** — son mecanismos incompatibles, no complementarios. El formulario de solicitud de EDP (AWS Private Pricing PDF) requiere diez campos específicos: término del descuento, año de contrato, cuentas payer elegibles, cuenta de créditos, descuento cross-service, descuentos/tarifas específicas por servicio, regiones con tarifa específica, y compromiso de gasto (documentado explícitamente como "información útil, pero no utilizable programáticamente").

**Request Refetch and Reprocess in Cloudability — dos mecanismos de corrección de datos, con propósitos distintos.** **Refetch** actualiza datos históricos de nube desde el proveedor — con una limitación documentada explícitamente: los meses N y N-1 no disparan refetch (se manejan automáticamente por los procesos BAU), y si una cuenta ya fue dada de baja en el proveedor, un refetch posterior puede no poder recuperar tags a nivel de cuenta/suscripción/grupo de recursos. **Reprocess** actualiza Business Metrics, Business Mappings, Tags & Labels y Account Groups retroactivamente — documentado como "el tipo de solicitud de actualización más común". Advertencia de costo real: **un refetch de GCP genera un costo real** al cliente por extraer los datos nuevamente de Google.

## Por qué importa en una conversación con el cliente

La incompatibilidad entre Custom Pricing de Cloudability y el Automated Discount Program (ADP) de AWS es una advertencia crítica de discovery técnico a verificar **antes** de cualquier configuración de EDP — configurar ambos simultáneamente genera un conflicto real, no solo una redundancia.

El protocolo de triage de performance (¿outage conocido?, ¿página de estado revisada?, ¿múltiples usuarios?, ¿alcance específico?) es directamente reutilizable como script de primer nivel de soporte para el equipo operativo del cliente, reduciendo escalamientos innecesarios a soporte formal de IBM.

El costo real asociado a un refetch de GCP es un detalle operativo importante a comunicar proactivamente — un cliente que solicita refetch de varios meses de historia de GCP sin conocer esta implicación de costo puede llevarse una sorpresa en su propia factura de GCP.

## Documentos fuente

- Technical Support — `kb/02-product-docs/apptio-cloudability-standard/en/support-technical.md`
- Optimize Cloudability Performance — `kb/02-product-docs/apptio-cloudability-standard/en/support-optimize-cloudability-performance.md`
- Custom Discounts and Enterprise Discount Programs (EDP) — `kb/02-product-docs/apptio-cloudability-standard/en/support-custom-discounts-enterprise-discount-programs-edp.md`
- Configure Enterprise Discount Program for AWS — `kb/02-product-docs/apptio-cloudability-standard/en/edp-configure-enterprise-discount-program-aws.md`
- Request Refetch and Reprocess in Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/support-request-refetch-reprocess-in-cloudability.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
