---
tbm_concept: "Getting Started (qué es Benchmarking, tipos de benchmark, fuentes de datos, roles y glosario fundacional)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-benchmarking
status: draft
generated_from:
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/benchmarking.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/started-what-you-can-do-benchmarking.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/started-overview-benchmarking-application.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/started-key-benefits.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/started-benchmark-types.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/started-data-partners-benchmark-sources.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/started-product-components-glance.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/started-user-roles-permissions.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/started-appendix-glossary-acronyms.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/started-appendix-b-version-compatibility-notes.md
last_updated: "2026-07-12"
---
# Getting Started — Cómo IBM Apptio Benchmarking Aborda Esta Capacidad

## El concepto

Costing Standard responde "cuánto nos cuesta la tecnología" y Planning responde "cuánto debería costarnos hacia adelante" — pero ninguno de los dos responde una pregunta que todo CIO y CFO termina haciendo tarde o temprano: **¿estos números son buenos o malos comparados con organizaciones similares?** Sin un punto de referencia externo, cualquier conversación sobre eficiencia de costos se queda en el terreno de las opiniones internas ("siempre lo hemos hecho así", "creo que gastamos demasiado en X"). Benchmarking cierra esa brecha, poniendo los costos ya modelados en Costing al lado de datos de peers reales, normalizados a la misma taxonomía TBM.

## Cómo lo resuelve IBM Apptio Benchmarking

**Posicionamiento: una capa de contexto externo sobre Costing, no un reemplazo.** Benchmarking es una aplicación SaaS que no requiere Costing para funcionar, pero está fuertemente recomendada su integración para aprovechar las funciones de cruce automático y los reportes "benchmark-enabled". El alcance actual cubre tres niveles: métricas de costo y eficiencia de infraestructura a nivel de Resource Tower y Sub-Tower, métricas de OpEx de TI mapeadas a Cost Pools y Towers, y métricas de gasto y labor a nivel de industria/empresa.

**Tres tipos de benchmark, cada uno con un propósito distinto en la conversación con el cliente:**

- **Benchmarks de industria** — métricas macro a nivel empresa (IT spend como % de revenue, mix de labor de TI) útiles para conversaciones de junta directiva y para validar si el gasto total de TI está en línea para el tamaño y sector del cliente.
- **Benchmarks de OpEx de TI** — distribuciones de gasto operativo por Cost Pool y Resource Tower, más "arquetipos" (perfiles operativos comunes, ej. "centrado en labor" vs. "centrado en vendors") que ayudan a validar si la estructura de gasto del cliente coincide con su modelo operativo intencionado.
- **Benchmarks de infraestructura** — costos unitarios y eficiencia por Tower/Sub-Tower (costo por servidor, costo por TB, FTE por 100 servidores), el nivel más granular, usado para justificar decisiones de sourcing y optimización torre por torre.

El patrón de adopción típico documentado es progresivo: los clientes empiezan con métricas de industria para enmarcar el panorama general, pasan a OpEx para revisar estructura de gasto, y terminan en infraestructura para el detalle de iniciativas específicas — una secuencia útil para estructurar la primera conversación de descubrimiento con un cliente nuevo.

**Tres fuentes de datos combinadas, todas normalizadas a la taxonomía TBM:**

- **Rubin Worldwide** — datos de economía de TI e industria a nivel empresa.
- **ISG** — métricas de infraestructura a nivel Resource Tower/Sub-Tower.
- **Datos anonimizados de la comunidad Apptio** — costos reales de clientes que optaron por compartir, agregados y anonimizados a nivel Cost Pool.

Este es un punto de venta importante frente a un cliente escéptico sobre benchmarks genéricos: no es un solo proveedor de datos de mercado, es una combinación de tres fuentes con metodologías distintas, todas ya alineadas a la misma taxonomía que el cliente ya usa en Costing — por lo que la comparación es directa, sin trabajo de re-mapeo adicional.

**Dos componentes de producto con roles complementarios:**

- **Interactive Benchmarking** — el dataset completo de benchmarks, no requiere un proyecto de Costing para empezar a explorar. Permite auto-seleccionar peer groups por industria, región, tamaño de revenue y escala, mostrando rangos, cuartiles, mínimo/máximo y arquetipos. También es la fuente de los "perfiles de benchmark" que se cargan en reportes de Costing.
- **Reportes benchmark-enabled en Costing** — consumen los perfiles seleccionados en Interactive Benchmarking y los combinan con los costos ya modelados del cliente, mostrando vistas lado a lado de actual vs. benchmark con drill-through hasta el detalle de cuenta contable.

**Modelo de roles simple pero con permisos granulares disponibles.** El rol estándar es Admin (acceso completo, incluida la administración de Access Administration), pero la plataforma permite crear roles personalizados con permisos específicos — por ejemplo, separar quién puede *configurar* perfiles de benchmarking de quién solo puede *ver* dashboards, o controlar quién tiene permiso de borrar datos de Interactive Benchmarking de forma permanente. Esto es relevante en clientes con estructuras de gobierno más estrictas entre TBMAs, ITFMAs y stakeholders de negocio.

**Alineación de versión TBM: un detalle de scoping que evita sorpresas tardías.** La versión de ATUM (Apptio's TBM Unified Model) seleccionada en la configuración de Interactive Benchmarking determina qué Cost Pools, Resource Towers y Sub-Towers existen y cómo se agrupan las métricas de infraestructura. Un cambio de versión sin coordinación entre Costing y Benchmarking rompe las comparaciones históricas — el documento recomienda explícitamente completar primero la migración del lado de Costing antes de tocar la configuración de Interactive Benchmarking, y tratar el año del cambio de versión como una nueva línea base en vez de intentar comparar cifras pre y post-cambio directamente.

**Funciona sin Costing, pero con limitaciones que vale la pena anticipar.** Es posible cargar costos anuales manualmente o vía archivo, y seguir usando benchmarks de industria y OpEx (e incluso algunos de infraestructura si se suministra costo y volumen por Sub-Tower manualmente). Lo que se pierde sin la integración: drill-back al mayor general, vendors o servicios dentro de Costing, y un refresh de datos mucho más manual. El documento es explícito en que este modo es válido para un piloto, pero para uso sostenido se recomienda fuertemente la integración con Costing.

## Por qué importa en una conversación de cliente

Esta capacidad es el punto de entrada natural para posicionar Benchmarking frente a un cliente que ya tiene Costing Standard implementado: el argumento no es "aquí hay otra herramienta que aprender", sino "los datos que ya modelaste en Costing ahora pueden compararse automáticamente contra tres fuentes de benchmark ya normalizadas a tu misma taxonomía, sin trabajo adicional de mapeo". El glosario extenso (Apéndice A) también es un activo práctico en sí mismo — términos como "archetype", "peer group" o "unit cost" no siempre son intuitivos, y tenerlos definidos con precisión ayuda a evitar malentendidos en la primera reunión de descubrimiento con el cliente. Finalmente, la nota de alineación de versión TBM es una bandera roja útil para levantar temprano en cualquier discovery técnico: si el cliente está en medio de una migración de taxonomía, hay que secuenciar bien el trabajo de Costing antes de tocar Benchmarking.

## Documentos fuente

- Benchmarking (landing/índice) — `02-product-docs/tbm-apptio/apptio-benchmarking/en/benchmarking.md`
- What you can do with Benchmarking — `02-product-docs/tbm-apptio/apptio-benchmarking/en/started-what-you-can-do-benchmarking.md`
- Overview of the Benchmarking application — `02-product-docs/tbm-apptio/apptio-benchmarking/en/started-overview-benchmarking-application.md`
- Key Benefits — `02-product-docs/tbm-apptio/apptio-benchmarking/en/started-key-benefits.md`
- Benchmark types — `02-product-docs/tbm-apptio/apptio-benchmarking/en/started-benchmark-types.md`
- Data partners and Benchmark sources — `02-product-docs/tbm-apptio/apptio-benchmarking/en/started-data-partners-benchmark-sources.md`
- Product components at a glance — `02-product-docs/tbm-apptio/apptio-benchmarking/en/started-product-components-glance.md`
- User Roles & Permissions — `02-product-docs/tbm-apptio/apptio-benchmarking/en/started-user-roles-permissions.md`
- Appendix A: Glossary & Acronyms — `02-product-docs/tbm-apptio/apptio-benchmarking/en/started-appendix-glossary-acronyms.md`
- Appendix B: Version & Compatibility Notes — `02-product-docs/tbm-apptio/apptio-benchmarking/en/started-appendix-b-version-compatibility-notes.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
