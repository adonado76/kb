---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos circulares"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Visualizaciones"
source_path: "studio/report-studio/visualizations/rs-pie.html"
images:
  - "resources/images/studio_images/rs-pie.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos circulares

Un gráfico circular muestra los datos como porciones de un círculo, indicando las proporciones relativas de cada categoría con respecto al total. Es ideal para ilustrar relaciones porcentuales o entre partes y el todo.

## Cuándo utilizar un gráfico circular

Utilice un gráfico circular cuando desee:

- Mostrar proporciones del total para un pequeño número de categorías
- Resaltar los segmentos más grandes o más pequeños
- Proporcionar una comparación visual rápida de las partes con el conjunto

## Añadir un gráfico circular a un informe

1. Añadir un gráfico circular desde el panel Visualizaciones de la barra de herramientas
2. Haga clic en el gráfico circular para habilitar los paneles Datos y Formato.
3. Panel de datos
   1. Seleccione el objeto modelo en el menú desplegable
   2. Categorías: define las porciones del gráfico circular utilizando una dimensión. Haga clic aquí o arrastre para añadir dimensiones desde el Explorador de dimensiones
   3. Valores: especifica la métrica o métricas que determinan el tamaño de la porción
   4. Filtros: limita los datos que se muestran en el gráfico según las condiciones seleccionadas
4. Panel de formato
   1. Propiedades generales: consulte [Propiedades de los componentes.](../components/components.html#abt-comp__comprop)
   2. Propiedades específicas del gráfico circular
      1. Total
         1. Conmutar para mostrar el recuento Total.
         2. Tamaño y estilo de fuente de la leyenda (negrita, cursiva, subrayado)
         3. Color del texto total (con opción de restablecer el color)
      2. Etiquetas de datos
         1. Cambia para mostrar la posición de la etiqueta: las opciones son «Exterior» o «Interior».
         2. Contenido de la etiqueta: elija entre las opciones Categoría, Valor y Porcentaje.
         3. Elija el tamaño de la fuente, el estilo (negrita, cursiva, subrayado) y el color
         4. Establecer colores automáticamente: asigna automáticamente colores a las barras en función de los datos y el tema seleccionados.
         5. Defina el contorno y el color de la etiqueta
      3. Leyenda
         1. Mostrar la leyenda
         2. Tamaño y estilo de fuente de la leyenda (negrita, cursiva, subrayado)
         3. Color del texto de la leyenda (con opción para restablecer el color)

Ejemplo: Gráfico circular

![gráfico circular](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rs-pie.png)

El gráfico circular admite fórmulas personalizadas y dimensiones de fórmulas. Para obtener más información, consulte [Fórmulas personalizadas.](../create-first/custom-formula.html "Las fórmulas personalizadas (también denominadas dimensiones de fórmula) le permiten definir nuevas dimensiones calculadas utilizando campos existentes en su modelo de datos. Esto permite realizar análisis más profundos y obtener información más detallada sin necesidad de realizar cambios en el conjunto de datos o el esquema subyacentes.")
