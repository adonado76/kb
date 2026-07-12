---
tbm_concept: "Getting Started (conceptos clave, terminología y navegación de Apptio Costing Standard)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/get-started/intro-ibm-cost.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/get-started/costing-terminologies.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/get-started/costing-guide-nav.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/get-started/ct-how-to-access.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/get-started/what-you-can-do.md
last_updated: "2026-07-05"
---
# Getting Started — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

Antes de entrar al detalle de cualquier módulo, un practicante necesita tres cosas: saber qué es la herramienta y para qué sirve, dominar el vocabulario que usa internamente (que no siempre coincide con el vocabulario financiero tradicional), y saber moverse por su interfaz. Sin esto, cualquier conversación posterior sobre Labor, Vendor o Public Cloud se vuelve más difícil de seguir — son módulos que dan por sentado que ya se entienden términos como ATUM, Componente o Master Data Set.

## Cómo lo resuelve Apptio Costing Standard

**Posicionamiento del producto.** Costing Standard se define como la solución central de IT Financial Management de IBM Apptio: transforma datos financieros, operativos y de consumo en inteligencia financiera confiable, y funciona como el "sistema de registro" que alimenta capacidades de nivel superior en el resto del portafolio — Planning, Billing y Benchmarking. Esto es clave para posicionar Costing Standard correctamente frente a un cliente: no es una herramienta aislada de reporting, es la base de datos de costos sobre la que se construye todo lo demás.

**Un mapa de seis tipos de casos de uso.** La introducción organiza toda la capacidad del producto en seis categorías que luego se convierten en las secciones principales de navegación: Financial Use Cases (labor, vendors, proyectos, activos fijos, nube pública), Infrastructure Use Cases (Data Centers, Compute, Storage, Network, End-User Devices, Service Desk), Solution Use Cases (Applications, Services, Products, Business Units), Strategic Technology Domains (Mainframe, AI, Hybrid IT), Cost Modeling & Allocation (metodología ATUM), e Integraciones (Planning, Cloudability, otras fuentes empresariales). Este mapa es, en efecto, la tabla de contenido de todo lo que cubriremos en los siguientes capítulos de esta base de conocimiento.

**Terminología fundacional con definiciones precisas.** El glosario de conceptos clave establece distinciones que son fáciles de confundir si no se explicitan:

- **AVF (Apptio Value Framework)** — organiza los casos de uso de ITFM alrededor de un problema, las capacidades que lo resuelven, y las personas involucradas. Es el marco que conecta capacidad de producto con valor de negocio.
- **ATUM (Apptio TBM Unified Model)** — el modelo de costeo estandarizado de IBM Apptio que alinea datos financieros, operativos y de consumo con la taxonomía TBM.
- **Proyecto, Plantilla (Template) y Componente** — un Proyecto es el ambiente de trabajo; una Plantilla da acceso a contenido predefinido de IBM Apptio; un Componente es un paquete modular instalable (Labor, Vendors, Servers, Storage, Applications, etc.) que trae consigo datasets maestros, tablas de referencia, lógica de asignación y reportes ya construidos.
- **Master Data Set (MDS), Modelo, Métrica y Asignación (Allocation)** — forman la cadena lógica del producto: los MDS normalizan datos de múltiples sistemas; el Modelo define cómo se estructuran y transforman los costos; las Métricas (OpEx, CapEx, horas de labor, GB de almacenamiento) sirven como drivers; las Asignaciones son las reglas que mueven el costo de un objeto a otro (de Labor a Resource Towers, de Servers a Applications) usando esos drivers.
- **Customización y Upgrade** — cualquier cambio al modelo estándar es una Customización, y requiere atención especial durante los Upgrades, que traen nuevas asignaciones, reportes o actualizaciones de taxonomía TBM.

**Navegación con dos experiencias coexistentes.** La guía de navegación documenta que Costing Standard actualmente opera bajo dos interfaces de reporting: el **TBM Report Studio clásico** (con su página de inicio organizada por colecciones de reportes, menú lateral con Landing Page/Recientes/Favoritos, y una barra superior con selector de entorno, manejo de release Trunk/Branch/Hotfix, comentarios colaborativos, multi-moneda y exportación) y el **New Report Studio** (disponible desde la versión 12.11.21, con una experiencia rediseñada de creación y gestión de reportes y colecciones). Un detalle operativo relevante: los clientes en la versión 12.11.19 deben inscribirse en el preview público para ver el botón de acceso al nuevo Report Studio — no es automático.

**Acceso vía Apptio Experience (Apex).** El acceso al producto se documenta como unificado a través de Apex, consistente con el resto del portafolio Apptio.

**Tres módulos, no un monolito.** "What You Can Do" aclara que Costing Standard se compone de tres módulos independientes: **Costing Standard Foundation** (vista mensual del desempeño financiero de TI contra presupuesto, y qué drivers