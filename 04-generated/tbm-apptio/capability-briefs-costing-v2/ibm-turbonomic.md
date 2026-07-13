---
concept: "Integración con IBM Turbonomic (recomendaciones de optimización de infraestructura en tiempo real, enriqueciendo el TCO retrospectivo con acción prospectiva)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
  - ibm-turbonomic
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/ti-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/ibm-turbonomic.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/ibm-turb-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/architecture.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/pre-requisite.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/install-_component.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/data-uploaded.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/reporting.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/configuations.md
last_updated: "2026-07-05"
---
# Integración con IBM Turbonomic — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

Todo lo documentado hasta ahora en Costing Standard responde "cuánto costó" — una vista retrospectiva, necesaria pero pasiva. IBM Turbonomic resuelve la mitad complementaria: qué hacer al respecto, en tiempo real. Es una plataforma de gestión de recursos de aplicación que analiza continuamente utilización real y genera recomendaciones accionables de right-sizing, colocación de workload y compra de capacidad — sin esta integración, el costeo de Compute, Storage y Public Cloud da visibilidad de qué se gastó, pero no una ruta clara y automatizada hacia cuánto se podría ahorrar.

## Cómo lo resuelve Apptio Costing Standard

**Turbonomic aporta la capa de "qué hacer", Costing Standard aporta la capa de "qué costó" — la integración las une en el mismo modelo.** Turbonomic monitorea continuamente el consumo real de recursos (CPU, memoria, IOPS, almacenamiento) a través de ambientes on-premise, nube privada y nube pública, y genera acciones específicas (redimensionar una VM, mover un workload, comprar una instancia reservada) basadas en demanda real, no en capacidad aprovisionada estática. La integración trae esos datos de utilización y esas recomendaciones de optimización hacia el modelo de costo de Costing Standard, permitiendo cuantificar en dólares el impacto de seguir — o no seguir — cada recomendación.

**Arquitectura de datos vía conector Datalink dedicado.** Turbonomic expone sus datos de utilización y recomendaciones a través de su API; un conector Apptio Datalink específico para Turbonomic extrae esos datos y los carga en tablas dedicadas dentro de Costing Standard, donde se combinan con el costo ya modelado en Compute (Servers), Storage y Public Cloud — enriqueciendo esos reportes existentes con una dimensión de "oportunidad de optimización" que antes no existía.

**Instalación como componente separado, con prerrequisitos de plataforma explícitos.** La integración requiere una instancia de IBM Turbonomic ya desplegada y en operación (no es parte de Costing Standard, es un producto separado del portafolio IBM), con acceso API habilitado, además de los prerrequisitos usuales de Costing Standard (CTF-Cost Source, y los componentes de Compute/Storage/Public Cloud correspondientes ya instalados, para que haya un modelo de costo base sobre el cual superponer las recomendaciones).

**El reporting resultante combina costo actual con ahorro potencial cuantificado.** En lugar de reportes nuevos independientes, la integración enriquece los reportes ya documentados de Compute, Storage y Public Cloud (Host Server Details, Storage Utilization Summary, Cloud TCO Cost Driver, etc.) con columnas o vistas adicionales que muestran qué recomendación de Turbonomic aplica a cada recurso, y cuál sería el impacto de costo de implementarla.

## Por qué importa en una conversación con el cliente

Esta integración es el argumento más fuerte de todo el proyecto para cerrar el ciclo completo de FinOps: visibilidad de costo (Costing Standard) → recomendación de acción (Turbonomic) → decisión informada → nueva medición de costo. Para un cliente que ya tiene ambos productos IBM, presentar esta integración como el "cierre del círculo" es mucho más persuasivo que hablar de cada producto por separado.

Para un cliente que aún no tiene Turbonomic, esta integración es un argumento de expansión de portafolio natural: una vez que Costing Standard ya reveló dónde está el gasto (vía los reportes de Compute/Storage/Public Cloud ya documentados), Turbonomic es la respuesta lógica a "¿y ahora qué hacemos con esta información?" — pasar de un reporte de diagnóstico a un motor de acción continua.

Vale la pena aclarar en discovery que esta es una integración entre dos productos separados del portafolio IBM, no una funcionalidad nativa de Costing Standard — el cliente necesita (o necesitará adquirir) IBM Turbonomic por separado para activarla.

## Documentos fuente

- Technology Integrations Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/ti-overview.md`
- IBM Turbonomic Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/ibm-turbonomic.md`
- IBM Turbonomic Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/ibm-turb-gs.md`
- Integration Architecture — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/architecture.md`
- Prerequisites — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/pre-requisite.md`
- Install the component — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/install-_component.md`
- Data uploaded via the integration — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/data-uploaded.md`
- Reporting enriched by Turbonomic data — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/reporting.md`
- Configurations — `02-product-docs/apptio-costing-standard/en/cost-transparency/technology-integration/configuations.md`

*Nota: no se identificaron links públicos de ibm.com/docs embebidos verificables en esta categoría. Hipervínculos externos pendientes según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*