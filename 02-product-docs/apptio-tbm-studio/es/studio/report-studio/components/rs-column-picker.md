---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Selector de columnas"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Componentes"
source_path: "studio/report-studio/components/rs-column-picker.html"
images:
  - "resources/images/studio_images/column-picker.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Selector de columnas

Un selector de columnas permite a los usuarios controlar qué columnas se muestran en una tabla normal, una tabla editable o un gráfico. Permite explorar de forma flexible los datos tabulares sin necesidad de cambiar la configuración del informe.

## Cuándo utilizar un selector de columnas

Utiliza un selector de columnas cuando quieras que los usuarios:

- Mostrar u ocultar columnas de la tabla según sus necesidades
- Céntrate en métricas o dimensiones específicas
- Reducir el desorden visual en tablas anchas

## Añadir un selector de columnas al informe

1. Añadir un selector de columnas desde el panel Componentes de la barra de herramientas
2. Haga clic en el selector de columnas para habilitar los paneles Datos y Formato.
3. Panel de datos
   1. Seleccione el objeto modelo de la lista desplegable
   2. Arrastre las dimensiones desde el Explorador de dimensiones a la sección de campos del panel de datos
4. Panel de formato
   1. Propiedades generales: consulte [Propiedades de los componentes.](components.html#abt-comp__comprop)
   2. Propiedades específicas del selector de columnas
      1. Selección
         1. Selección múltiple: las columnas aparecen como un conjunto de casillas de verificación.
         2. Selección única con - Los campos del selector aparecen como botones de opción.
      2. Activar Seleccionar todo
         1. Alternar para ver la opción **Seleccionar todo** en el componente selector de columnas.
      3. Orientación
         1. Vertical
         2. Horizontal

Ejemplo: Selector de columnas

![selector de columna](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/column-picker.png)

Column Picker admite fórmulas personalizadas y dimensiones de fórmulas. Para obtener más información, consulte [Fórmulas personalizadas.](../create-first/custom-formula.html "Las fórmulas personalizadas (también denominadas dimensiones de fórmula) le permiten definir nuevas dimensiones calculadas utilizando campos existentes en su modelo de datos. Esto permite realizar análisis más profundos y obtener información más detallada sin necesidad de realizar cambios en el conjunto de datos o el esquema subyacentes.")
