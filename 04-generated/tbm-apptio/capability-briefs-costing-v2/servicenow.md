---
concept: "Integración con ServiceNow (sincronización de CMDB, tickets y catálogo de servicios hacia el modelo de costo)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
  - servicenow
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/servicenow/sn-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/servicenow/sn-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/servicenow/sn-getstart.md
last_updated: "2026-07-05"
---
# Integración con ServiceNow — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

A lo largo de este proyecto hemos visto que módulos como Service Desk, Applications, Data Centers y Compute dependen de datos maestros que en la práctica viven en un CMDB o en una plataforma ITSM — configuración de activos, relaciones entre aplicaciones e infraestructura, tickets de soporte, catálogo de servicios. ServiceNow es, para la mayoría de las organizaciones de TI empresarial, exactamente esa plataforma. Sin una integración directa, mantener sincronizados esos datos maestros entre ServiceNow y Costing Standard requeriría exportaciones e importaciones manuales recurrentes, con el riesgo de desactualización que eso implica.

## Cómo lo resuelve Apptio Costing Standard

**La integración trae tres tipos de datos de ServiceNow hacia el modelo de costo**: configuración de activos e infraestructura desde el CMDB (alimentando directamente los módulos de Compute, Storage, Network Devices y Data Centers ya documentados con sus tablas de master data), volumen y detalle de tickets desde el módulo ITSM (alimentando el módulo de Service Desk, incluyendo los campos de Priority, Weighting y tipo de ticket ya vistos en ese brief), y catálogo y relaciones de servicio desde el módulo de Service Catalog/CMDB (alimentando la tabla All Business Services usada por Services, Products y Business Units).

**El propósito documentado es mantener el modelo de costo alineado con la fuente de verdad operativa de ServiceNow**, en lugar de requerir que los datos de configuración e infraestructura se mantengan por duplicado en Costing Standard. Esto reduce directamente el trabajo manual de carga y mapeo que hemos visto repetido en casi todos los módulos de Infrastructure y Solution Use Cases (Servers, Storage, Data Centers, Service Desk, Applications, Services), ya que ServiceNow suele ser precisamente la fuente típica documentada para varios de ellos.

**Instalación como integración de datos configurable**, con getting started documentando los pasos de habilitación específicos de conexión entre ambos sistemas — sin la complejidad de arquitectura de múltiples workbenches vista en Hybrid IT TCO Impact, ni el conector de plataforma externa dedicado visto en Turbonomic; es una integración de sincronización de datos maestros más directa.

**Reportes**: la colección de reportes de esta integración se enfoca en verificar y visualizar la calidad y cobertura de los datos sincronizados desde ServiceNow — permitiendo confirmar que la información de CMDB, tickets y catálogo de servicio efectivamente está alimentando el modelo de costo de forma completa y consistente antes de confiar en los reportes downstream de Compute, Storage, Service Desk, Applications y Services.

## Por qué importa en una conversación con el cliente

Esta integración es, probablemente, la de mayor impacto de eficiencia de implementación de todo el proyecto para clientes que ya usan ServiceNow como su plataforma ITSM/CMDB estándar (la mayoría de las organizaciones empresariales grandes) — reduce directamente el esfuerzo de carga manual documentado repetidamente como prerrequisito en Servers, Storage, Data Centers, Service Desk, Applications y Services.

Vale la pena preguntar explícitamente en cualquier discovery temprano si el cliente usa ServiceNow, y en qué medida su CMDB está actualizado y bien mantenido — la calidad de esta integración, como cualquier integración de datos maestros, depende directamente de la calidad y disciplina de los datos en el sistema origen.

Esta integración también conecta con la conversación de Applications Portfolio Management, dado que ServiceNow APM apareció ya mencionado como fuente típica de propiedad y ciclo de vida de aplicaciones en el brief de Services — reforzando que ServiceNow no es solo una fuente de datos técnicos, sino también de gobernanza de portafolio.

## Documentos fuente

- ServiceNow Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/servicenow/sn-overview.md`
- ServiceNow Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/servicenow/sn-reports.md`
- ServiceNow Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/servicenow/sn-getstart.md`

*Nota: no se identificaron links públicos de ibm.com/docs embebidos verificables en esta categoría. Hipervínculos externos pendientes según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*