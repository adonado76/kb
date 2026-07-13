---
concept: "Mainframe TCO (costeo defendible por MSU/zIIP, showback/chargeback, benchmarking de industria)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/mf-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/mf-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/mf-reports-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/mf-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/mainframes.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/mainframe-tco-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/mainframe-config-guide.md
last_updated: "2026-07-05"
---
# Mainframe — Cómo Apptio Costing Standard Aborda Esta Capacidad

## El concepto

El mainframe sigue siendo la plataforma preferida para workloads transaccionales de alto volumen que exigen confiabilidad, seguridad y desempeño consistente — pero también es uno de los dominios de costo más opacos: unidades de medida propias (MSU, zIIP), modelos de costeo de software complejos, y una desconexión histórica entre el equipo que opera el mainframe y el equipo de finanzas que necesita justificar su costo ante el negocio. Sin un modelo TBM defendible, es casi imposible responder "cuánto le cuesta al negocio ejecutar esta aplicación en el mainframe" en términos que un dueño de aplicación pueda entender.

## Cómo lo resuelve Apptio Costing Standard

**Cuatro casos de uso, formando una cadena Costo → Consumo → Asignación → Cobro:**
- **Mainframe Total Cost of Ownership** — consolida hardware, software, labor y servicios externos en una sola vista de costo.
- **Mainframe Consumption and Unit-Cost Analysis** — analiza consumo relativo a volúmenes de transacción de negocio para identificar workloads de alto costo unitario.
- **Mainframe Cost Allocation by Application** — asigna costo a aplicaciones usando métricas de consumo reales: **MSUs, almacenamiento asignado/usado y segundos de CPU**.
- **Mainframe Showback and Chargeback** — genera vistas transparentes de showback/chargeback para fomentar consumo responsable.

**Ocho reportes, del más agregado al más operativo:** Mainframe TCO – Cost Transparency & Allocation (vista integrada de costo + MSUs GCP/zIIP + costo unitario calculado), Mainframe TCO – Cost Pool Composition & Peer Comparison (desglose por hardware/software/labor/instalaciones/servicios externos, **con benchmarks de industria superpuestos** — el único módulo de infraestructura visto hasta ahora con comparación de industria incorporada directamente en el reporte), Mainframe Analysis (tabla flexible exportable), Mainframe Application (costo, volumen de negocio y consumo por aplicación, con clasificación de ciclo de vida Invest/Migrate/Tolerate/Eliminate), Mainframe Utilization (tendencias de consumo MSU con resaltado condicional de cambios significativos), Mainframe Showback & Chargeback (integrado con datos de IBM IntelliMagic Vision), Mainframe TCO – Utilization & Efficiency Insights (patrones, picos y capacidad subutilizada a nivel de workload), y Mainframe TCO – Model View (visualización del flujo de costo completo, de la fuente en el libro mayor hasta la aplicación de negocio).

**La fuente de datos de consumo no es genérica — requiere una herramienta de telemetría específica.** A diferencia de todos los módulos anteriores, Mainframe depende de **IBM IntelliMagic Vision** (u otras soluciones de telemetría como zPCA) como fuente primaria de datos de utilización: consumo de GCP MSU, zIIP MSU, almacenamiento asignado/usado, y métricas de consumo por workload y aplicación. Esto es un prerrequisito de infraestructura de monitoreo, no solo de datos financieros — vale la pena confirmarlo en discovery antes de prometer este módulo.

**La fórmula de ponderación de costo está documentada explícitamente — un nivel de transparencia técnica poco común.** El costo se distribuye usando una columna de "Weighting" calculada como: **MSU + (zIIP × 0.3)** — es decir, el 100% del consumo GCP MSU más el 30% del consumo zIIP. Esta fórmula es ajustable según la preferencia de ponderación de la organización, pero el valor por defecto documentado es ese. Conocer esta fórmula es valioso porque permite explicarle a un cliente escéptico exactamente cómo se calculó el costo asignado a su aplicación, en lugar de tratar el modelo como una caja negra.

**La cadena de asignación completa, documentada paso a paso:** Cost Source → Labor/Vendor/Fixed Assets/otros cost pools → IT Resource Towers → Mainframes → Applications → Business Services → Business Unit. Dentro de Mainframes específicamente: el costo fluye de IT Resource Towers y Data Centers hacia Mainframes (ponderado por la fórmula de Weighting), luego GCP MSU y zIIP MSU se asignan como "unit drivers" específicos del objeto Mainframe (con la advertencia explícita de que estos drivers deben removerse manualmente si por error quedan asignados desde otro objeto), y finalmente el costo fluye de Mainframes hacia Applications, emparejado por Application ID.

**Dos componentes con siete tablas de datos maestros.** CT Apps-Mainframes crea seis tablas (Mainframe LPARs, Mainframe Storage, Mainframes — cada una con su tabla modelo y master data), con campos requeridos específicos por tabla (Application ID/Name, LPAR, Object Identifier para LPARs; Storage ID para Storage; Actual Units para Mainframes, con CPU Capacity y Guaranteed MIPS como recomendados). BI-Mainframe Insights es el componente de analítica avanzada, disponible solo en **templates v120 y posteriores**, con prerrequisitos de versión de servidor específicos (R12.11.17 o superior).

**Prerrequisitos en cascada, incluyendo un módulo no visto en otras dependencias hasta ahora**: CTF-Cost Source, CTF-IT Towers, y **CT Apps-Applications** — este último es notable porque conecta explícitamente el módulo de Mainframe con el módulo de Applications (Solution Use Cases) como requisito, no como una integración opcional posterior.

## Por qué importa en una conversación con el cliente

El benchmark de industria incorporado directamente en el reporte Cost Pool Composition & Peer Comparison es un diferenciador competitivo real: la mayoría de las herramientas de costeo requieren un ejercicio de benchmarking separado; aquí el cliente ve de inmediato si su estructura de costo (por ejemplo, porcentaje en software vs. hardware vs. labor) está por encima o por debajo de la norma de la industria, sin trabajo adicional.

La dependencia de IBM IntelliMagic Vision es un dato de discovery crítico y temprano: si el cliente no tiene esta herramienta (u otra de telemetría de mainframe compatible) ya desplegada, hay una conversación de prerrequisito de infraestructura antes de poder activar Mainframe TCO — vale la pena preguntarlo en la primera reunión técnica, no descubrirlo después de vender el alcance.

La fórmula de weighting (MSU + zIIP×0.3) es un excelente ejemplo concreto para ilustrar el principio general de TBM de que las asignaciones de costo deben ser defendibles y explicables — mostrarle a un cliente la fórmula real, y que es ajustable, genera confianza en que el modelo no es una caja negra arbitraria.

## Documentos fuente

- Mainframe Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/mf-overview.md`
- Mainframe Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/mf-reports.md`
- Mainframe NX Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/mf-reports-nx.md`
- Mainframe Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/infra-use-cases/mf-gs.md`
- CT Apps - Mainframes component — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/mainframes.md`
- IBM Apptio Mainframe TCO Solution — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/mainframe-tco-overview.md`
- Mainframe TCO Configuration Guide — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/mainframe-config-guide.md`

*Nota: no se encontraron links públicos de ibm.com/docs embebidos en esta categoría (las referencias son a otras páginas del mismo árbol de configuración, vía rutas relativas). Hipervínculos externos pendientes según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*