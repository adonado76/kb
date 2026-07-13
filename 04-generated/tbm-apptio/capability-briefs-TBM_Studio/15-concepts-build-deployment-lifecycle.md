---
concept: "Concepts: Build and Deployment Lifecycle — los tres ambientes, el proceso de build/cálculo, promoción a producción, rollback, y branches/hotfixes"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/lifecycle-build-deployment.md
  - kb/02-product-docs/apptio-tbm-studio/en/lifecycle-understanding-three-environments.md
  - kb/02-product-docs/apptio-tbm-studio/en/lifecycle-check-out-check-in-workflow.md
  - kb/02-product-docs/apptio-tbm-studio/en/lifecycle-build-calculation-process.md
  - kb/02-product-docs/apptio-tbm-studio/en/lifecycle-promotion-workflow.md
  - kb/02-product-docs/apptio-tbm-studio/en/lifecycle-rollback-recovery.md
  - kb/02-product-docs/apptio-tbm-studio/en/lifecycle-branches-hotfixes.md
  - kb/02-product-docs/apptio-tbm-studio/en/lifecycle-integration-other-workflows.md
  - kb/02-product-docs/apptio-tbm-studio/en/lifecycle-what-learn-next.md
last_updated: "2026-07-07"
---
# Concepts: Build and Deployment Lifecycle — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

Este es el capítulo de gobernanza de cambios más técnicamente profundo de todo el proyecto: no solo los tres ambientes ya introducidos conceptualmente en Getting Started, sino el mecanismo real de builds, promoción, rollback, y ramificación (branching) para cambios de configuración complejos o urgentes.

## Cómo lo resuelve Apptio TBM Studio

**Los tres ambientes, accesibles desde una sola URL vía el menú Environment** — Development (espacio personal, entrado automáticamente al hacer check-out), Staging (donde confluyen los cambios de todo el equipo), y Production (solo promovido por administradores).

**Qué es un "build"** — el proceso de calcular todas las transformaciones, métricas, drills y reportes para un ambiente dado. Los triggers de build son distintos por ambiente, y el flujo de cálculo sigue una secuencia clara: Data Tables (carga cruda) → Transform Steps (limpieza/mapeo/join/enriquecimiento) → Master Datasets (tablas unificadas, ej. Cost Source Master combinando GL, Budget y Forecast) → Model Objects (el modelo referencia esas transform tables unificadas) → Allocations (las métricas se propagan hacia abajo por la cadena de asignación).

**Promotion Workflow — dos modos, con mecanismo de bloqueo explícito.**
- **On-Demand Promotion** (estándar): validar → bloquear el proyecto (impide nuevos check-ins durante la promoción, aunque los usuarios pueden seguir haciendo check-out) → promover (Promote Now o Promote Later, esta última programable para ejecutar tan pronto el build complete o a una hora específica) → desbloquear.
- **Force Promotion** (desde v12.11.0) — promueve el último build calculado **sin bloquear Staging**, para actualizaciones urgentes cuando bloquear no es práctico.
- **Recurring Promotion** (modo avanzado): promueve automáticamente en horarios programados, para equipos con ritmo de check-in y validación ya establecido — con una restricción importante: **el bloqueo no puede combinarse con promoción recurrente**; si el proyecto está bloqueado durante un horario de promoción programado, la promoción falla.

**Rollback and Recovery — capacidad de reversión, con una advertencia explícita de uso responsable.** Casos de uso: una configuración causando problemas de performance, contenido desplegado prematuramente, o necesidad de volver rápidamente a un estado conocido bueno. Mecánica: se detienen los cálculos en curso, arranca un nuevo cálculo usando la configuración del check-in seleccionado, y **todos los check-ins posteriores a ese punto se descartan** (las operaciones de branch están exentas) — advertencia explícita: si hay cambios valiosos en esos check-ins descartados, hay que reimplementarlos manualmente después del rollback. No debe usarse "a la ligera".

**Branches and Hotfixes — la distinción entre Workspace y Branch es la más importante de esta sección.** Un **workspace** es el ambiente específico de un usuario donde viven los cambios a documentos ya sacados (checked-out) hasta el check-in — con bloqueo exclusivo del documento. Un **branch** es una **copia completa del proyecto** al momento de su creación; los cambios en un branch son independientes del trunk principal hasta que se fusionan (merge) — con su propio workspace separado del workspace en el trunk.

**Tres casos de uso documentados explícitamente para branching:**
1. **Long-Running Configuration Changes** — cambios de configuración que tomarán semanas o meses (ej. reestructuración mayor del modelo que requiere pruebas extensas), trabajados en paralelo mientras las cargas operativas de datos continúan en el trunk.
2. **Hotfix to Production** — cuando Producción tiene un problema pero Development contiene cambios aún no listos para desplegar: se crea un branch de hotfix, se corrige el problema específico ahí, se promueve a Producción, y luego se fusiona de vuelta al trunk. **Los branches de hotfix calculan en paralelo con otros builds, saltándose la cola normal**.
3. **Audit or Archive Past State** (tercer caso, mencionado pero no detallado en el extracto disponible).

## Por qué importa en una conversación con el cliente

El patrón de Hotfix Branch es la respuesta correcta a una pregunta de gobernanza que casi todo cliente hace tarde o temprano: "¿qué pasa si necesitamos corregir un problema urgente en Producción mientras hay cambios grandes sin terminar en Development?" — poder mostrarle al cliente que existe un camino formal para esto (branch de hotfix, cálculo en paralelo saltándose la cola) es un argumento de madurez operativa importante.

La advertencia de que el rollback descarta permanentemente los check-ins posteriores al punto de reversión es una de las piezas de información más críticas para comunicar antes de cualquier incidente real — un administrador que ejecuta un rollback sin entender esta consecuencia puede perder trabajo válido de otros miembros del equipo sin darse cuenta.

La incompatibilidad entre bloqueo manual y promoción recurrente es un detalle operativo fino que vale la pena confirmar explícitamente con cualquier cliente que planee usar promoción recurrente — mezclar ambos enfoques produce fallos de promoción silenciosos si no se diseña con cuidado.

## Documentos fuente

- Build & Deployment Lifecycle (índice) — `kb/02-product-docs/apptio-tbm-studio/en/lifecycle-build-deployment.md`
- Understanding the Three Environments — `kb/02-product-docs/apptio-tbm-studio/en/lifecycle-understanding-three-environments.md`
- Check-Out and Check-In Workflow — `kb/02-product-docs/apptio-tbm-studio/en/lifecycle-check-out-check-in-workflow.md`
- Build and Calculation Process — `kb/02-product-docs/apptio-tbm-studio/en/lifecycle-build-calculation-process.md`
- Promotion Workflow — `kb/02-product-docs/apptio-tbm-studio/en/lifecycle-promotion-workflow.md`
- Rollback and Recovery — `kb/02-product-docs/apptio-tbm-studio/en/lifecycle-rollback-recovery.md`
- Branches and Hotfixes — `kb/02-product-docs/apptio-tbm-studio/en/lifecycle-branches-hotfixes.md`
- Integration with Other Workflows — `kb/02-product-docs/apptio-tbm-studio/en/lifecycle-integration-other-workflows.md`
- What to Learn Next — `kb/02-product-docs/apptio-tbm-studio/en/lifecycle-what-learn-next.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
