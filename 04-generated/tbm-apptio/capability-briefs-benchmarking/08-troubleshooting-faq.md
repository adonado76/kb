---
tbm_concept: "Troubleshooting & FAQ (diagnóstico por síntoma de acceso/datos/valores/peer group/integración, y reglas de alcance detalladas para comparaciones like-for-like)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-benchmarking
status: draft
generated_from:
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-how-use-troubleshooting-section.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-access-navigation-issues.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-missing-incomplete-data.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-values-look-wrong-suspicious.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-peer-group-filter-problems.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-configuration-integration-issues.md
  - 02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-frequently-asked-questions.md
last_updated: "2026-07-12"
---
# Troubleshooting & FAQ — Cómo IBM Apptio Benchmarking Aborda Esta Capacidad

## El concepto

Cuando algo "se ve mal" en Benchmarking — un gráfico en blanco, un número absurdo, un peer group que un ejecutivo no acepta — la peor respuesta posible es improvisar. Esta capacidad organiza el diagnóstico por síntoma (no por causa técnica), dando en cada caso las causas probables, qué revisar, y una respuesta corta lista para adaptar en un correo o una diapositiva. También documenta, con precisión inusual, las reglas exactas de qué incluir y excluir de cada tipo de benchmark — el tipo de detalle que evita comparaciones "manzanas con naranjas" sin que nadie se dé cuenta.

## Cómo lo resuelve IBM Apptio Benchmarking

**Estructura de diagnóstico consistente en toda la sección: síntoma → causas probables → qué revisar → respuesta corta reusable.** Dirigida a TBMAs/analistas ITFM, admins, y cualquiera que tenga que explicar o defender la salida de Benchmarking. La regla de enrutamiento es simple: si la causa raíz es de configuración, se termina en Configuration Guide; si es de definiciones, se termina en Data & Methodology Reference.

**Problemas de acceso y navegación** — cuando un usuario no ve Interactive Benchmarking en la navegación, las causas típicas son: producto no aprovisionado para la compañía, rol sin acceso al endpoint, rol sin el permiso `ViewInteractiveBenchmarksAndCostData`, o usuario en el ambiente equivocado (sandbox en vez de main). Cuando un usuario puede abrir Costing pero no los reportes de Benchmarking: falta de acceso a los reportes subyacentes de Costing, el reporte fue removido/renombrado/movido, permisos a nivel de reporte más restrictivos, o los componentes de Benchmarking no fueron instalados en el proyecto de Costing.

**Datos faltantes o incompletos** — tres escenarios distintos con diagnóstico específico:
- **Gráficos completamente en blanco** — sin datos de costo/perfil para el año seleccionado, Benchmarking apuntando al año o proyecto de Costing equivocado, configuración de peer group que excluye a la organización, o dominio (Industria/OpEx/Infra) no completamente habilitado.
- **Resource Towers o Cost Pools específicos sin gasto** — costos mapeados a categorías custom no alineadas a TBM estándar, gasto en un proyecto de Costing que Benchmarking no está usando, o el dataset de benchmark no soporta esa torre para el peer group elegido.
- **Métricas de infraestructura ausentes pero OpEx sí aparece** — datos de volumen/capacidad faltantes para Resource Sub-Towers de infra, o Sub-Towers no mapeadas limpiamente a las definiciones de benchmark.

**Valores que se ven mal o sospechosos** — tres patrones específicos: valor propio órdenes de magnitud distinto de los pares (posible desajuste de unidades, error de volumen, desajuste de alcance, o año parcial — se resuelve revisando la definición de la métrica, conciliando el total de costo con Finanzas, y verificando unidades); ratio de gasto de TI muy distinto de los números internos de Finanzas (alcance de TI distinto, alcance de revenue distinto, diferencias de moneda/período, o el hecho fundamental de que Benchmarking usa definiciones alineadas a TBM mientras Finanzas usa categorías internas); y saltos inesperados de tendencia año contra año (cambios de modelo TBM, Benchmarking apuntando a un proyecto/alcance distinto ese año, cambio de perfil organizacional que alteró el peer group, o refresh del dataset que cambió la composición de pares).

**Problemas de peer group y filtros** — cuando las métricas desaparecen al aplicar filtros, la causa casi siempre es que el peer group cae bajo el tamaño mínimo de muestra requerido; la respuesta es ampliar ligeramente el peer group. Cuando un stakeholder disputa la elección del peer group, el documento da una lectura honesta: a veces la clasificación de industria/tamaño/región genuinamente no calza, pero frecuentemente la persona está reaccionando a una brecha incómoda, no a un peer group genuinamente malo — la respuesta recomendada es fijar el peer group según industria/tamaño/región primarios, probar alternativas si se solicita, pero **no cambiar de pares cada vez que un número resulta incómodo.**

**Problemas de configuración e integración** — cuando Benchmarking no refleja cambios recientes en Costing: verificar a qué proyecto de Costing apunta, cuándo fue el último refresh, y si el modelo modificado realmente alimenta el dataset de Benchmarking. Tras un cambio de versión TBM, cuando las métricas se ven inconsistentes: comparar definiciones de Resource Tower/Sub-Tower antigua vs. nueva, revisar costo no mapeado o parcialmente mapeado, y tratar el año del cambio como una nueva línea base — no como una continuación de la tendencia.

**Un extenso FAQ operativo con reglas de alcance muy específicas — el detalle que separa una implementación amateur de una rigurosa:**

- **Alcance general** — no incluir gasto fuera del control de TI ("Shadow IT"), sí incluir contratistas (excepto si son parte de BPO), excluir hardware/software específico de industria con propósito único (robots de manufactura, cajeros automáticos, dispositivos POS especializados), excluir BPO de funciones de negocio completas (nómina, beneficios), y excluir suscripciones de datos de negocio (ej. Bloomberg) — estas van al Cost Pool "Other" pero se excluyen de los benchmarks de costo de TI.
- **Cost Pools a excluir específicamente de Infrastructure Benchmarks** — Facilities and Power, Telecom, Internal Services, y Other (los cuatro no tienen métricas de infraestructura disponibles). El gasto de Telecom se asigna en su lugar a la Sub-Tower "Network – Transport" — ISG mapea **todo** el gasto de Telecom hacia ahí, y no debe incluirse en ninguna otra métrica de infraestructura.
- **Tratamiento de depreciación y amortización (D&A), distinto por tipo de benchmark** — en Industry Benchmarks (fuente Rubin) solo se incluyen desembolsos de caja (CapEx + OpEx del año fiscal actual), **sin D&A**; en IT OpEx Benchmarks (fuente Apptio) sí se incluye D&A pero **no** gasto capitalizado.
- **Costos de nube pública, también distintos por tipo de benchmark** — en Industry Benchmarks se incluyen dentro del gasto total de TI; en OpEx Benchmarks se incluyen en el Cost Pool "Outside Services"; en Infrastructure Benchmarks se **excluyen por completo** (son solo para gasto on-premise), manejado automáticamente en el modelo de costo de Apptio asignando el gasto de nube a Delivery = "Public Cloud".
- **Comparabilidad "manzanas con manzanas" por tipo de benchmark** — Industry Benchmarks ajusta por industria/región/tamaño; IT OpEx Benchmarks ajusta por arquetipos de modelo operativo (aplicaciones build-vs-buy, Cost Pools people/hardware/software/vendor); Infrastructure Benchmarks ajusta por volumen/región/industria.
- **Otros detalles operativos puntuales** — se puede benchmarkear BUs o regiones específicas poblando datos financieros y de volumen específicos de esa unidad en Interactive Benchmarking; los cambios de volumen hechos directamente en la pantalla de Infrastructure Benchmarks **no sobrescriben** los datos de Costing (son exclusivos de Interactive Benchmarking); el período extraído desde Costing usa un total corriente de 12 meses (no YTD anualizado); y el ambiente de origen de datos, si hay integración con Costing, es **siempre el de Producción**, nunca sandbox.

## Por qué importa en una conversación de cliente

El FAQ de reglas de alcance (qué incluir/excluir por Cost Pool, cómo tratar D&A, cómo tratar nube pública) es quizás el activo más valioso de toda la documentación de Benchmarking para un consultor — son exactamente las decisiones de mapeo que, si se toman mal, invalidan silenciosamente meses de comparaciones sin que nadie lo note hasta que alguien audita los números. La respuesta sugerida para disputas de peer group ("no cambiar de pares cada vez que un número resulta incómodo") es un guion de manejo de conflicto directamente aplicable en cualquier sesión ejecutiva tensa. Y la distinción de que los cambios hechos en Interactive Benchmarking nunca sobrescriben Costing es una aclaración de arquitectura importante que evita que un cliente asuma erróneamente que está editando su sistema de registro al ajustar una vista de benchmark.

## Documentos fuente

- How to use the Troubleshooting & FAQ section — `02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-how-use-troubleshooting-section.md`
- Access and navigation issues — `02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-access-navigation-issues.md`
- Missing or incomplete data — `02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-missing-incomplete-data.md`
- Values look wrong or suspicious — `02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-values-look-wrong-suspicious.md`
- Peer group and filter problems — `02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-peer-group-filter-problems.md`
- Configuration and integration issues — `02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-configuration-integration-issues.md`
- Frequently Asked Questions — `02-product-docs/tbm-apptio/apptio-benchmarking/en/faq-frequently-asked-questions.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
