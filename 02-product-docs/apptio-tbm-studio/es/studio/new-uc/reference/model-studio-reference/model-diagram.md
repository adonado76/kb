---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Diagramas de modelo"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
source_path: "studio/new-uc/reference/model-studio-reference/model-diagram.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Diagramas de modelo

Los diagramas de modelos ofrecen representaciones visuales de la estructura del modelo de costes, mostrando cómo fluye el valor entre los objetos del modelo.

## Tipos de diagramas y vistas

TBM Studio ofrece tres formas de visualizar el modelo, cada una de ellas con una finalidad distinta.

**Vista de una sola tabla (Área de trabajo de edición de modelos)**

**Descripción:** Muestra un objeto modelo con sus controladores y asignaciones en un diagrama de Sankey. Se utiliza para configurar objetos individuales.

**Diseño**

- Columna de la izquierda: Conductores (conductores de la unidad y asignaciones entrantes)
- Centro: El objeto modelo que se está editando
- Columna derecha: Asignaciones salientes (objetos de destino)

**Cómo acceder**

1. Haz clic en una tabla en el Explorador de proyectos
2. Haz clic en el paso «Modelo» del proceso de transformación

**Vista métrica modelada (vista de diagrama)**

**Descripción:** Visualización de alto nivel que muestra todos los objetos del modelo y sus conexiones. Similar a un diagrama de Visio. Se utiliza para comprender la estructura general del modelo.

**Características**

- Muestra todos los objetos del modelo y sus conexiones
- Admite el zoom y el desplazamiento
- Al hacer clic en un nodo, se abre la vista de tabla única de ese objeto
- Trazabilidad de costes para líneas de asignación específicas
- Refleja el modelo actualmente implementado

**Nota:** La vista de diagrama no se puede utilizar para modificar las asignaciones directamente. Los cambios deben realizarse en la vista de tabla única.

**Vista de informe del modelo (vista por niveles/Sankey)**

**Descripción:** Vista del usuario final que muestra las tablas seleccionadas organizadas en niveles con una visualización de flujos al estilo Sankey. Se utiliza para la elaboración de informes y el análisis.

**Características**

- Estructura de niveles personalizable
- Muestra los anchos de flujo proporcionales
- Acceder a los detalles de la columna
- Acceder a los datos a nivel de transacción
- Se puede añadir a las colecciones de informes ( v12.2.2+ )

*Consulte [los informes de modelos para obtener información detallada sobre la configuración](model-reports.html)*

- **[Conceptos del diagrama de Sankey](../../../../studio/new-uc/reference/model-studio-reference/sankey-diagram.html)**
- **[Navegación por el diagrama](../../../../studio/new-uc/reference/model-studio-reference/diagram-navigation.html)**
- **[Opciones de personalización de diagramas](../../../../studio/new-uc/reference/model-studio-reference/diagram-customization.html)**
- **[Exportación y uso compartido](../../../../studio/new-uc/reference/model-studio-reference/export-sharing.html)**
