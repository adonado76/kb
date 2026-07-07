---
tbm_concept: "Integración con SAP LeanIX (arquitectura empresarial y portafolio de aplicaciones enriqueciendo el TCO con contexto estratégico)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
  - sap-leanix
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/sapleanix/sap-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/sapleanix/sap-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/sapleanix/sap-getstart.md
last_updated: "2026-07-05"
---
# Integración con SAP LeanIX — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

El brief de Applications ya estableció que un campo requerido central de ese módulo es **Application Investment Objective** — pero clasificar correctamente ese objetivo (¿esta aplicación es estratégica, en tolerancia, o candidata a retiro?) requiere una disciplina de arquitectura empresarial que Costing Standard, por sí solo, no está diseñado para sostener. SAP LeanIX es una plataforma de gestión de arquitectura empresarial y portafolio de aplicaciones — exactamente el tipo de sistema donde esa clasificación estratégica vive y se mantiene actualizada por los equipos de arquitectura.

## Cómo lo resuelve Apptio Costing Standard

**La integración trae contexto de arquitectura empresarial hacia el modelo de costo, complementando el dato financiero con dato estratégico.** Donde ServiceNow aporta principalmente configuración técnica (CMDB, tickets, catálogo operativo), SAP LeanIX aporta la capa de gobierno de portafolio: relaciones entre aplicaciones, dependencias tecnológicas, y clasificaciones de ciclo de vida y valor estratégico — enriqueciendo directamente los reportes de Application Portfolio, Application List e Impact of Retiring Applications ya documentados, que dependen de tener esa clasificación correctamente mantenida.

**El propósito es evitar que la clasificación estratégica de aplicaciones (Invest/Tolerate/Migrate/Eliminate, ya vista repetidamente en Applications, Services y Products) se mantenga de forma duplicada y potencialmente inconsistente entre dos sistemas** — la integración sincroniza esa clasificación desde LeanIX, donde típicamente la mantienen los equipos de arquitectura empresarial, hacia el modelo de costo, donde se usa para agrupar y priorizar el análisis financiero.

**Reportes centrados en verificar la cobertura y consistencia de los datos de arquitectura sincronizados**, de forma análoga a la integración de ServiceNow — permitiendo confirmar que el portafolio de aplicaciones en Costing Standard refleja correctamente las relaciones y clasificaciones mantenidas en LeanIX antes de confiar en los reportes de portafolio downstream.

## Por qué importa en una conversación con el cliente

Esta integración es el complemento natural de ServiceNow para clientes con una práctica de arquitectura empresarial madura: ServiceNow resuelve "qué tenemos y cómo está configurado" (CMDB técnico), mientras LeanIX resuelve "qué tan estratégicamente importante es y hacia dónde va" (arquitectura y portafolio) — juntas, dan al modelo de Applications, Services y Products tanto la base técnica como el contexto estratégico necesario para que la clasificación de inversión sea defendible y esté actualizada.

Vale la pena posicionar esta integración específicamente en conversaciones donde el cliente ya expresó interés en los reportes de racionalización de portafolio (Application Portfolio, Impact of Retiring Applications) — sin una fuente confiable de clasificación estratégica como LeanIX, esos reportes dependen de que alguien mantenga esa clasificación manualmente dentro de Costing Standard, lo cual es exactamente el tipo de trabajo duplicado que esta integración evita.

## Documentos fuente

- SAP LeanIX Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/sapleanix/sap-overview.md`
- SAP LeanIX Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/sapleanix/sap-reports.md`
- SAP LeanIX Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/sapleanix/sap-getstart.md`

*Nota: no se identificaron links públicos de ibm.com/docs embebidos verificables en esta categoría. Hipervínculos externos pendientes según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*