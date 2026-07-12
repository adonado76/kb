---
tbm_concept: "Concepts: Security Model — arquitectura de seguridad en capas (autenticación, RBAC, RLS, permisos de componente), mejores prácticas, y seguridad a través del ciclo de vida"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/model-security-architecture-overview.md
  - kb/02-product-docs/apptio-tbm-studio/en/model-authentication-identity.md
  - kb/02-product-docs/apptio-tbm-studio/en/model-role-based-access-control-rbac.md
  - kb/02-product-docs/apptio-tbm-studio/en/rbac-how-works.md
  - kb/02-product-docs/apptio-tbm-studio/en/rbac-default-roles.md
  - kb/02-product-docs/apptio-tbm-studio/en/rbac-custom-roles.md
  - kb/02-product-docs/apptio-tbm-studio/en/rbac-permission-inheritance-effective-permissions.md
  - kb/02-product-docs/apptio-tbm-studio/en/model-row-level-security-rls.md
  - kb/02-product-docs/apptio-tbm-studio/en/rls-how-works.md
  - kb/02-product-docs/apptio-tbm-studio/en/rls-architecture.md
  - kb/02-product-docs/apptio-tbm-studio/en/rls-scope-where-applies.md
  - kb/02-product-docs/apptio-tbm-studio/en/rls-inheritance-flow.md
  - kb/02-product-docs/apptio-tbm-studio/en/model-report-component-permissions.md
  - kb/02-product-docs/apptio-tbm-studio/en/permissions-component-level-visibility.md
  - kb/02-product-docs/apptio-tbm-studio/en/permissions-editable-table.md
  - kb/02-product-docs/apptio-tbm-studio/en/permissions-table-upload-component.md
  - kb/02-product-docs/apptio-tbm-studio/en/permissions-how-report-rls-interact.md
  - kb/02-product-docs/apptio-tbm-studio/en/model-security-best-practices.md
  - kb/02-product-docs/apptio-tbm-studio/en/practices-security-design-patterns.md
  - kb/02-product-docs/apptio-tbm-studio/en/practices-security-testing-validation.md
  - kb/02-product-docs/apptio-tbm-studio/en/model-security-across-lifecycle.md
  - kb/02-product-docs/apptio-tbm-studio/en/lifecycle-staging-environment-security.md
  - kb/02-product-docs/apptio-tbm-studio/en/lifecycle-production-environment-security.md
  - kb/02-product-docs/apptio-tbm-studio/en/lifecycle-security-check-incheck-out-workflow.md
last_updated: "2026-07-07"
---
# Concepts: Security Model — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

TBM Studio da acceso a la construcción del modelo de costo, no solo a su consumo — el riesgo de un modelo de seguridad mal diseñado es proporcionalmente mayor que en un producto puramente de reporte. Este es el capítulo de arquitectura de seguridad más extenso de todo el proyecto: cuatro capas, ciclo de vida completo, y — el hallazgo más importante — una advertencia explícita sobre los límites reales de RLS frente a usuarios Admin.

## Cómo lo resuelve Apptio TBM Studio

**Cuatro capas de seguridad, cada una respondiendo una pregunta distinta:**

| Capa | Pregunta que responde | Mecanismo | Alcance |
|---|---|---|---|
| 1. Authentication | ¿Quién eres? | Usuario/contraseña, SSO, API keys | Todo el dominio |
| 2. RBAC | ¿Qué puedes hacer? | Roles y permisos | Nivel de proyecto |
| 3. RLS | ¿Qué datos puedes ver? | Tablas de mapeo + filtros | Nivel de fila |
| 4. Component | ¿Qué partes del reporte ves? | Visibilidad condicional | Nivel de componente |

**Security Decision Framework — cuatro preguntas secuenciales** para diseñar cualquier configuración: ¿quién necesita acceso? → cuentas y autenticación; ¿qué debería poder hacer cada persona? → roles con permisos apropiados; ¿qué reportes debería ver cada persona? → permisos de reporte por rol; ¿personas distintas deberían ver datos distintos en el mismo reporte? → row-level security.

**Autenticación — múltiples métodos, gestionados vía Enhanced Access Administration (EAA).** Usuario/contraseña, y **API Key Authentication** (clave pública + clave secreta) como método preferido para acceso programático, dado que ofrece mejor seguridad que usuario/contraseña y puede acotarse a permisos específicos. Identidad de sesión vía tokens (Apptio-opentoken), con expiración configurable a nivel de dominio, y **Impersonation** — administradores pueden impersonar a otro usuario para verificar sus permisos y diagnosticar problemas de acceso, una herramienta de prueba valiosa para validar configuraciones de seguridad.

**RBAC — roles por defecto con listas de permisos específicas documentadas.** Además de Admin y Power User ya vistos en el capítulo How-To, aparecen aquí con detalle: permisos clave de Admin incluyen AccessDev, AccessStg, AccessProd, Edit Models, UploadData, ViewViewAllData; Power User incluye AccessDev, AccessStg, Edit Models, UploadData, DrillDown, Edit Personal Reports; y un tercer rol, **Business User** (o "View-only"), limitado a ver reportes y datos en producción, sin modificar modelos/transformaciones/configuración, con permisos como AccessProd, ViewReportsSavedForEveryone, DrillDown. Un rol adicional de **Analyst**, con permiso de Edit Personal Reports (reportes personales visibles solo para sí mismo), puede existir según la instalación.

**Advertencia de seguridad crítica, documentada explícitamente: "RLS does not reliably restrict Admin users."** Los usuarios Admin tienen acceso a modo Studio y en última instancia pueden autorear reportes que evaden RLS, agregarse a sí mismos a tablas de mapeo de RLS, o desactivar RLS por completo. **No se debe confiar en RLS para proteger datos de usuarios Admin** — la única protección real frente a un Admin es no otorgar ese rol a quien no debería tener visibilidad total.

**RLS Scope — dónde aplica y dónde no.** Se aplica vía un paso de pipeline RLS agregado individualmente a cada tabla (agregar un paso RLS automáticamente agrega un paso de modelado) — **solo tablas modeladas y tablas editables pueden tener RLS**. En asignaciones del modelo, la configuración de RLS en la tabla fuente y en la tabla destino son **independientes entre sí** — un detalle sutil que puede generar comportamiento inesperado si no se diseña deliberadamente.

**Report Permissions con interfaz simplificada desde v12.7** — reemplazando el patrón anterior de crear copias separadas de reporte por cada rol, con un modelo de permisos unificado.

**Principle of Least Privilege, aplicado en cada capa**: asignar el rol menos privilegiado que satisfaga la necesidad del usuario (empezar con Business User y elevar solo cuando se requiera); al crear roles personalizados, incluir solo los permisos que realmente se necesitan, evitando copiar permisos de Admin "por si acaso".

**Seguridad a través del ciclo de vida — Development, Staging, Production, cada una con su propio perfil de seguridad.** El ambiente de Development requiere el permiso AccessDev (típicamente Admin y Power User), con el mecanismo de check-out/check-in ya visto en Getting Started actuando también como control de concurrencia de seguridad (bloquea el objeto para que otros no editen simultáneamente).

## Por qué importa en una conversación con el cliente

La advertencia de que RLS no protege confiablemente contra usuarios Admin es, posiblemente, el hallazgo de seguridad más importante de todo este proyecto para comunicar proactivamente en cualquier conversación de gobernanza con el cliente — un cliente que asume que otorgar acceso Admin "con RLS activo" sigue siendo seguro necesita esta corrección explícita antes de diseñar su modelo de roles, no después de un incidente de exposición de datos.

El Security Decision Framework de cuatro preguntas es directamente reutilizable como cuestionario de discovery de seguridad en cualquier propuesta de implementación — ayuda a estructurar una conversación que de otra forma podría volverse desordenada entre autenticación, roles, permisos de reporte y RLS.

La independencia de configuración de RLS entre tabla fuente y tabla destino en una asignación es un detalle técnico de diseño que vale la pena validar explícitamente durante cualquier configuración de modelo con múltiples niveles de RLS — un descuido aquí puede generar fugas de datos no intencionales entre niveles del modelo.

## Documentos fuente

- Security Architecture Overview — `kb/02-product-docs/apptio-tbm-studio/en/model-security-architecture-overview.md`
- Authentication and Identity — `kb/02-product-docs/apptio-tbm-studio/en/model-authentication-identity.md`
- Role-Based Access Control (RBAC) (índice) — `kb/02-product-docs/apptio-tbm-studio/en/model-role-based-access-control-rbac.md`
- How RBAC Works — `kb/02-product-docs/apptio-tbm-studio/en/rbac-how-works.md`
- Default Roles — `kb/02-product-docs/apptio-tbm-studio/en/rbac-default-roles.md`
- Custom Roles — `kb/02-product-docs/apptio-tbm-studio/en/rbac-custom-roles.md`
- Permission Inheritance and Effective Permissions — `kb/02-product-docs/apptio-tbm-studio/en/rbac-permission-inheritance-effective-permissions.md`
- Row-Level Security (RLS) (índice) — `kb/02-product-docs/apptio-tbm-studio/en/model-row-level-security-rls.md`
- How RLS Works — `kb/02-product-docs/apptio-tbm-studio/en/rls-how-works.md`
- RLS Architecture — `kb/02-product-docs/apptio-tbm-studio/en/rls-architecture.md`
- RLS Scope: Where RLS Applies — `kb/02-product-docs/apptio-tbm-studio/en/rls-scope-where-applies.md`
- RLS Inheritance and Flow — `kb/02-product-docs/apptio-tbm-studio/en/rls-inheritance-flow.md`
- Report and Component Permissions (índice) — `kb/02-product-docs/apptio-tbm-studio/en/model-report-component-permissions.md`
- Component-Level Visibility — `kb/02-product-docs/apptio-tbm-studio/en/permissions-component-level-visibility.md`
- Editable Table Permissions — `kb/02-product-docs/apptio-tbm-studio/en/permissions-editable-table.md`
- Table Upload Component Permissions — `kb/02-product-docs/apptio-tbm-studio/en/permissions-table-upload-component.md`
- How Report Permissions and RLS Interact — `kb/02-product-docs/apptio-tbm-studio/en/permissions-how-report-rls-interact.md`
- Security Best Practices (índice) — `kb/02-product-docs/apptio-tbm-studio/en/model-security-best-practices.md`
- Security Design Patterns — `kb/02-product-docs/apptio-tbm-studio/en/practices-security-design-patterns.md`
- Security Testing and Validation — `kb/02-product-docs/apptio-tbm-studio/en/practices-security-testing-validation.md`
- Security Across the Lifecycle (índice) — `kb/02-product-docs/apptio-tbm-studio/en/model-security-across-lifecycle.md`
- Staging Environment Security — `kb/02-product-docs/apptio-tbm-studio/en/lifecycle-staging-environment-security.md`
- Production Environment Security — `kb/02-product-docs/apptio-tbm-studio/en/lifecycle-production-environment-security.md`
- Security and the Check-In/Check-Out Workflow — `kb/02-product-docs/apptio-tbm-studio/en/lifecycle-security-check-incheck-out-workflow.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
