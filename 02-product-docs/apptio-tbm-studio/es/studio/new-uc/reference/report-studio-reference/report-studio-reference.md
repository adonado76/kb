---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Referencia de Report Studio"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
source_path: "studio/new-uc/reference/report-studio-reference/report-studio-reference.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Referencia de Report Studio

## Visión general

Report Studio te permite crear informes interactivos que presentan los datos de tus modelos a las partes interesadas. Los informes pueden incluir tablas, gráficos y diversos elementos para filtrar, navegar e introducir datos. Esta sección de referencia ofrece documentación completa sobre todas las funciones y componentes de Report Studio.

Utilice esta sección para consultar las propiedades específicas de los componentes, las opciones de configuración y los detalles técnicos. Para obtener instrucciones detalladas sobre cómo crear informes, consulte ***la sección « 3.3 : Crear informes*** ».

## Principales características

- **Visualización de datos:** muestra los datos del modelo mediante tablas y gráficos configurables con navegación de desglose
- **Filtrado interactivo:** Facilita la exploración de datos mediante segmentadores, selectores de columnas y tableros dinámicos
- **Introducción de datos:** Permitir a los usuarios finales introducir datos directamente a través de tablas editables y componentes de carga
- **Imagen de marca coherente:** aplica plantillas de informes y paletas de colores personalizadas para cumplir con los estándares de la organización
- **Control de acceso:** gestiona la visibilidad de los informes mediante permisos basados en roles

## Contenido de la sección

Esta sección contiene 11 apartados que abarcan todos los componentes y funciones de Report Studio:

|  |  |
| --- | --- |
| **Tema** | **Descripción** |
| **Tablas** | Configurar tablas basadas en objetos y de transformación, añadir columnas (de fórmula, calculadas, de calendario, de minigráficos y de totales), establecer la agrupación y la ordenación, y definir las propiedades de la tabla, incluyendo el formato condicional y los enlaces de navegación. |
| **Gráficos** | Crea visualizaciones, como gráficos de barras, de barras apiladas, de columnas, de columnas apiladas, de líneas, circulares, de KPI, de árbol y en cascada. Configura las paletas de colores, las leyendas y la navegación entre gráficos e informes. |
| **Filtros y segmentadores** | Añade filtros interactivos, configura filtros compactos, selectores de columnas y tablas dinámicas rápidas. Permite el descubrimiento de datos mediante combinaciones dinámicas de filtros. |
| **Navegación** | Crea enlaces de profundización entre informes, configura botones de navegación al estilo wiki, crea navegadores de colecciones de informes y configura informes emergentes modales. |
| **Componentes de entrada** | Añade botones, cuadros de texto HTML, notas, cuadros de grupo y componentes con pestañas. Configure los componentes de carga de tablas para que los usuarios finales puedan introducir datos sin necesidad de acceder a Studio. |
| **Tablas editables** | Configure los componentes de informe de tabla editables para la introducción directa de datos. Configura listas desplegables, valores posibles, bloqueo de celdas, permisos de carga y flujos de trabajo de publicación. |
| **Propiedades de informe** | Configure los ajustes del informe, incluyendo el estado activo, el tipo de informe (desglose, filtrado, unidad), los campos de búsqueda automática, las opciones de cálculo y las propiedades avanzadas. |
| **Diseño** | Aplica opciones dinámicas de tamaño y posicionamiento (centrar, ajustar al ancho, acoplar). Configura diseños adaptables, la visibilidad de los grupos con pestañas y la disposición de los componentes dentro de los contenedores. |
| **Informes principales** | Crea y aplica plantillas de informes para garantizar la coherencia en los diseños. Utiliza informes estándar o crea plantillas personalizadas con contenedores, botones y elementos de marca reutilizables. |
| **Colecciones de informes** | Crea y gestiona colecciones de informes para agrupar informes relacionados. Añadir o eliminar informes, configurar los navegadores de colecciones y controlar la visibilidad de los informes dentro de las colecciones. |
| **Permisos del informe** | Configure el control de acceso basado en roles para los informes. Configure los permisos de visualización, edición y eliminación a nivel de informe y de colección. Gestiona la visibilidad de los componentes según el rol. |

## Guía de navegación

**Cómo utilizar esta referencia**

Esta sección está concebida como una guía de referencia para consultar detalles específicos sobre las funciones de Report Studio. Ve a la subsección correspondiente según lo que necesites hacer:

- **Creación de representaciones de datos:** Véanse [«Tablas](report-component-table.html) y [gráficos»](report-component-charts.html)
- **Añadir interactividad:** consulta [«Filtros y segmentadores»](report-component-filters-slicers.html) y [«Navegación»](report-component-navigation.html)
- **Habilitar la introducción de datos:** Véase [«Componentes de entrada](report-component-input-components.html) y [tablas editables»](report-component-editable-components.html)
- **Personalización del aspecto:** consulta [«Propiedades](report-properties.html) y [diseño del informe»](layout-options.html)
- **Estandarización de informes:** Véase [«Informes maestros»](master-report.html)
- **Gestión del acceso:** Consulte [«Colecciones de informes»](report-collection.html) y [«Permisos de informes»](report-permissions.html)

**Secciones relacionadas**

Si necesitas orientación práctica sobre cómo crear y personalizar informes, consulta estas secciones de instrucciones:

- **Conceptos básicos sobre informes:** instrucciones paso a paso para crear [informes](../../howtoguides/create-reports/create-basic-report.html), añadir [tablas](../../howtoguides/create-reports/add-tables-report.html) y [gráficos](../../howtoguides/create-reports/add-chart-visual.html)
- Procedimientos **de personalización de informes** para [perspectivas personalizadas](../../howtoguides/create-reports/create-cust-pers.html), [colecciones](../../howtoguides/create-reports/build-rc.html) e [informes maestros](../../howtoguides/create-reports/design-master-rep.html)
- Guía **avanzada** sobre informes: [informes con función de desglose](../../howtoguides/create-reports/drill-thru-reports.html), [componentes editables](../../howtoguides/create-reports/add-et-rep.html) y [exportaciones](../../howtoguides/create-reports/export-print-rep.html)

## Requisitos previos

Antes de empezar a trabajar con Report Studio, asegúrate de:

- Los datos se han subido a través de Data Studio
- Los modelos de asignación se han creado en Model Studio (para informes basados en objetos)
- Tienes los permisos de rol adecuados (administrador o usuario avanzado para editar; usuario empresarial para ver)
- El proyecto dispone de datos calculados para el periodo sobre el que desea elaborar el informe

## Panel de configuración de componentes

Al crear tablas y gráficos, se utiliza el panel «Configuración de componentes» para definir qué datos se muestran. El panel incluye cuatro secciones principales: **Filas** (dimensión de agrupación), **Valores** (métricas que se van a mostrar), **Columnas** (períodos de tiempo) y **Filtros** (restricciones de datos). Arrastra los campos desde el Explorador de proyectos a estas áreas para configurar los componentes de tu informe. El panel se muestra de forma diferente para los usuarios avanzados (con acceso completo) y para los analistas (solo perspectivas personalizadas).
