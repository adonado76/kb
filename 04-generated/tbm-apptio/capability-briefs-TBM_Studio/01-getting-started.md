---
concept: "Getting Started (posicionamiento de TBM Studio, los tres estudios integrados, seis conceptos fundacionales, y el asistente de IA Conversational Insights)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/tbm-studio.md
  - kb/02-product-docs/apptio-tbm-studio/en/started-what-is-tbm-studio.md
  - kb/02-product-docs/apptio-tbm-studio/en/started-core-concepts.md
  - kb/02-product-docs/apptio-tbm-studio/en/started-quick-start-guide.md
  - kb/02-product-docs/apptio-tbm-studio/en/started-ui-overview.md
  - kb/02-product-docs/apptio-tbm-studio/en/overview-main-navigation-areas.md
  - kb/02-product-docs/apptio-tbm-studio/en/overview-environments.md
  - kb/02-product-docs/apptio-tbm-studio/en/overview-working-documents.md
  - kb/02-product-docs/apptio-tbm-studio/en/overview-keyboard-shortcuts.md
  - kb/02-product-docs/apptio-tbm-studio/en/overview-customization-options.md
  - kb/02-product-docs/apptio-tbm-studio/en/started-conversational-insights.md
last_updated: "2026-07-07"
---
# Getting Started — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

Costing Standard, Billing y Planning son productos SaaS que consumen un modelo de costo ya construido. TBM Studio es distinto: es el **ambiente donde ese modelo se construye desde cero** — la plataforma de modelado tradicional de Apptio, con capacidad de ingesta de datos, motor de asignación, y diseño de reportes en un solo entorno integrado. Entender esta distinción de posicionamiento es el punto de partida obligatorio antes de cualquier conversación técnica sobre TBM Studio.

## Cómo lo resuelve Apptio TBM Studio

**Tres estudios integrados, cada uno resolviendo una etapa distinta del flujo dato → insight:**

- **Data Studio** — ingesta y transformación: subir archivos (Excel/CSV), transformar vía un pipeline visual de operaciones (filtrar, unir, pivotar), enriquecer con fórmulas, versionar datos mensuales, y particionar por fecha.
- **Model Studio** — el motor de asignación: agregar tablas como objetos del modelo, definir *drivers* (headcount, conteo de servidores, volumen de transacciones) que determinan cómo se distribuye el costo, crear asignaciones entre objetos, y visualizar el flujo de costo vía diagramas Sankey interactivos.
- **Report Studio** — la capa de consumo: tablas, gráficos, KPIs, slicers para exploración interactiva, drill-through de resumen a detalle, dashboards por rol, y distribución programada.

**Seis conceptos fundacionales que se repiten en toda la plataforma:**
- **Projects** — el espacio de trabajo autocontenido: cada proyecto tiene sus propias tablas, modelos, métricas y reportes interconectados.
- **Tables & Data** — dos orígenes: *source tables* (cargadas desde archivo) y *transform tables* (derivadas de otras vía operaciones), organizadas por período de tiempo.
- **Models** — objetos del modelo (Cost Source, Vendors, Technology Services, Applications, Business Units) conectados por asignaciones gobernadas por *drivers*.
- **Metrics** — *model metrics* que fluyen a través de las asignaciones (Cost, Budget, Forecast) vs. *calculated metrics*, fórmulas derivadas (varianza, YTD, costo unitario).
- **Reports** — la interfaz principal de consumo, interactiva, con permisos a nivel de reporte y seguridad a nivel de fila.
- **Environments** — el ciclo de tres ambientes (Development individual → Staging compartido y calculado → Production, promovido solo por administradores), que aparece consistentemente en cada capítulo posterior del producto.

**El Quick Start Guide es, en la práctica, la demo completa de punta a punta**: sube datos → transforma → agrega la tabla al modelo con un *unit driver* → crea una asignación básica → construye un reporte con tabla y slicer — recorriendo los tres estudios en un solo flujo de 10 minutos.

**Conversational Insights — un asistente de IA en vista previa pública, disponible actualmente para Costing y Billing.** Merece mención aparte por ser la capacidad más nueva y estratégicamente relevante de todo TBM Studio: permite hacer preguntas en lenguaje natural sobre el modelo de costo o los reportes, con un modelo de acceso de tres niveles (Admin, Power User, End User) que preserva la segregación de datos ya configurada vía reportes. Incluye conciencia de contexto de sesión (producto, proyecto, rango de fechas activos), modo silencioso vs. verboso (con trazabilidad de "cómo llegué a esta respuesta"), historial de conversación persistente, y — el detalle más interesante para consultoría — **Skills**: plantillas de salida reutilizables y personalizables en markdown que los administradores pueden crear para estandarizar cómo el asistente responde a preguntas recurrentes del negocio.

## Por qué importa en una conversación con el cliente

El posicionamiento correcto de TBM Studio frente al resto del portafolio (Costing Standard, Billing, Planning) es la aclaración más importante a hacer temprano: estos productos SaaS *consumen* un modelo, mientras TBM Studio es donde ese modelo *se construye* — un cliente que ya tiene Costing Standard funcionando probablemente tiene TBM Studio (o su predecesor) operando detrás, aunque nunca lo haya visto directamente.

El ciclo de tres ambientes (Dev/Staging/Production) es la misma disciplina de gobernanza de cambios ya vista en Costing Standard y Billing — vale la pena señalar esta consistencia arquitectónica, ya que confirma que el portafolio completo de Apptio comparte una filosofía común de control de cambios.

Conversational Insights es el gancho de conversación más fuerte para cualquier cliente que ya esté explorando IA generativa en su organización — vale la pena posicionarlo explícitamente como una capacidad emergente en vista previa, no como una funcionalidad estable de producción, y aclarar que hoy solo aplica a Costing y Billing.

## Documentos fuente

- TBM Studio (índice general del producto) — `kb/02-product-docs/apptio-tbm-studio/en/tbm-studio.md`
- What is TBM Studio? — `kb/02-product-docs/apptio-tbm-studio/en/started-what-is-tbm-studio.md`
- Core Concepts — `kb/02-product-docs/apptio-tbm-studio/en/started-core-concepts.md`
- Quick Start Guide — `kb/02-product-docs/apptio-tbm-studio/en/started-quick-start-guide.md`
- UI Overview — `kb/02-product-docs/apptio-tbm-studio/en/started-ui-overview.md`
- Main Navigation Areas — `kb/02-product-docs/apptio-tbm-studio/en/overview-main-navigation-areas.md`
- Environments — `kb/02-product-docs/apptio-tbm-studio/en/overview-environments.md`
- Working with Documents — `kb/02-product-docs/apptio-tbm-studio/en/overview-working-documents.md`
- Keyboard Shortcuts — `kb/02-product-docs/apptio-tbm-studio/en/overview-keyboard-shortcuts.md`
- Customization Options — `kb/02-product-docs/apptio-tbm-studio/en/overview-customization-options.md`
- Conversational Insights — `kb/02-product-docs/apptio-tbm-studio/en/started-conversational-insights.md`

*Nota: versión en español/portugués se genera en una siguiente pasada. Hipervínculos a documentación oficial de IBM pendientes de verificación individual.*
