---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Componentes de los informes: tablas editables en los informes"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
source_path: "studio/new-uc/reference/report-studio-reference/report-component-editable-components.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Componentes de los informes: tablas editables en los informes

El componente de informe «Tabla editable» permite realizar flujos de trabajo de introducción de datos directamente desde la interfaz de informes. Los usuarios pueden introducir, modificar y publicar datos sin necesidad de acceder a TBM Studio, lo que lo convierte en la solución ideal para escenarios de recopilación de datos distribuida, como los flujos de trabajo de introducción de presupuestos, enriquecimiento de datos y clasificación de datos.

## Descripción general del componente de tabla editable

El componente de informe «Tabla editable» muestra los datos de una tabla editable subyacente (creada en Data Studio ) y permite a los usuarios autorizados modificar dichos datos directamente desde un informe. Para una implementación correcta, es fundamental comprender en qué se diferencia este componente de otros tipos de tablas.

**Diferencias con respecto a las tablas de informes estándar**

Las tablas estándar de los informes (sección 5.3.1 ) muestran datos de solo lectura procedentes de tablas de transformación u objetos de modelo. Las principales diferencias con respecto a los componentes de tabla editables son las siguientes:

- Los usuarios finales no pueden modificar las tablas estándar; los componentes de tabla editables permiten introducir datos directamente
- Las tablas estándar muestran datos calculados o agregados; las tablas editables almacenan los valores introducidos por el usuario
- Las tablas estándar se actualizan automáticamente cuando cambian las fuentes de datos; las tablas editables requieren acciones explícitas de guardado y publicación
- Las tablas editables incluyen controles adicionales para añadir filas, eliminar filas, guardar y publicar

**Diferencias con respecto a las tablas editables de Data Studio**

Las tablas editables se definen en Data Studio (sección 5.1 ) y se muestran a través de componentes de informe. La relación funciona de la siguiente manera:

- Data Studio : Define el esquema de la tabla editable, los tipos de columna, las reglas de validación y los valores posibles
- Report Studio: Crea el componente visible para el usuario que muestra la tabla y permite editarla
- El componente de informe hereda las definiciones de columnas de la configuración de Data Studio
- Los ajustes a nivel de informe determinan qué columnas son visibles y editables, así como la forma en que se presentan los datos

**Casos de uso habituales**

Los componentes de tabla editables son ideales para los siguientes casos:

- **Entrada presupuestaria:** Permitir a los responsables de centros de coste introducir las previsiones presupuestarias directamente en los informes
- **Enriquecimiento de datos:** permite a los usuarios añadir clasificaciones, categorías o asignaciones a los datos importados
- **Mapeo de la mano de obra:** permite a los equipos de RR. HH. o de finanzas asignar personal a centros de coste o proyectos
- **Explicaciones de las desviaciones:** Recopilar las justificaciones de los jefes de departamento sobre las desviaciones presupuestarias
- **Flujos de trabajo de aprobación:** Realiza un seguimiento del estado de aprobación y los comentarios de las partidas

- **[Configuración de la tabla editable](../../../../studio/new-uc/reference/report-studio-reference/editable-table-config.html)**
- **[Opciones de edición de columnas](../../../../studio/new-uc/reference/report-studio-reference/column-editing-options.html)**
- **[Configuración de validación](../../../../studio/new-uc/reference/report-studio-reference/validation-config.html)**
- **[Operaciones con filas](../../../../studio/new-uc/reference/report-studio-reference/row-operations.html)**
- **[Guardar configuración](../../../../studio/new-uc/reference/report-studio-reference/save-behavior.html)**
- **[Permisos de edición](../../../../studio/new-uc/reference/report-studio-reference/edit-permissions.html)**
- **[Estilo de las tablas editables](../../../../studio/new-uc/reference/report-studio-reference/styling-editable-tables.html)**
- **[Tabla editable + Integración de informes](../../../../studio/new-uc/reference/report-studio-reference/et-ri.html)**
- **[Patrones habituales](../../../../studio/new-uc/reference/report-studio-reference/common-patterns.html)**
- **[Solución de problemas](../../../../studio/new-uc/reference/report-studio-reference/editable-troubleshoot.html)**
