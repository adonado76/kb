---
tbm_concept: "AI TCO (costeo de modelos y plataformas de IA — dos arquitecturas de origen de dato, marco de madurez Crawl-Walk-Run)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-tco-report-collection.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-tco-configguide.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-summary.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-models.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-solutions.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-business-units.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-model-views.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitcosol-over.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitcosol-rep.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitcosol-rep-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitcosol-gs.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitco-nx-report.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-platform-mapping-nx.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ai-tco-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ai-tco-configguide.md
last_updated: "2026-07-05"
---
# AI TCO — Cómo Apptio Costing Standard Aborda Esta Capacidad

## La decisión arquitectónica central: dos orígenes de dato posibles, no un modelo único

AI TCO se puede construir desde dos puntos de partida distintos, y elegir correctamente entre ellos es la primera decisión de discovery de este módulo:

**GL-driven (basado en libro mayor)** — parte del gasto financiero ya registrado en el libro mayor (licencias de plataforma, contratos con proveedores de IA, labor especializado) y lo asigna hacia modelos y soluciones de IA usando la misma lógica de asignación por torres/cost pools ya vista en el resto de Costing Standard. Es el camino más rápido de activar para una organización que ya tiene Costing Standard maduro, pero da una vista más agregada, financieramente orientada.

**Bill-driven (basado en factura de consumo)** — parte de los datos de uso y facturación reales de las plataformas de IA (tokens consumidos, llamadas de API, horas de cómputo de entrenamiento/inferencia en proveedores como OpenAI, Azure OpenAI Service, AWS Bedrock) y construye el costo desde el consumo granular hacia arriba. Da visibilidad mucho más precisa a nivel de modelo y de solución específica, pero requiere integración con las fuentes de facturación de cada plataforma de IA que la organización use.

Esta elección no es trivial ni "una o la otra para siempre" — el propio módulo se explica con un marco de madurez progresivo.

## El concepto

El gasto en IA generativa y modelos de machine learning está creciendo más rápido que la capacidad de las organizaciones de gobernarlo financieramente: se contratan múltiples plataformas (OpenAI, Anthropic, proveedores de nube), se entrenan y despliegan modelos con patrones de consumo muy distintos entre sí, y rara vez existe una vista consolidada de cuánto cuesta realmente cada modelo, cada solución de IA, o el uso que hace de ella cada unidad de negocio. Sin este módulo, el gasto en IA se ve como una línea genérica de "software" o "cloud", sin la granularidad necesaria para gestionar su crecimiento de forma responsable.

## Cómo lo resuelve Apptio Costing Standard

### Un marco de madurez explícito: Crawl, Walk, Run

El propio producto organiza la adopción de AI TCO en tres etapas de madurez creciente — la primera vez que vemos este marco explícito en la documentación de Costing Standard, aunque conceptualmente es paralelo al patrón de "Cost Overview → Insights & Optimization" ya visto repetidamente en Infrastructure Use Cases. **Crawl** corresponde típicamente al enfoque GL-driven (visibilidad financiera agregada, rápida de activar); **Walk** y **Run** incorporan progresivamente datos de consumo Bill-driven más granulares, hasta llegar a una vista completa de costo por modelo, por token, y por solución de negocio.

### Cinco reportes centrales, organizados por dimensión de análisis

**AI TCO Summary** — vista ejecutiva del gasto total en IA, comparando contra presupuesto y mostrando la distribución entre plataformas y proveedores.

**AI TCO - AI Models** — costo a nivel de modelo individual (GPT-4, Claude, modelos propios entrenados internamente), permitiendo comparar costo por modelo y su tendencia de consumo.

**AI TCO - AI Solutions** — vista a nivel de solución de negocio construida sobre uno o más modelos, conectando el costo de IA con el caso de uso que la consume — un patrón conceptual idéntico al ya visto en Applications/Services (agregación desde el componente técnico hacia la solución de negocio).

**AI TCO - Business Units** — consume la misma lógica de asignación directa/indirecta ya documentada en el brief de Business Unit, aplicada específicamente al gasto de IA — permitiendo mostrarle a cada unidad de negocio cuánto de su costo de tecnología corresponde a IA.

**AI TCO - Model Views** — reporte de trazabilidad (el equivalente de "Application Model" y "Services Model" ya vistos), mostrando cómo fluye el costo a través de las asignaciones del modelo de IA.

### Versión NX con dos reportes especializados en consumo

**AI TCO and Usage** — vista de consumo bruto (tokens, llamadas, horas de cómputo) en la interfaz New Report Studio, más orientada a equipos técnicos y de FinOps de IA que a finanzas tradicional.

**AI Platform Mapping** — mapea el catálogo de servicios y modelos de cada plataforma de IA (equivalente conceptual al mapeo de servicios de AWS/Azure ya visto en Public Cloud) hacia la taxonomía interna de Costing Standard — y, como en nube pública, es razonable esperar que este mapeo requiera actualización periódica a medida que los proveedores de IA lanzan nuevos modelos y cambian su estructura de precios.

### Componentes y configuración

La guía de configuración documenta el despliegue de AI TCO como un componente instalable dentro de Other Solutions, con prerrequisitos consistentes con el resto del portafolio (CTF-Cost Source como mínimo para el camino GL-driven), y pasos adicionales de integración de datos de facturación de plataforma para el camino Bill-driven — reflejando la misma filosofía de "empezar simple, añadir granularidad con madurez" vista en Public Cloud, Compute y Storage.

## Por qué importa en una conversación con el cliente

La elección GL-driven vs. Bill-driven es, con diferencia, la pregunta de discovery más importante de este módulo, y vale la pena hacerla explícitamente desde la primera conversación: un cliente que apenas está empezando a gobernar su gasto de IA probablemente debería activar la vía GL-driven primero (rápida, usa lo que ya tiene en el libro mayor), y migrar hacia Bill-driven cuando su consumo de plataformas de IA sea lo suficientemente grande y diverso como para justificar la integración granular por token/consumo.

El marco Crawl-Walk-Run es un excelente argumento de secuenciación de venta para un tema que a muchos clientes les genera ansiedad por su naturaleza nueva y de rápido crecimiento — permite posicionar una conversación de "empecemos con visibilidad básica este trimestre" en lugar de exigir desde el día uno una integración completa de facturación por token de cada plataforma de IA que usan.

El reporte AI TCO - Business Units es el gancho más fuerte para una conversación con el CFO: mostrar qué unidad de negocio está impulsando el crecimiento del gasto en IA generativa es exactamente el tipo de pregunta que un comité de finanzas está empezando a hacer en 2026, y pocas organizaciones tienen hoy una respuesta defendible.

## Documentos fuente

- AI TCO Report Collection (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-tco-report-collection.md`
- AI TCO Configuration Guide (reports) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-tco-configguide.md`
- AI TCO - Summary — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-summary.md`
- AI TCO - AI Models — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-models.md`
- AI TCO - AI Solutions — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-solutions.md`
- AI TCO - Business Units — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-business-units.md`
- AI TCO - Model Views — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-model-views.md`
- AI TCO Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitcosol-over.md`
- AI TCO Reports (índice) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitcosol-rep.md`
- AI TCO NX Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitcosol-rep-nx.md`
- AI TCO Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitcosol-gs.md`
- AI TCO and Usage (NX) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/aitco-nx-report.md`
- AI Platform Mapping (NX) — `02-product-docs/apptio-costing-standard/en/cost-transparency/reports/ai-platform-mapping-nx.md`
- IBM Apptio AI TCO Solution Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ai-tco-overview.md`
- AI TCO Configuration Guide (configuration) — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ai-tco-configguide.md`

*Nota: no se identificaron con certeza links públicos de ibm.com/docs embebidos verificables en el volumen de contenido revisado para esta categoría; hipervínculos externos pendientes según lo acordado.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*