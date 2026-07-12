---
tbm_concept: "Administration (credenciales de vendor, roles y permisos, usuarios/grupos con sincronización Entra ID, Views jerárquicas, y multi-moneda)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/administration-vendor-credentials.md
  - kb/02-product-docs/apptio-cloudability-standard/en/credentials-vendor-email-alerts-banners.md
  - kb/02-product-docs/apptio-cloudability-standard/en/credentials-manage-vendor-in-cloudability.md
  - kb/02-product-docs/apptio-cloudability-standard/en/administration-roles-permissions-in-cloudability.md
  - kb/02-product-docs/apptio-cloudability-standard/en/administration-manage-users-user-groups.md
  - kb/02-product-docs/apptio-cloudability-standard/en/groups-manage-users-user-views-dashboards.md
  - kb/02-product-docs/apptio-cloudability-standard/en/groups-manage-user.md
  - kb/02-product-docs/apptio-cloudability-standard/en/groups-manage-entra-id.md
  - kb/02-product-docs/apptio-cloudability-standard/en/groups-users-user-faqs.md
  - kb/02-product-docs/apptio-cloudability-standard/en/administration-create-manage-views.md
  - kb/02-product-docs/apptio-cloudability-standard/en/views-organize-using-hierarchical.md
  - kb/02-product-docs/apptio-cloudability-standard/en/views-feature-compatibility.md
  - kb/02-product-docs/apptio-cloudability-standard/en/administration-multi-currency-service-in-cloudability.md
last_updated: "2026-07-09"
---
# Administration — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Con los datos ya conectados (Capítulos 2-3) y la taxonomía de negocio ya definida (Capítulo 4), este capítulo cubre quién puede ver y hacer qué dentro de Cloudability — credenciales de proveedor, roles, usuarios y grupos, y el mecanismo de filtrado de datos más central del producto: las Views.

## Cómo lo resuelve IBM Cloudability Standard

**Vendor Credentials — el panel de control operativo de todas las conexiones ya establecidas en los Capítulos 2-3.** Permite a los administradores ver, actualizar o eliminar cuentas individuales bajo cada fuente de datos, buscar y filtrar cuentas, y ver el nivel de permiso de cada una. Incluye gestión de **alertas por correo y banners** cuando una credencial de vendor tiene problemas — visibilidad proactiva de fallas de conexión antes de que se conviertan en un hueco de datos silencioso.

**Roles and Permissions** — el modelo de control de acceso base, complementario a la gestión específica de usuarios y vistas cubierta en el resto del capítulo.

**Users & User Groups — con tres formas de gestionar el acceso.** Gestión individual de usuario (vista y dashboard por defecto, acceso a vistas específicas), **User Groups** (colecciones lógicas de usuarios para simplificar la asignación consistente de Views a escala — con protección explícita: el sistema **bloquea la eliminación** de un grupo si está siendo usado en alguna asignación de View, mostrando una lista de solo lectura de dónde se usa), y **sincronización con Microsoft Entra ID Groups** — en vez de crear y mantener grupos manualmente, se importan/sincronizan grupos ya existentes del tenant de Entra ID, con **auto-sync configurable** (diario, semanal o mensual, con criterios de filtro específicos) para que los cambios de membresía en Entra ID se reflejen automáticamente sin intervención manual. Detalle operativo importante: si un grupo se elimina del lado de Entra ID, **no se elimina automáticamente en Cloudability** — requiere eliminación manual.

**Views — el mecanismo de filtrado de datos más importante del producto, con lógica de comportamiento documentada con precisión.** Una View es un filtro de aplicación completa que acota qué datos ve un usuario. Funcionalidad destacada: **Duplicate View** (clonar una vista existente con todos sus filtros, permisos y configuración en un clic, evitando recrear manualmente vistas similares), y **Show Default Usage** (antes de eliminar o restringir una vista, un admin puede ver exactamente qué usuarios la tienen configurada como su vista por defecto — compartida directamente, vía User Groups, vía Entra ID Groups, o con toda la organización — evitando romper el acceso de alguien sin saberlo).

**Comportamiento de eliminación y cambio de permisos, documentado explícitamente**: si se elimina una vista (incluyendo una Vista Jerárquica) que era la default de un usuario, su default revierte automáticamente a la vista default a nivel de organización; si no existe una default de organización, queda en blanco. La misma lógica de reversión aplica cuando se reducen permisos de una vista compartida.

**Hierarchical Views (HV) — Views organizadas en estructura padre-hijo anidada**, donde una View puede contener Views hijas, que a su vez pueden tener sus propias hijas — el mismo patrón conceptual de jerarquía ya visto en Hierarchical Business Mappings (Capítulo 4), aplicado ahora a la capa de filtrado de datos en lugar de a la taxonomía de negocio.

**Multi-Currency Service** — normalización de moneda a través de todos los proveedores y contratos de facturación, el mismo principio ya documentado en Costing Standard y Billing, aquí aplicado específicamente al consumo de nube multi-proveedor.

## Por qué importa en una conversación con el cliente

La sincronización automática con Entra ID Groups es un argumento de eficiencia operativa fuerte para cualquier cliente que ya gestiona su directorio corporativo en Microsoft Entra ID — evita el trabajo manual recurrente de mantener grupos duplicados, y la nota de que la eliminación no es automática en ambos sentidos es un detalle de gobernanza a comunicar proactivamente a cualquier administrador.

Show Default Usage es una funcionalidad de gobernanza de bajo perfil pero alto impacto práctico — vale la pena mencionarla explícitamente en cualquier conversación sobre limpieza o reorganización de Views, dado que evita el escenario común de "eliminé una vista y ahora alguien no puede ver sus datos sin saber por qué".

Las Hierarchical Views son el argumento correcto para clientes con estructuras organizacionales profundas (múltiples niveles de unidad de negocio) que necesitan que el filtrado de datos refleje esa jerarquía real, no solo una lista plana de vistas independientes.

## Documentos fuente

- Vendor Credentials — `kb/02-product-docs/apptio-cloudability-standard/en/administration-vendor-credentials.md`
- Vendor Email Alerts & Banners — `kb/02-product-docs/apptio-cloudability-standard/en/credentials-vendor-email-alerts-banners.md`
- Manage Vendor in Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/credentials-manage-vendor-in-cloudability.md`
- Roles and Permissions in Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/administration-roles-permissions-in-cloudability.md`
- Manage Users & User Groups — `kb/02-product-docs/apptio-cloudability-standard/en/administration-manage-users-user-groups.md`
- Manage Users' Views and Dashboards — `kb/02-product-docs/apptio-cloudability-standard/en/groups-manage-users-user-views-dashboards.md`
- Manage User — `kb/02-product-docs/apptio-cloudability-standard/en/groups-manage-user.md`
- Manage Entra ID Groups — `kb/02-product-docs/apptio-cloudability-standard/en/groups-manage-entra-id.md`
- Users & Groups FAQs — `kb/02-product-docs/apptio-cloudability-standard/en/groups-users-user-faqs.md`
- Create and Manage Views — `kb/02-product-docs/apptio-cloudability-standard/en/administration-create-manage-views.md`
- Organize Using Hierarchical Views — `kb/02-product-docs/apptio-cloudability-standard/en/views-organize-using-hierarchical.md`
- Views Feature Compatibility — `kb/02-product-docs/apptio-cloudability-standard/en/views-feature-compatibility.md`
- Multi-Currency Service in Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/administration-multi-currency-service-in-cloudability.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
