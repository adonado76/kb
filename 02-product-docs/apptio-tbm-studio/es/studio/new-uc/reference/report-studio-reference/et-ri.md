---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Tabla editable + Integración de informes"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes de los informes: tablas editables en los informes"
source_path: "studio/new-uc/reference/report-studio-reference/et-ri.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tabla editable + Integración de informes

Los componentes de tabla editables interactúan con otros elementos del informe y con el flujo de datos.

**Repercusiones en otros componentes del informe**

Los cambios realizados en los datos de las tablas editables no afectan inmediatamente al resto de componentes del informe:

- Los gráficos y las tablas vinculados a las tablas de transformación muestran los datos de la última publicación

- Los cambios guardados pero no publicados solo son visibles en el componente de tabla editable

- Tras la publicación, es necesario que finalice una compilación o un cálculo para que los demás componentes reflejen los cambios

**Comportamiento de actualización**

Después de guardar o publicar:

- El componente de tabla editable se actualiza automáticamente
- Es posible que otros componentes requieran una actualización manual o una recarga completa del informe
- Para recibir actualizaciones en tiempo real, configura programas de publicación periódica

**Columnas calculadas**

Puedes añadir columnas de fórmulas a los componentes de tabla editables:

- Las columnas calculadas pueden hacer referencia a valores de columna editables
- Los valores se actualizan a medida que los usuarios introducen datos
- Las columnas de fórmulas son siempre de solo lectura

**Tema principal:** [Componentes de los informes: Tablas editables en los informes](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
