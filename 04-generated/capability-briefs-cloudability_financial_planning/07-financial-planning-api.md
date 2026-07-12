---
tbm_concept: "Cloudability Financial Planning API (autenticación, endpoints de Plan/Dimension/Budget/Import-Export/Alerts/User, y la distinción crítica entre identidades CFP y Cloudability)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-financial-planning
status: draft
generated_from:
  - kb/02-product-docs/apptio-financial-planning/en/api-getting-started-cloudability-financial-planning.md
  - kb/02-product-docs/apptio-financial-planning/en/api-plan-endpoints.md
  - kb/02-product-docs/apptio-financial-planning/en/api-dimension-endpoints.md
  - kb/02-product-docs/apptio-financial-planning/en/api-budget-endpoints.md
  - kb/02-product-docs/apptio-financial-planning/en/api-importexport-endpoints.md
  - kb/02-product-docs/apptio-financial-planning/en/api-alerts-endpoints.md
  - kb/02-product-docs/apptio-financial-planning/en/api-user-endpoints.md
last_updated: "2026-07-10"
---
# Cloudability Financial Planning API — Cómo IBM Cloudability Financial Planning Aborda Esta Capacidad

## El concepto

Todo lo documentado en Working with Plans tiene su contraparte programática completa — la API v3 de Financial Planning cubre creación/gestión de planes, dimensiones, presupuestos, alertas, e importación/exportación masiva, habilitando automatización completa del ciclo de planeación sin depender de la interfaz de usuario.

## Cómo lo resuelve IBM Cloudability Financial Planning

**Autenticación — vía Frontdoor apptio-opentoken exclusivamente.** A diferencia de otras APIs de Cloudability, **las API Keys de Cloudability no están soportadas** para Financial Planning — un detalle crítico de compatibilidad a verificar antes de cualquier integración. Los permisos de interacción API (crear, actualizar, leer, eliminar) corresponden a los permisos de usuario de Financial Planning ya vistos en Administration. Endpoints regionales específicos para clientes EU (`api-eu.cloudability.com`) y APAC (`api-au.cloudability.com`) — cualquier referencia genérica a `api.cloudability.com` en la documentación debe sustituirse por el endpoint regional correspondiente.

**Plan Endpoints — el CRUD central.** Get Plan Options (valores soportados para duración, tipos de gasto excluible, métricas de costo — la fuente de verdad para construir cualquier solicitud de creación válida), Create a Plan (con el objeto `calculateBaselineRequest` anidado, configurando meses de historia, si usar actuals del año anterior, métrica de costo, y gastos excluidos), Get/Get All/Delete Plan.

**Dimension Endpoints — gestión completa del ciclo de vida de dimensión.** Get Dimensions (filtrable por tipo Plan o Cloudability), Create a Plan Dimension (solo crea dimensiones tipo Plan — cuatro tipos de dato soportados: Text, Numeric, Data, List), Add Dimension to a Plan (asocia dimensiones ya existentes, no crea nuevas), Export Plan Dimension Values a CSV, **dos endpoints distintos para actualizar valores de lista** — uno actualiza solo la instancia usada dentro de un plan específico, otro actualiza la definición global (afectando la disponibilidad futura, no las instancias ya en uso), Make a Cloudability Dimension Recommended (la implementación API de "Setting up Recommended Dimensions"), y Delete a Dimension (con comportamiento distinto según tipo: una dimensión Cloudability se remueve solo del conjunto recomendado; una dimensión Plan se remueve de todos los planes asociados, **con pérdida de sus valores**).

**Budget Endpoints — lectura y edición granular por período.** El objeto Budget expone montos tanto en `budgets_as_flat_amounts` (valores absolutos por período/trimestre/año, con claves `pN`/`qN`/`fyN`) como opcionalmente en `budgets_as_percentages` (mismo esquema de claves, como fracción del plan). Editar un presupuesto (`PATCH`) apunta a un nodo específico vía `fiscalPeriod` (ej. `budgets_as_flat_amounts.fy0`), con el mismo comportamiento de distribución equitativa ya visto en la interfaz al editar a nivel de período resumen.

**Import/Export Endpoints — el mecanismo de carga masiva.** Export soporta dos targets (`FORECAST`, `BUDGET_TARGET`) con configuración de encoding y delimitador de CSV. Import es **asíncrono** (retorna un job con estado Pending/Running/Success/Error, consultable por ID), y actualmente **solo soporta el modo REPLACE** (el parámetro `type` de modo de importación existe pero es ignorado por el servicio). Recomendación explícita documentada: exportar primero el Forecast o Budget vía la interfaz para usar como plantilla exacta del esquema CSV requerido antes de construir un import.

**Alerts Endpoints — cuatro tipos de verificación, con lógica de evaluación documentada explícitamente.** `EXCEEDS_FORECAST`, `EXPECTED_TO_EXCEED_FORECAST`, `EXCEEDS_BUDGET`, `EXPECTED_TO_EXCEED_BUDGET` — cada uno evaluado contra un umbral porcentual (`alertThresholdValue`) sobre un período (`MTD`/`QTD`/`YTD`). Los `filterConditions` combinan múltiples dimensiones con lógica **AND entre condiciones, OR entre valores dentro de una condición** — permitiendo alcance preciso (ej. Cuenta = A o B, Y Ambiente = producción). `isTriggered` se recalcula en la cadencia de evaluación de la plataforma, y no se dispara si el filtro no coincide con ningún dato.

**User Endpoints — la distinción técnica más importante de toda esta categoría API: existen dos sistemas de identidad de usuario paralelos, no intercambiables.**
- **CFP user** — identificado por UUID (string), usado donde la API espera identidades de Financial Planning (ej. `subscribedUsers` en Alerts). Se obtiene vía `GET /v3/planning/whoami` o `GET /v3/planning/users`.
- **Cloudability user** — identificado por entero, usado donde la API espera identidades generales de Cloudability (ej. el campo `userId` en query/body de Plan Endpoints). Se obtiene vía `GET /v3/users` (API core de Cloudability, **con nombres de encabezado distintos**: `apptio-environmentid`/`apptio-opentoken` en vez de `Apptio-Current-Environment`/`Apptio-Opentoken` usados en el resto de endpoints de CFP).

## Por qué importa en una conversación con el cliente

La incompatibilidad de autenticación (solo Frontdoor apptio-opentoken, sin soporte de API Keys de Cloudability) es una verificación de discovery técnico obligatoria antes de cualquier propuesta de integración — un cliente que ya tiene una integración de API Keys con el resto de Cloudability necesitará un mecanismo de autenticación separado específicamente para Financial Planning.

La distinción entre CFP user (UUID) y Cloudability user (entero) es, posiblemente, la fuente de error de integración más probable para cualquier desarrollador nuevo en esta API — vale la pena entregar esta tabla de referencia explícitamente a cualquier equipo de desarrollo del cliente antes de que empiecen a escribir código, ya que confundir estos dos sistemas de ID produce errores silenciosos o de autorización difíciles de diagnosticar.

El hecho de que Import solo soporte el modo REPLACE (no MERGE, a pesar de que el parámetro existe) es un detalle de comportamiento real del sistema que vale la pena confirmar directamente antes de diseñar cualquier flujo de actualización incremental automatizado — un cliente que asuma soporte de fusión incremental basándose solo en el nombre del parámetro se llevará una sorpresa.

## Documentos fuente

- Getting Started with Cloudability Financial Planning API — `kb/02-product-docs/apptio-financial-planning/en/api-getting-started-cloudability-financial-planning.md`
- Plan Endpoints — `kb/02-product-docs/apptio-financial-planning/en/api-plan-endpoints.md`
- Dimension Endpoints — `kb/02-product-docs/apptio-financial-planning/en/api-dimension-endpoints.md`
- Budget Endpoints — `kb/02-product-docs/apptio-financial-planning/en/api-budget-endpoints.md`
- Import/Export Endpoints — `kb/02-product-docs/apptio-financial-planning/en/api-importexport-endpoints.md`
- Alerts Endpoints — `kb/02-product-docs/apptio-financial-planning/en/api-alerts-endpoints.md`
- User Endpoints — `kb/02-product-docs/apptio-financial-planning/en/api-user-endpoints.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
