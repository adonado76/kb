---
concept: "Data & Methodology Reference (fuentes de datos, cobertura y límites, normalización, métodos estadísticos de peer group, arquetipos, guías de interpretación, y FAQ de metodología)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-benchmarking
status: draft
generated_from:
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/reference-benchmark-data-sources.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/reference-coverage-limits.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/reference-normalization-mapping.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/reference-peer-group-statistical-methods.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/reference-interpretation-guidelines-caveats.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/reference-frequently-asked-questions-about-methodology.md
last_updated: "2026-07-12"
---
# Data & Methodology Reference — Cómo IBM Apptio Benchmarking Aborda Esta Capacidad

## El concepto

Los reportes de Benchmarking son tan confiables como la metodología que los sostiene — y esa metodología es exactamente lo que un cliente escéptico va a cuestionar primero. Esta capacidad documenta el "cómo se cocina" detrás de cada benchmark: de dónde vienen los datos, dónde son fuertes y dónde son débiles, cómo se normalizan para ser comparables, qué significan estadísticamente percentiles y arquetipos, y las reglas explícitas para distinguir una comparación válida de una engañosa.

## Cómo lo resuelve IBM Apptio Benchmarking

**Tres fuentes de datos, cada una con su propia naturaleza y cadencia de actualización:**

- **Benchmarks de industria** — de proveedores de mercado e investigación que recolectan datos de gasto y staffing de TI a través de muchas organizaciones; basados en presentaciones de año fiscal completo, normalizados a sectores estándar y bandas de tamaño, refrescados anual o periódicamente (no mensualmente).
- **Benchmarks de OpEx de la comunidad Apptio** — datos de clientes anonimizados y agregados, de forma opt-in, alineados a Cost Pools y Resource Towers TBM; los contribuyentes individuales son anónimos y las métricas solo se exponen por encima de umbrales mínimos de muestra.
- **Benchmarks de costo y eficiencia de infraestructura** — de programas de benchmarking de infraestructura a gran escala, basados en presentaciones detalladas de costo y volumen por Resource Tower/Sub-Tower, con definiciones estándar alineadas a TBM y frecuentemente incluyendo múltiples años para chequeo de tendencia y estabilidad.

**Cobertura y límites — dónde los benchmarks son fuertes y dónde son delgados, un mapa honesto de expectativas.** Por industria: fuerte en servicios financieros, manufactura, retail, salud, sector público, tecnología y medios; industrias nicho o muy especializadas pueden tener muestras limitadas, y organizaciones diversificadas pueden caer en un cubo genérico de "diversificado". Por tamaño: segmentado principalmente por bandas de revenue anual (a veces headcount como vista secundaria); empresas de crecimiento o contracción muy rápida pueden cambiar de banda entre ciclos de recolección, y holdings/grupos pueden distorsionar resultados si el alcance de TI y el alcance financiero no coinciden. Por geografía: comparaciones globales o agrupaciones regionales (NA, EMEA, APAC); las diferencias de costo laboral regional pueden ser significativas, y los modelos de entrega multinacionales pueden difuminar las distinciones geográficas. Por tiempo: siempre hay un rezago entre el cierre de un año calendario y el procesamiento completo de benchmarks — son fotografías de cómo se veían los participantes ese año, no se actualizan mes a mes.

**Normalización y mapeo — donde el modelo del cliente gana o pierde credibilidad.** Todo debe mapearse a la misma estructura estándar (Cost Pools, Resource Towers/Sub-Towers): cuentas del mayor general, datos de vendors y otras fuentes hacia los mismos Cost Pools, y costos hacia las torres/sub-torres que corresponden a las definiciones de benchmark. Riesgos comunes de mapeo: Resource Towers custom, Cost Pools custom, y categorías mixtas que combinan varios pools estándar. Qué se incluye típicamente en el alcance: labor y contratistas de funciones de TI, hardware/software/servicios cloud, servicios de vendors que soportan TI, y depreciación/amortización de activos tecnológicos. Qué típicamente se excluye: business process outsourcing donde TI no es el driver principal, overhead corporativo no-TI no asignado, y cargos extraordinarios de una sola vez (si el proveedor los excluye). Reglas de moneda: usar una sola moneda de trabajo, asegurar que costo de TI y revenue usen la misma moneda para el período, y hacer la conversión aguas arriba (en Costing o antes de la carga manual), documentando tasas y momento usado. Regla de alineación temporal: el patrón limpio es año fiscal N de actuales vs. benchmark del año fiscal N — no comparar un forecast del año actual contra un benchmark que refleja actuales del año pasado, a menos que se haga deliberadamente y se declare explícitamente.

**Construcción de peer group y métodos estadísticos — los benchmarks muestran distribuciones, no organizaciones individuales.** El peer group se construye por industria, banda de tamaño (usualmente revenue) y región/geografía, con reglas de integridad estadística: tamaños mínimos de muestra antes de reportar una métrica, exclusión o recorte de outliers extremos en algunos datasets, y anonimización que impide identificar contribuyentes individuales. Los percentiles/cuartiles documentados: mediana (percentil 50), cuartil inferior (25), cuartil superior (75), y mínimo/máximo (a veces con outliers recortados). Regla de lectura: cerca de la mediana es típico, dentro de la banda intercuartil es un rango normal, fuera de la banda hay una diferencia estructural que amerita entender por qué.

**Arquetipos — patrones derivados agrupando organizaciones por su estructura de gasto, útiles para explicar por qué alguien difiere de la mediana sin que sea "un problema":**

- **Hardware Technology-centric** — modelo operativo apoyado fuertemente en infraestructura propia o directamente gestionada; mayor huella on-prem/colocation, más gasto en plataformas de infraestructura, operaciones más gestionadas internamente.
- **Software Technology-centric** — modelo apoyado en plataformas de software, herramientas y licencias más que en hardware propio; mayor uso de SaaS, suscripciones de plataforma, automatización; infraestructura abstraída (cloud/gestionada); más gasto en seguridad, observabilidad, ITSM, plataformas de desarrollador y apps empresariales.
- **Vendor-centric** — gran parte del trabajo lo hacen terceros (managed services, integradores de sistemas, outsourcing, contratistas); equipos internos enfocados en gobierno, arquitectura y gestión de vendors.
- **People-centric** — la capacidad se entrega principalmente con empleados internos; equipos de ingeniería/operaciones más grandes; fuerte propiedad interna de entrega y operación.

El uso práctico de los arquetipos es doble: entender a qué patrón se parece la organización propia, y explicar por qué se ve diferente de la mediana porque intencionalmente sigue un arquetipo distinto — un argumento defensivo poderoso cuando un ejecutivo objeta "por qué no nos parecemos al promedio".

**Guías de interpretación — la sección que previene malas decisiones.** Comparaciones válidas: pares que comparten industria, banda de tamaño y región; torres en alcance y mapeadas consistentemente; costos unitarios donde tanto costo como definición de volumen coinciden. Comparaciones inválidas: cruzar industrias con modelos de negocio radicalmente distintos, comparar un alcance parcial de TI contra benchmarks de alcance completo, o mezclar tratamientos contables distintos sin ajuste. Desajustes de alcance comunes documentados: algunas organizaciones incluyen telecom y tecnología operacional dentro de TI, otras no; los shared services a veces están completamente asignados a TI y otras veces quedan en overhead corporativo; los costos de cloud/SaaS a veces están centralizados en TI y otras veces distribuidos. La regla es siempre la misma: **primero verificar alcance y mapeo, solo después etiquetar como diferencia de desempeño.** Diferencias estructurales pueden reflejar ineficiencia real, decisiones estratégicas deliberadas (mayor nivel de servicio, más resiliencia), decisiones de sourcing distintas, o huella legacy/deuda técnica — el benchmark señala la diferencia, pero no dice automáticamente cuál de estas cuatro explicaciones es la correcta.

**Seis preguntas frecuentes de metodología, con respuestas "de bolsillo" listas para adaptar:**

- *¿Qué tan precisos son estos benchmarks?* — consistentes y estadísticamente fundamentados, no precisos al centavo; sirven para ver si se está bajo, típico o alto, y luego confirmar con datos propios antes de decisiones grandes.
- *¿Podemos ver quiénes son nuestros pares?* — no, los datos están anonimizados; solo se ve la distribución y estadísticas.
- *¿Se remueven outliers?* — la mayoría de datasets aplica manejo sensato de outliers y siempre requiere conteos mínimos de pares.
- *¿Por qué desaparece una métrica al cambiar filtros?* — porque el peer group filtrado cae bajo el tamaño mínimo de muestra; ampliar el peer group usualmente la trae de vuelta.
- *¿Por qué esta métrica no coincide con lo que reporta Finanzas?* — Finanzas puede usar una definición o alcance distinto; los benchmarks usan definiciones TBM estándar para ser comparables entre organizaciones — hay que reconciliar alcance y definiciones primero, y luego decidir qué vista usar para qué propósito.
- *¿Podemos cambiar cómo se calcula una métrica de benchmark?* — no, las definiciones están estandarizadas para que todos comparen lo mismo; se pueden crear métricas internas custom en Costing, pero son independientes de los benchmarks externos.

## Por qué importa en una conversación de cliente

Esta es la sección de "defensa metodológica" — el material que un TBMA necesita tener internalizado para responder con autoridad cuando un ejecutivo pregunta "¿pero esto realmente nos compara con nosotros?". Los arquetipos son particularmente valiosos como herramienta narrativa: convierten una desviación de la mediana de una señal de alarma en una confirmación de estrategia deliberada, siempre que la organización efectivamente siga ese patrón de forma consciente. Las seis preguntas frecuentes de metodología son, literalmente, un guion de preparación para la primera sesión donde se presenten resultados de benchmark a la alta gerencia — vale la pena que cualquier consultor las tenga memorizadas antes de esa reunión.

## Documentos fuente

- Benchmark data sources — `02-product-docs/tbm-apptio/apptio-benchmarking/en/reference-benchmark-data-sources.md`
- Coverage and limits — `02-product-docs/tbm-apptio/apptio-benchmarking/en/reference-coverage-limits.md`
- Normalization and mapping — `02-product-docs/tbm-apptio/apptio-benchmarking/en/reference-normalization-mapping.md`
- Peer group and statistical methods — `02-product-docs/tbm-apptio/apptio-benchmarking/en/reference-peer-group-statistical-methods.md`
- Interpretation guidelines and caveats — `02-product-docs/tbm-apptio/apptio-benchmarking/en/reference-interpretation-guidelines-caveats.md`
- Frequently asked questions about methodology — `02-product-docs/tbm-apptio/apptio-benchmarking/en/reference-frequently-asked-questions-about-methodology.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
