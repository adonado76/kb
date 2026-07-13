---
concept: "Account Groups (agrupación de cuentas/subscripciones/proyectos en dimensiones tipo key/value, gestionable vía UI o API v3)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/spend-account-groups.md
last_updated: "2026-07-13"
---
# Setup — Organize - Account Groups — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Account Groups funcionan como un tag aplicado a nivel de cuenta de AWS, subscripción de Azure, o proyecto de GCP — en vez de etiquetar cada recurso individualmente, se asigna un valor una sola vez a nivel de cuenta y ese valor se propaga a todo el gasto que consume esa cuenta. Es el mecanismo más simple para segmentar gasto a alto nivel (ej. por ambiente o unidad de negocio) sin depender de que cada recurso tenga tags consistentes.

## Cómo lo resuelve IBM Cloudability Standard

**Modelo de datos: Account Group (la llave) + Account Group Entries (los valores).** Un Account Group llamado "Environment" tendría Account Group Entries como "Production", "Staging" o "Development", cada una asignada a cuentas/proyectos/subscripciones específicas. Cada Account Group Entry queda disponible como dimensión de reporte en toda la plataforma.

**Gestión desde la UI (página Accounts) o de forma programática vía API v3**, con paridad completa de capacidades entre ambos caminos.

**Control de permisos: solo administradores pueden crear, actualizar o eliminar Account Groups y sus Entries** — tanto desde la UI como desde la API. El resto de los usuarios puede consultar y usar como dimensión los Account Groups ya generados, pero no modificarlos.

**API v3 — estructura y comportamiento documentado con precisión:**
- Cada Account Group tiene un `id` (identificador único e inmutable asignado en creación — distinto de la `position`, que es el orden mostrado en la interfaz) y un arreglo `account_group_entry_values` con la lista informativa de valores actuales.
- Creación vía `POST /v3/account_groups`, especificando `position` (el siguiente slot libre disponible) y `name`.
- Los valores de un Account Group **no se modifican en la creación/edición del grupo mismo** — se gestionan exclusivamente a través del endpoint de Account Group Entries.
- Actualización de nombre vía `PUT` sobre el `id` del Account Group (requiere primero un `GET` para obtener ese id si no se conoce).
- **Restricción de borrado: solo se puede eliminar un Account Group cuando todas sus Account Group Entries han sido removidas primero** — un `DELETE` directo sobre un grupo con entries activas falla; el flujo correcto es `GET` para listar y obtener el id, remover las entries, y luego `DELETE` el grupo.

## Por qué importa en una conversación con el cliente

**RETOS QUE RESUELVE:** para organizaciones que necesitan segmentar gasto por ambiente o unidad de negocio pero no controlan (o no confían en) la disciplina de tagging a nivel de recurso de sus equipos de ingeniería, Account Groups ofrece un punto de control administrativo único — se asigna una vez a nivel de cuenta y se propaga automáticamente, sin depender de que cada recurso nuevo llegue correctamente etiquetado.

**VALOR DIFERENCIAL:** la separación estricta entre quién administra (solo admins) y quién consume (todos los usuarios) la dimensión resultante es un punto de gobernanza importante para clientes con equipos de FinOps centralizados que necesitan controlar la taxonomía sin bloquear el acceso de reporting a otros equipos. La regla de borrado (remover entries antes que el grupo) es un detalle operativo que vale la pena anticipar en cualquier automatización vía API para evitar llamadas fallidas en scripts de mantenimiento masivo.

## Documentos fuente

- Account Groups — `kb/02-product-docs/apptio-cloudability-standard/en/spend-account-groups.md`
- Account Groups End Point (API) — `kb/02-product-docs/apptio-cloudability-standard/en/api-account-groups-end-point.md`
- Fuente oficial: https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=api-account-groups-end-point

*Nota: versión en español/portugués se genera en una siguiente pasada.*
