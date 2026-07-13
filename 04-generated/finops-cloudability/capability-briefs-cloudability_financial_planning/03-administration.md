---
concept: "Administration (control de acceso vía Enhanced Access Administration, roles disponibles, y soporte multi-moneda)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-financial-planning
status: draft
generated_from:
  - kb/02-product-docs/apptio-financial-planning/en/administration-controlling-access.md
  - kb/02-product-docs/apptio-financial-planning/en/administration-roles-permissions.md
  - kb/02-product-docs/apptio-financial-planning/en/administration-multi-currency.md
last_updated: "2026-07-10"
---
# Administration — Cómo IBM Cloudability Financial Planning Aborda Esta Capacidad

## El concepto

Antes de que cualquier usuario pueda crear o editar un plan, un administrador tiene que otorgarle acceso explícitamente — Financial Planning no está habilitado por defecto para todos los usuarios de Cloudability. Este capítulo cubre el mecanismo de control de acceso y el soporte multi-moneda del producto.

## Cómo lo resuelve IBM Cloudability Financial Planning

**Controlling access — vía Enhanced Access Administration, el mismo mecanismo centralizado ya usado en el resto de Cloudability**, accesible desde el menú de engranaje en la barra de herramientas superior. Regla de acceso por defecto explícita: **solo usuarios con rol Cloudability Admin pueden acceder a la funcionalidad de CFP (Cloud Financial Planning) de entrada** — un Cloudability Admin debe otorgar permisos explícitamente a otros usuarios para que puedan acceder.

**Roles and Permissions — un conjunto de roles de Enhanced Access Administration específicos para controlar acceso a las funciones de CFP.** Cualquiera de estos roles otorga acceso a la funcionalidad base (acceder a la página de listado de Planes desde la navegación de Cloudability), con diferencias específicas entre ellos (el detalle granular de cada rol no está capturado en el extracto disponible, pero la estructura confirma un modelo de permisos escalonado, consistente con el patrón ya visto en Cloudability Standard).

**Multi-currency — conversión automática hacia la moneda base configurada.** Financial Planning soporta planeación en moneda local, entendida como la moneda base definida por la configuración multi-moneda general de Cloudability. El producto convierte automáticamente las monedas facturadas por cada proveedor de nube (CSP) hacia la moneda base configurada, tanto al generar forecasts como al comparar desempeño de actuals contra el plan — **todos los montos de plan (forecast y presupuesto) se expresan en la moneda base**, sin necesidad de conversión manual por parte del usuario.

## Por qué importa en una conversación con el cliente

La regla de acceso por defecto (solo Cloudability Admin) es un detalle operativo importante a comunicar en cualquier fase de onboarding — un cliente que espera que sus Planning Users tengan acceso inmediato tras la implementación necesita saber que hay un paso explícito de otorgamiento de permisos que un administrador debe ejecutar primero.

El soporte multi-moneda automático es directamente relevante para cualquier cliente multinacional — vale la pena confirmar en discovery que la configuración multi-moneda base de Cloudability ya está correctamente establecida antes de que el cliente empiece a crear planes, dado que Financial Planning hereda esa configuración en vez de tener la suya propia.

## Documentos fuente

- Controlling access — `kb/02-product-docs/apptio-financial-planning/en/administration-controlling-access.md`
- Roles and Permissions — `kb/02-product-docs/apptio-financial-planning/en/administration-roles-permissions.md`
- Multi-currency — `kb/02-product-docs/apptio-financial-planning/en/administration-multi-currency.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
