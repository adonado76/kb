---
tbm_concept: "Getting Started (posicionamiento del producto, mapa completo de capacidades por sección de menú, acceso vía Apex, y rutas de primeros pasos diferenciadas por rol)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/started-what-you-can-do-cloudability-standard.md
  - kb/02-product-docs/apptio-cloudability-standard/en/started-how-request-new-updated-ssocertificate.md
  - kb/02-product-docs/apptio-cloudability-standard/en/started-how-access-cloudability.md
  - kb/02-product-docs/apptio-cloudability-standard/en/started-find-your-way-around-cloudability.md
  - kb/02-product-docs/apptio-cloudability-standard/en/started-first-steps-cloudability-users.md
  - kb/02-product-docs/apptio-cloudability-standard/en/started-first-steps-cloudability-admin.md
last_updated: "2026-07-09"
---
# Getting Started — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Cloudability es, de los cinco productos del portafolio Apptio documentados en este proyecto, el más orientado a la **capa de datos de consumo de nube en sí misma** — no construye el modelo de costeo TBM completo (eso lo hace TBM Studio/Costing Standard), sino que se especializa en traducir facturas y etiquetas de proveedores de nube en insights accionables de optimización, gobernanza y planeación. Este capítulo establece el vocabulario y el mapa de navegación completo antes de entrar a cada capacidad en detalle.

## Cómo lo resuelve IBM Cloudability Standard

**Definición de producto, en la propia introducción**: "IBM Cloudability optimiza recursos de nube y traduce facturas y etiquetas en insights para dar claridad y responsabilidad en tiempo real sobre el consumo." La condición previa explícita para cualquier otra capacidad: conectar con los proveedores de nube para configurar la ingesta de datos — sin eso, no hay nada que explorar u optimizar.

**Un mapa de seis áreas funcionales, que se convierten en las secciones del menú principal y en los capítulos siguientes de este documento:**

- **Dashboards y Reports** — herramientas de autoservicio: Dashboards personalizables con widgets, y Reports para responder preguntas ad hoc, programar envíos, o exportar datos crudos con reportes preconfigurados o construidos desde cero.
- **Insights** — TrueCost Explorer (estructura de las facturas de nube), Containers (costo de Kubernetes/OpenShift), Tag Explorer (qué etiquetas usa realmente la organización), Anomaly Detection (picos de gasto inesperados, con alertas por correo o PagerDuty), y Scorecards (benchmarking contra pares de industria y entre unidades de negocio propias).
- **Optimize** — Commitment Portfolio, Commitment Recommendations y Commitment Manager (gestión de instrumentos de compromiso como Reserved Instances y Savings Plans), Rightsizing y Rightsizing ROI (dimensionar correctamente la infraestructura y rastrear el impacto de esas recomendaciones), y Turbonomic (integración con la plataforma de optimización ya documentada en TBM Studio).
- **Governance** — políticas FinOps aplicadas directamente en los flujos de trabajo de desarrollo, de forma proactiva.
- **Plan** — Budgets and Forecasting (pronósticos basados en patrones históricos, presupuestos con notificaciones), y Workload Planning (precisión de planeación financiera a través de proveedores de nube).
- **Organize** — Cost Sharing y Telemetry-Based Allocations (distribuir costos compartidos usando métricas de uso real), Tags and Labels, Account Groups, Business Mappings (taxonomía propia de la organización), Views (filtros de aplicación completa), y Data Reprocess (refresco retrospectivo de datos históricos cuando cambia la estrategia de negocio).

**Acceso vía Apex — el mismo patrón de acceso unificado ya documentado en Costing Standard, Billing y TBM Studio.** Navegación por panel izquierdo colapsable, cambio rápido entre productos vía el selector de aplicaciones, y ayuda contextual — sin cambios funcionales dentro de cada producto, solo en la capa de navegación.

**Navegación real de Cloudability, con menú adaptado por rol**: Home (dashboard y reportes propios), Insights, Optimize, Plan, Organize, y Settings (credenciales de proveedor, gestión de usuarios, preferencias de Rightsizing y Commitment, DataLink) — cada sección visible según el rol del usuario, no un menú único para todos.

**Dos rutas de primeros pasos, diferenciadas explícitamente por rol:**
- **Primeros pasos para usuarios** — personalizar dashboards/reportes, y explorar Insights (Containers, Commitments basados en gasto, Anomaly Detection, sostenibilidad de nube), TrueCost Explorer, y Tag Explorer.
- **Primeros pasos para administradores** — ocho pasos de configuración: cuentas de usuario, roles y permisos, credenciales de vendor (conexión a fuentes de datos), Tag Mappings, Account Groups, creación de Views, configuración de tipo de cambio multi-moneda, y Business Mappings.

**Solicitud de SSO/certificado** — un procedimiento operativo específico y detallado (requisitos SAML 2.0, atributos obligatorios `mail` y `fullname`, límites documentados como que Apptio no gestiona MFA por el cliente) para integrar el proveedor de identidad de la organización, incluyendo el detalle técnico de que las capacidades de email de Billing Standard/IT Finance variance report requieren específicamente flujo SP-initiated habilitado.

## Por qué importa en una conversación con el cliente

El mapa de seis áreas es el mejor recurso para la primera reunión de discovery: permite ubicar rápidamente en qué área cae el dolor principal del cliente (¿es un problema de visibilidad — Insights —, de ahorro específico — Optimize —, o de gobernanza proactiva — Governance?) y de ahí navegar la conversación hacia la capacidad concreta.

Las dos rutas de primeros pasos (usuario vs. administrador) son directamente reutilizables como plan de habilitación diferenciado — el mismo principio de capacitación por rol ya visto en TBM Studio y Billing, aplicado aquí desde el arranque del producto.

El requisito de SP-initiated flow para las capacidades de email de variance report es un detalle técnico de integración que vale la pena confirmar explícitamente en cualquier discovery de SSO donde el cliente también use Billing Standard — pasarlo por alto genera un descubrimiento tardío y costoso durante la configuración de notificaciones automáticas.

## Documentos fuente

- What you can do with Cloudability Standard — `kb/02-product-docs/apptio-cloudability-standard/en/started-what-you-can-do-cloudability-standard.md`
- How to Request a New Or Updated SSO/Certificate — `kb/02-product-docs/apptio-cloudability-standard/en/started-how-request-new-updated-ssocertificate.md`
- How to access Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/started-how-access-cloudability.md`
- Find your way around Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/started-find-your-way-around-cloudability.md`
- First steps for Cloudability users — `kb/02-product-docs/apptio-cloudability-standard/en/started-first-steps-cloudability-users.md`
- First steps for Cloudability admin — `kb/02-product-docs/apptio-cloudability-standard/en/started-first-steps-cloudability-admin.md`

*Nota: versión en español/portugués se genera en una siguiente pasada. Hipervínculos a documentación oficial de IBM pendientes de verificación individual.*
