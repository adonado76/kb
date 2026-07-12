---
tbm_concept: "How-To: Manage Users and Permissions (roles por defecto, roles personalizados, y tres capas de control de acceso)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/permissions-user-management.md
  - kb/02-product-docs/apptio-tbm-studio/en/management-create-manage-users.md
  - kb/02-product-docs/apptio-tbm-studio/en/management-assign-roles-users.md
  - kb/02-product-docs/apptio-tbm-studio/en/management-configure-custom-roles.md
  - kb/02-product-docs/apptio-tbm-studio/en/permissions-access-control.md
  - kb/02-product-docs/apptio-tbm-studio/en/control-decision-guide-choosing-right-access.md
  - kb/02-product-docs/apptio-tbm-studio/en/control-set-report-permissions-by-role.md
  - kb/02-product-docs/apptio-tbm-studio/en/control-implement-row-level-security-user-access.md
  - kb/02-product-docs/apptio-tbm-studio/en/control-configure-editable-table-permissions.md
last_updated: "2026-07-07"
---
# How-To: Manage Users and Permissions — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

TBM Studio da acceso a la construcción del modelo, no solo a su consumo — eso eleva el riesgo de un modelo de permisos mal configurado, ya que un usuario con el rol equivocado podría alterar el modelo de costo de toda la organización, no solo ver un reporte incorrecto. Este capítulo cubre gestión de usuarios y las tres capas de control de acceso del producto.

## Cómo lo resuelve Apptio TBM Studio

**Roles por defecto — dos documentados explícitamente, con más implícitos.** **Admin**: acceso administrativo completo, incluyendo gestión de usuarios, configuración de proyecto y todos los datos — para administradores de TBM, dueños del sistema, administradores de seguridad. **Power User**: puede configurar modelos, crear reportes, cargar datos y acceder a ambientes de desarrollo, pero no puede gestionar usuarios ni configuración de dominio — para arquitectos TBM y analistas de IT Finance que construyen modelos y reportes.

**Create and Manage Users / Assign Roles to Users / Configure Custom Roles** — el ciclo de vida completo de gestión de identidad: creación/activación/desactivación de cuentas, asignación de rol al crear o cuando cambian responsabilidades, y — cuando los roles por defecto no cubren la combinación exacta de permisos necesaria — creación de roles personalizados con control granular.

**Tres capas de control de acceso, cada una con un propósito distinto:**

1. **Report permissions** — la primera línea de defensa: controla qué roles pueden ver reportes o colecciones enteras. Principio documentado explícitamente: si un usuario no puede ver un reporte, no puede acceder a ningún dato dentro de él — es el filtro más grueso, aplicado antes que cualquier otro.
2. **Row-Level Security (RLS)** — control a nivel de fila dentro de un reporte ya visible: usuarios distintos ven subconjuntos distintos de los mismos datos (un gerente de unidad de negocio solo ve el costo de su departamento). Arquitectura de dos componentes: **mapping tables** (definen qué usuario puede ver qué elemento de dato, ej. "bob@acme.com puede ver Business Unit 2") y **RLS filters** (aplicados a las transform tables para hacer cumplir esas reglas de mapeo).
3. **Editable Table Permissions** — control específico de quién puede editar, cargar o eliminar datos en tablas de captura manual — relevante en escenarios de captura distribuida donde gerentes de centro de costo o dueños de aplicación mantienen su propia porción de datos de referencia.

**El comportamiento de RLS documentado a través de todas las superficies del producto** — un nivel de precisión técnica poco común: en transform tables, filtra filas antes de que aparezcan en cualquier uso posterior; en editable tables, restringe qué filas el usuario puede ver **y** editar (solo puede modificar filas visibles); en reportes, las agregaciones reflejan solo los datos filtrados visibles; al publicar tablas editables, **las filas ocultas se preservan, no se eliminan**; y en reportes de resumen del modelo, cada nivel refleja el RLS aplicado específicamente a ese nivel — **los valores pueden no sumar hacia los totales mostrados en niveles superiores**, un detalle de validación crítico a anticipar.

## Por qué importa en una conversación con el cliente

La distinción Admin vs. Power User es el primer punto de discovery de gobernanza: confirmar cuántas personas del cliente necesitan realmente construir/modificar el modelo (Power User) versus solo administrar usuarios y configuración (Admin) evita sobre-provisionar acceso administrativo innecesariamente.

El detalle de que los valores de RLS "pueden no sumar hacia los totales de niveles superiores" es una de las advertencias más importantes de todo este proyecto para anticipar en cualquier validación de modelo con el cliente — sin esta explicación previa, una discrepancia de totales entre niveles se percibe como un error del sistema, cuando en realidad es el comportamiento esperado de RLS aplicado de forma independiente por nivel.

El principio de "filas ocultas se preservan, no se eliminan" al publicar tablas editables es un argumento de integridad de datos importante para clientes preocupados por pérdida accidental de información en flujos de captura distribuida con RLS activo.

## Documentos fuente

- User Management (índice) — `kb/02-product-docs/apptio-tbm-studio/en/permissions-user-management.md`
- Create and Manage Users — `kb/02-product-docs/apptio-tbm-studio/en/management-create-manage-users.md`
- Assign Roles to Users — `kb/02-product-docs/apptio-tbm-studio/en/management-assign-roles-users.md`
- Configure Custom Roles — `kb/02-product-docs/apptio-tbm-studio/en/management-configure-custom-roles.md`
- Access Control (índice) — `kb/02-product-docs/apptio-tbm-studio/en/permissions-access-control.md`
- Decision Guide: Choosing the Right Access Control — `kb/02-product-docs/apptio-tbm-studio/en/control-decision-guide-choosing-right-access.md`
- Set Report Permissions by Role — `kb/02-product-docs/apptio-tbm-studio/en/control-set-report-permissions-by-role.md`
- Implement Row-Level Security for User Access — `kb/02-product-docs/apptio-tbm-studio/en/control-implement-row-level-security-user-access.md`
- Configure Editable Table Permissions — `kb/02-product-docs/apptio-tbm-studio/en/control-configure-editable-table-permissions.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
