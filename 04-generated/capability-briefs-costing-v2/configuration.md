---
tbm_concept: "Configuration (el flujo completo de puesta en marcha de un proyecto de Costing Standard, desde su creación hasta la carga y validación del primer modelo de costo)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/createproject.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/configproject.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/configtime.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/installitpfintegration.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/loaddata.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/maptomaster.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/validatemodel.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/install-apptio-ibm-costing-old-template.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/installing-new-solutions.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/aboutct.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/aboutcsconfig.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/aboutcustom.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/aboutmoduleconfig.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/generalconfig.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/moduleconfig.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/optionalconfig.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/multicurrency.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/addformulastep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/idsharedservices.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/dataqualitydim.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/populatecostsource.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/populatecostsource2.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/uploadmapctf.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-capex-component.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-cs-component.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-labor-component.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-laborunits-component.md
last_updated: "2026-07-05"
---
# Configuration — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

Todos los módulos documentados hasta ahora (Labor, Vendor, Compute, Applications, Business Units...) asumen que existe un proyecto de Costing Standard funcional, con su calendario fiscal definido, sus componentes instalados, y su primer conjunto de datos cargado y validado. Esta categoría es esa base — el conjunto de pasos secuenciales que convierten un proyecto vacío en un modelo de costo funcional, y las decisiones de arquitectura (personalización, multi-moneda, servicios compartidos) que afectan a todos los módulos posteriores.

## Cómo lo resuelve Apptio Costing Standard

### La secuencia de siete pasos, en el orden documentado explícitamente por el producto

1. **Create a Project** — crear el ambiente de trabajo a partir de una plantilla de IBM Apptio, que trae consigo la taxonomía ATUM, componentes disponibles y contenido predefinido.
2. **Set Time** — definir el calendario fiscal del proyecto (mensual, trimestral, año fiscal) antes de cargar cualquier dato, porque todos los períodos de reporte dependen de esta configuración.
3. **Installing Components** — instalar los componentes modulares necesarios (Cost Source, Labor, Vendors, Servers, etc., cada uno ya documentado en su propio brief) — nada se instala automáticamente salvo CTF-Cost Source.
4. **Load Data** — cargar los datasets crudos (financieros, operativos, de consumo) hacia las tablas de entrada del proyecto.
5. **Map Data to Master Data** — mapear los campos cargados hacia las tablas de datos maestros que cada componente espera (el paso que hemos visto repetirse, con variaciones, en cada uno de los módulos ya documentados).
6. **Validate Model Allocations** — confirmar que el costo fluye correctamente a través de las reglas de asignación configuradas, antes de confiar en los reportes.
7. **Installing New IBM Apptio Costing Solutions on Older Template Projects** — un camino alternativo para proyectos ya existentes en plantillas antiguas que necesitan adoptar módulos más nuevos (como AI TCO o Hybrid IT TCO Impact) sin reconstruir el proyecto desde cero.

### Conceptos fundacionales que afectan a todos los módulos

**La distinción entre Costing Standard Foundation (CTF) y Applications and Services Module, ya insinuada en briefs anteriores, se confirma aquí explícitamente**: CTF es el módulo más estandarizado y con menor necesidad de personalización; el módulo de Applications and Services (Compute, Storage, Applications, Services, etc.) es el que típicamente requiere más ajuste a la realidad específica de cada organización.

**La customización tiene un costo futuro que el producto advierte explícitamente**: cualquier cambio al modelo estándar (nuevas reglas de asignación, campos adicionales, lógica propia) es una Customización, y el producto documenta que estas requieren atención especial durante los Upgrades — un upgrade puede traer nuevas asignaciones, reportes o cambios de taxonomía ATUM que entran en conflicto con una personalización previa si no se gestionan con cuidado. Esta es la primera vez que el ciclo de vida de mantenimiento a largo plazo (no solo la implementación inicial) aparece documentado con este nivel de explicitud.

**Multi-moneda** se configura a nivel de proyecto, con tablas de tasas de cambio que afectan de forma transversal todos los módulos que manejan valores monetarios — relevante para cualquier cliente con operación multi-país, un patrón ya visto en Apptio Planning.

**Identificación de servicios compartidos (Shared Services)** — un concepto de asignación específico para costos que no pertenecen a un solo consumidor sino que se distribuyen entre varios (labor de soporte compartido, licencias corporativas), relevante para entender correctamente cómo el costo indirecto se reparte, en línea con la lógica de asignación Directa/Indirecta ya vista en Business Units.

**Dimensiones de calidad de datos**, documentadas como un concepto propio — sugiriendo que el producto tiene un marco explícito para medir qué tan completos, consistentes y confiables son los datos cargados, más allá de simplemente cargarlos y esperar que los reportes "se vean bien".

### Populate Cost Source: el proceso de carga más repetido de todo el producto, documentado en dos partes

Dado que CTF-Cost Source es el componente que se instala automáticamente y es prerrequisito de prácticamente todos los demás módulos ya documentados (Labor, Vendor, Fixed Assets, Resource Towers, Applications...), el proceso de poblarlo correctamente — en dos partes documentadas por separado — es, en efecto, el paso de configuración más crítico de todo el producto. Un error aquí se propaga a todos los módulos posteriores.

### Cuatro componentes CTF documentados con su propio detalle técnico

**CTF-CapEx** — separa el reporting de gasto de capital del de OpEx (ya mencionado en el brief de IT Financials).
**CTF-Cost Source** — el componente fundacional, prerrequisito universal.
**CTF-Labor** — habilita reporting de costo y headcount (ya documentado en el brief de Workforce).
**CTF-Labor Units** — la alternativa a Time Tracking para asignar headcount vía métricas de unidades de labor (ya documentada en el brief de Workforce, donde se estableció que normalmente se usa uno u otro, no ambos).

## Por qué importa en una conversación con el cliente

La secuencia de siete pasos es el mejor mapa de proyecto de implementación disponible en toda la documentación — vale la pena usarla literalmente como esqueleto de un plan de trabajo en cualquier propuesta de implementación de Costing Standard, ya que refleja el orden real y obligatorio, no una sugerencia.

La advertencia sobre el costo futuro de la personalización es un argumento importante de gobernanza de proyecto a comunicar desde el discovery inicial: cada personalización que el cliente pida "porque así lo hacemos nosotros" tiene un costo de mantenimiento en cada upgrade futuro — vale la pena que esta conversación ocurra explícitamente durante el diseño de la solución, no como sorpresa en el primer upgrade post-implementación.

El hecho de que CTF-Cost Source sea prerrequisito casi universal, documentado en dos partes de carga, confirma algo que ya era evidente de forma implícita en todos los briefs anteriores: la calidad de la implementación inicial de Cost Source determina, en gran medida, la calidad de todo el resto del programa TBM del cliente — es el lugar correcto para invertir el mayor rigor de validación de datos.

## Documentos fuente

- Create a Project — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/createproject.md`
- Configure a Project — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/configproject.md`
- Set Time — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/configtime.md`
- Installing Components — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/installitpfintegration.md`
- Load Data — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/loaddata.md`
- Map Data to Master Data — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/maptomaster.md`
- Validate Model Allocations — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/validatemodel.md`
- Installing New IBM Apptio Costing Solutions on Older Template Projects — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/install-apptio-ibm-costing-old-template.md`
- Installing New Solutions (guía complementaria) — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/installing-new-solutions.md`
- About Cost Transparency (CT) — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/aboutct.md`
- About Costing Standard Configuration — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/aboutcsconfig.md`
- About Customizations — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/aboutcustom.md`
- About Module Configuration — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/aboutmoduleconfig.md`
- General Configuration — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/generalconfig.md`
- Module Configuration — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/moduleconfig.md`
- Optional Configuration — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/optionalconfig.md`
- Multi-currency Configuration — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/multicurrency.md`
- Add a Formula Step — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/addformulastep.md`
- Identify Shared Services — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/idsharedservices.md`
- Data Quality Dimensions — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/dataqualitydim.md`
- Populate Cost Source (Part 1) — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/populatecostsource.md`
- Populate Cost Source (Part 2) — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/populatecostsource2.md`
- Upload and Map CTF Data — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/uploadmapctf.md`
- CTF - CapEx component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-capex-component.md`
- CTF - Cost Source component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-cs-component.md`
- CTF - Labor component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-labor-component.md`
- CTF - Labor Units component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-laborunits-component.md`

*Nota: no se identificaron links públicos de ibm.com/docs embebidos verificables en esta categoría. Hipervínculos externos pendientes según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*