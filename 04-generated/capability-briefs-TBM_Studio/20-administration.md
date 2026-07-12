---
tbm_concept: "Administration (proyecto, multi-moneda, usuarios, seguridad/cumplimiento, performance, precisión numérica, y build/deployment desde la perspectiva del administrador)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/administration-project.md
  - kb/02-product-docs/apptio-tbm-studio/en/administration-configure-multi-currency.md
  - kb/02-product-docs/apptio-tbm-studio/en/administration-user-management.md
  - kb/02-product-docs/apptio-tbm-studio/en/administration-security-compliance.md
  - kb/02-product-docs/apptio-tbm-studio/en/administration-performance-optimization.md
  - kb/02-product-docs/apptio-tbm-studio/en/administration-apptioone-precision.md
  - kb/02-product-docs/apptio-tbm-studio/en/administration-build-deployment.md
last_updated: "2026-07-07"
---
# Administration — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

El capítulo operativo consolidado para el rol de Administrador, ya perfilado en Learning Paths: configuración de proyecto y multi-moneda, gestión de usuarios, seguridad y cumplimiento, optimización de performance, y — el hallazgo más singular de este capítulo — la especificación técnica exacta de cómo TBM Studio maneja la precisión numérica internamente.

## Cómo lo resuelve Apptio TBM Studio

**Project Administration** — un proyecto es la unidad organizacional fundacional (agrupa datasets, métricas, modelos y reportes en un solo espacio de trabajo, con su propia configuración, ajustes de tiempo y permisos de usuario). Project Settings controla comportamiento a nivel de proyecto (cálculo, formato, presentación); Time Settings define el calendario fiscal y qué períodos están activos; **Domain Settings** controla configuraciones a nivel de todo el dominio (aplican a todos los proyectos de la instancia Apptio) — incluyendo el Proyecto por Defecto que se abre al iniciar sesión sin especificar uno.

**Configure multi-currency — el procedimiento más detallado documentado en esta categoría.** Moneda y locale son **independientes entre sí**: la moneda determina el símbolo/código ISO 4217 mostrado; el locale determina el formato de número (posición del símbolo, separadores) sin importar el símbolo literal. Procedimiento: ingresar tasas de cambio en la tabla Currency Exchange (moneda base siempre = 1, código de tres letras estándar), asignar un tipo de tasa por defecto a cada métrica de costo/precio, y seleccionar moneda base + locale del proyecto. **Restricciones documentadas explícitamente**: en reportes, solo valores de métricas modeladas de tipo Costing/Pricing pueden mostrarse en la moneda elegida por el usuario — el resto se muestra en moneda base o ya convertida; multi-currency solo aplica a tablas/gráficos Ad Hoc, no a los legacy; las tablas editables se muestran en la moneda asignada al dataset y no se puede cambiar; **los gráficos Waterfall siempre se muestran en la moneda base del proyecto**, sin excepción.

**User Management (Roles y Permisos)** — el modelo ya documentado en el capítulo de Security Model, aquí desde la perspectiva operativa de quién los configura.

**Security & Compliance** — Domain Security Settings controla políticas de autenticación, requisitos de contraseña, y gestión de sesión para todos los usuarios del ambiente Apptio — el nivel más alto de configuración de seguridad, complementario al detalle de RBAC/RLS ya visto en Concepts: Security Model.

**Performance & Optimization — cuatro herramientas de diagnóstico y un conjunto de mejores prácticas:**
- **Calc Explorer** — visibilidad detallada del esfuerzo de cálculo por reportes, transformaciones, drills y métricas — la herramienta correcta para identificar cuellos de botella de performance.
- **Build Anomaly Detection** — compara cada build contra builds anteriores y alerta sobre cambios significativos en esfuerzo de cálculo, detectando problemas de performance temprano, antes de que se vuelvan críticos.
- **Recommendations Engine** — identifica problemas de configuración que pueden impactar performance o calidad de datos, con flujos de trabajo guiados para resolverlos.
- **Performance Review Component** — reportes que muestran el impacto de la configuración del proyecto en performance, incluyendo análisis de relaciones de asignación, salud de identificadores, y granularidad del modelo.
- **Mejores prácticas documentadas explícitamente**: reducir granularidad innecesaria (eliminar columnas/detalle no necesario para asignaciones o reporte), agrupar filas (agregar datos a nivel de transacción cuando el detalle no se necesita), desactivar reportes no usados (los reportes contribuyen al tiempo de cálculo incluso si no se ven frecuentemente), y **reemplazar `Eval()` con `DynamicColumn()`** para mejoras de performance de cálculo de precisión.

**ApptioOne Precision — el documento más técnicamente singular de toda la base de conocimiento de TBM Studio.** Apptio usa la especificación **IEEE 754 de punto flotante de doble precisión**, que da aproximadamente 17 − log₁₀(N) dígitos de precisión para la mayoría de operaciones (N = número de valores sumados), y hasta apenas 15 dígitos para ciertas otras operaciones — por lo que números más allá de 15 dígitos **pueden cambiar entre builds o entre cálculos del mismo build/configuración/dato**. El redondeo usa la regla "round half away from zero" (redondeo comercial). Las sumas usan el **algoritmo de Suma de Kahan** para máxima precisión posible. Y — el detalle más peculiar — Apptio agrega un "fudge amount" de **0.00000001** a todos los números mostrados vía `Round()` o `NumberFormat()`, específicamente para controlar el redondeo de números de punto flotante. Precisión práctica garantizada: 15 dígitos significativos o 7 decimales.

**Build & Deployment (perspectiva de administrador)** — reconfirma los tres ambientes, el flujo de check-out/check-in (con buenas prácticas explícitas: revisar datos antes de cargar, guardar tras cualquier modificación, resolver todos los errores antes de check-in, validar reportes que usan el dato modificado), el **Calculation Queue** (monitorea el estado de builds a través de todos los ambientes), bloqueo y promoción a producción, trabajo con branches, rollback (con la misma advertencia crítica ya vista en Concepts: Build and Deployment Lifecycle), y **promociones programadas y recurrentes** para flujos de despliegue automatizado.

## Por qué importa en una conversación con el cliente

El documento de ApptioOne Precision es material de referencia crítico para cualquier conversación donde un cliente cuestione "por qué este número cambió ligeramente entre dos cálculos idénticos en apariencia" — la respuesta honesta y técnicamente precisa es que el sistema opera bajo las limitaciones matemáticas conocidas y documentadas de IEEE 754 de doble precisión, no un bug — vale la pena tener este documento a mano en cualquier conversación de validación de modelo con analistas financieros exigentes.

La restricción de que los gráficos Waterfall siempre se muestran en moneda base (sin excepción, incluso con multi-currency activo) es un detalle operativo puntual que vale la pena confirmar explícitamente en cualquier demo o validación con un cliente multinacional que use ese tipo de gráfico.

Las cuatro herramientas de Performance & Optimization (Calc Explorer, Anomaly Detection, Recommendations Engine, Performance Review) son un argumento de madurez operativa fuerte para cualquier cliente preocupado por tiempos de build crecientes a medida que su modelo escala — vale la pena posicionarlas explícitamente como parte del programa de "salud del modelo" recurrente, no solo herramientas de troubleshooting reactivo.

## Documentos fuente

- Project Administration (índice) — `kb/02-product-docs/apptio-tbm-studio/en/administration-project.md`
- Configure multi-currency — `kb/02-product-docs/apptio-tbm-studio/en/administration-configure-multi-currency.md`
- User Management — `kb/02-product-docs/apptio-tbm-studio/en/administration-user-management.md`
- Security & Compliance — `kb/02-product-docs/apptio-tbm-studio/en/administration-security-compliance.md`
- Performance & Optimization — `kb/02-product-docs/apptio-tbm-studio/en/administration-performance-optimization.md`
- ApptioOne Precision — `kb/02-product-docs/apptio-tbm-studio/en/administration-apptioone-precision.md`
- Build & Deployment — `kb/02-product-docs/apptio-tbm-studio/en/administration-build-deployment.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
