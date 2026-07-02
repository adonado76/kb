---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración de la tabla editable"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes de los informes: tablas editables en los informes"
source_path: "studio/new-uc/reference/report-studio-reference/editable-table-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración de la tabla editable

Para configurar un componente de tabla editable, hay que conectarse a una fuente de datos, seleccionar las columnas y configurar los comportamientos de edición.

**Conexión a la fuente de datos**

Para añadir un componente de tabla editable a un informe:

1. Echa un vistazo al informe en Report Studio
2. Ve a la pestaña «Informe» y selecciona el componente «Tabla editable»
3. En el panel «Configuración de componentes», selecciona la tabla editable en la vista «Tablas»
4. Arrastra las columnas de la tabla al área «Columnas incluidas»

Consejo: Solo las tablas creadas como tablas editables en Data Studio aparecerán como fuentes válidas para los componentes de tabla editables.

**Correlación de columnas**

Al configurar el componente, puedes elegir qué columnas se muestran y en qué orden:

- **Columnas incluidas:** arrastra las columnas de la tabla de origen para que aparezcan en el informe
- **Orden de las columnas:** reorganiza las columnas arrastrándolas dentro del área «Columnas incluidas»
- **Columnas ocultas:** las columnas que no se incluyen permanecen en la tabla subyacente, pero no se muestran

Las columnas del sistema, como.PK (clave primaria),.Username y .EditDate, se pueden mostrar u ocultar haciendo clic con el botón derecho del ratón en el encabezado de la columna y seleccionando «Mostrar» u «Ocultar».

**Filtrado por filas**

Puedes limitar las filas que aparecen en el componente de tabla editable:

- Arrastra las columnas de filtro al área «Filtros» del panel «Configuración de componentes»
- Haz clic con el botón derecho del ratón en el filtro y selecciona «Editar filtro» para especificar los valores del filtro
- Los filtros pueden ser estáticos (valores fijos) o estar vinculados a segmentadores para permitir un filtrado dinámico

Advertencia: *Cuando la seguridad a nivel de fila (RLS) está activa, los usuarios solo ven las filas para las que tienen autorización, independientemente de los filtros a nivel de informe.*

**Tema principal:** [Componentes de los informes: Tablas editables en los informes](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
