---
concept: "Administration (control de acceso vía Enhanced Access Administration, roles disponibles, y soporte multi-moneda)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - cloudability-financial-planning
status: draft
generated_from:
  - kb/02-product-docs/apptio-financial-planning/en/administration-controlling-access.md
  - kb/02-product-docs/apptio-financial-planning/en/administration-roles-permissions.md
  - kb/02-product-docs/apptio-financial-planning/en/administration-multi-currency.md
  - kb/02-product-docs/apptio-financial-planning/en/administration.md
last_updated: "2026-07-10"
last_agent_update: "2026-07-23"
---
# Administration — Cómo IBM Cloudability Financial Planning Aborda Esta Capacidad

## El concepto

Antes de que cualquier usuario pueda crear o editar un plan, un administrador tiene que otorgarle acceso explícitamente — Financial Planning no está habilitado por defecto para todos los usuarios de Cloudability. Este capítulo cubre el mecanismo de control de acceso, el soporte multi-moneda, y la configuración organizacional del producto vía Plan Preferences.

## Cómo lo resuelve IBM Cloudability Financial Planning

**Controlling access — vía Apptio Access Administration, el mismo mecanismo centralizado ya usado en el resto de Cloudability**, accesible desde el menú de engranaje (gear menu) en la barra de herramientas de Cloudability. Regla de acceso por defecto explícita: **solo los Cloudability Admins — usuarios con el rol `CloudabilityPlanningAdmin` — pueden acceder a CFP de entrada** — un Cloudability Admin debe asignar un rol CFP apropiado a los demás usuarios de Cloudability antes de que puedan llegar a la página de Plans y al resto de la funcionalidad del producto.

**Roles and Permissions — tres roles de Access Administration, con alcance nombrado explícitamente:**
- `CloudabilityPlanningAdmin` — acceso de Cloudability Admin, incluyendo acceso completo a todas las funciones y configuraciones de CFP.
- `CloudabilityPlanningUser` — acceso para ver y editar planes CFP, sujeto a los permisos específicos que el usuario tenga dentro de cada plan.
- `CloudabilityPlanningRestrictedUser` — acceso de solo lectura a los planes CFP.

**El acceso a CFP se controla en tres niveles que se aplican en cascada** — un detalle de diseño que conviene tener presente porque un solo nivel no basta para explicar qué ve un usuario:
- Los **roles de Access Administration** determinan si el usuario puede acceder a CFP y si tiene acceso de vista, edición o administración.
- Los **permisos de View de Cloudability** determinan qué planes y qué datos de plan están disponibles para ese usuario.
- Los **permisos de plan** determinan qué datos de forecast o presupuesto puede editar dentro de un plan específico.

**Multi-currency — conversión automática hacia la moneda base configurada.** Financial Planning soporta planeación en la moneda base definida por la configuración multi-moneda general de Cloudability. El producto convierte automáticamente los montos facturados por cada proveedor de nube (CSP) hacia la moneda base configurada, tanto al generar forecasts como al comparar gasto real contra los valores de forecast y presupuesto — **todos los montos de forecast y presupuesto de un plan se almacenan y se muestran en esa moneda base**, sin necesidad de conversión manual por parte del usuario. **Restricción bloqueante documentada explícitamente**: si el gasto real incluido en los planes contiene más de una moneda, es obligatorio configurar el **Multi-Currency Service (MCS)** para convertir esas monedas a una sola moneda base — **CFP no puede usarse con gasto real en múltiples monedas hasta completar esa configuración**.

**Plan Preferences — la página de configuración organizacional del producto, accesible solo para Cloudability Admins.** Sus ajustes aplican a todos los usuarios y a todos los planes de CFP, y se organizan en tres pestañas:
- **Forecasts** — lista los modelos de pronóstico soportados por Intelligent Forecasting y permite habilitarlos o deshabilitarlos individualmente. Los modelos deshabilitados quedan **excluidos cuando Intelligent Forecasting genera y evalúa estimaciones de forecast** — es decir, la exclusión afecta tanto la generación como la evaluación comparativa entre modelos, no solo lo que se muestra.
- **Cloudability Dimensions** — selecciona qué dimensiones de Cloudability aparecen como opciones **recomendadas** cuando los usuarios crean planes. Las dimensiones recomendadas se promueven en la lista de selección pero **no restringen** al usuario de elegir otras dimensiones disponibles.
- **Advanced** — habilita o deshabilita funciones opcionales de CFP. Durante el **período limitado de transición**, esta pestaña permite deshabilitar la nueva experiencia de Intelligent Forecasting y devolver temporalmente a los usuarios a la experiencia de pronóstico anterior.

## Por qué importa en una conversación con el cliente

La regla de acceso por defecto (solo Cloudability Admin) es un detalle operativo importante a comunicar en cualquier fase de onboarding — un cliente que espera que sus Planning Users tengan acceso inmediato tras la implementación necesita saber que hay un paso explícito de otorgamiento de permisos que un administrador debe ejecutar primero.

El soporte multi-moneda automático es directamente relevante para cualquier cliente multinacional, y aquí no se trata de una recomendación sino de un **prerrequisito duro**: si el gasto real que entrará a los planes tiene más de una moneda, el cliente **no puede usar CFP** hasta que el Multi-Currency Service esté configurado para consolidar todo a una sola moneda base. Es una pregunta obligatoria de discovery para cualquier cliente multinacional, y conviene hacerla antes de comprometer fechas de implementación, dado que Financial Planning hereda la configuración multi-moneda de Cloudability en vez de tener la suya propia.

Plan Preferences es la palanca que rara vez se menciona en demo pero que define cómo se comporta el producto para toda la organización: qué modelos de Intelligent Forecasting están activos, qué dimensiones se promueven a los usuarios al crear un plan, y — durante el período limitado de transición — la posibilidad de volver a la experiencia de pronóstico anterior. Ese último punto es especialmente útil como red de seguridad en conversaciones con clientes que ya operan sobre la experiencia previa y necesitan una ruta de reversa antes de comprometerse a la migración.

## Documentos fuente

- Controlling access — `kb/02-product-docs/apptio-financial-planning/en/administration-controlling-access.md`
- Roles and Permissions — `kb/02-product-docs/apptio-financial-planning/en/administration-roles-permissions.md`
- Multi-currency — `kb/02-product-docs/apptio-financial-planning/en/administration-multi-currency.md`
- Administration (página consolidada que IBM publicó en reemplazo de las tres anteriores) — `kb/02-product-docs/apptio-financial-planning/en/administration.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
