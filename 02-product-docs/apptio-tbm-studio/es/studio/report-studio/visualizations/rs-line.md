---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos de líneas"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Visualizaciones"
source_path: "studio/report-studio/visualizations/rs-line.html"
images:
  - "resources/images/studio_images/rs-line.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de líneas

Un gráfico de líneas muestra puntos de datos conectados por líneas, lo que lo hace ideal para mostrar tendencias, patrones y cambios a lo largo del tiempo. Es más adecuado para datos continuos o categorías secuenciales.

## Cuándo utilizar un gráfico de líneas

Utilice un gráfico de líneas cuando desee:

- Mostrar tendencias a lo largo del tiempo o categorías secuenciales
- Compare varias series para analizar correlaciones o patrones
- Resaltar aumentos, disminuciones o fluctuaciones en los datos

## Añadir un gráfico de líneas a un informe

1. Añadir un gráfico de líneas desde el panel Visualizaciones de la barra de herramientas
2. Haga clic en el gráfico de líneas para habilitar los paneles Datos y Formato.
3. Panel de datos
   1. Seleccione el objeto modelo en el menú desplegable
   2. Categorías: define el eje X, normalmente una dimensión basada en el tiempo o secuencial. Haga clic aquí o arrastre para añadir dimensiones desde el Explorador de dimensiones
   3. Valores: especifica la(s) métrica(s) que se muestran como puntos de datos conectados por líneas
   4. Leyenda: divide los valores en varias series basadas en una dimensión.
   5. Filtros: limita los datos que se muestran en el gráfico según las condiciones seleccionadas
   6. Resultados a mostrar: indique el número de líneas que desea mostrar
   7. Configurar ordenación: controla el orden de las categorías en el eje X.
4. Panel de formato
   1. Propiedades generales: consulte [Propiedades de los componentes.](../components/components.html#abt-comp__comprop)
   2. Propiedades específicas del gráfico de líneas
      1. Categorías
         1. Mostrar título de la categoría
         2. Mostrar etiquetas de categoría
         3. Elija el tamaño de la fuente, el estilo (negrita, cursiva, subrayado) y el color
         4. Alternar para cambiar la posición de las categorías
         5. Mostrar líneas de cuadrícula
      2. Valores
         1. Mostrar título de valores
         2. Mostrar etiquetas de valores
         3. Elija el tamaño de la fuente, el estilo (negrita, cursiva, subrayado) y el color
         4. Alternar para invertir el rango
         5. Mostrar líneas de cuadrícula
      3. Leyenda
         1. Mostrar la leyenda
         2. Tamaño y estilo de fuente de la leyenda (negrita, cursiva, subrayado)
         3. Color del texto de la leyenda (con opción para restablecer el color)
      4. Líneas
         1. Elija el color y el estilo de la línea
      5. Etiquetas de datos
         1. Alternar para mostrar las etiquetas de datos: centro, derecha, izquierda
         2. Elija el tamaño de la fuente, el estilo (negrita, cursiva, subrayado) y el color
         3. Establecer colores automáticamente: asigna automáticamente colores a las barras en función de los datos y el tema seleccionados.
         4. Defina el contorno y el color de la etiqueta

Ejemplo: Gráfico de líneas

![gráfico de líneas](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rs-line.png)

Los gráficos de líneas admiten fórmulas personalizadas y dimensiones de fórmulas. Para obtener más información, consulte [Fórmulas personalizadas](../create-first/custom-formula.html "Las fórmulas personalizadas (también denominadas dimensiones de fórmula) le permiten definir nuevas dimensiones calculadas utilizando campos existentes en su modelo de datos. Esto permite realizar análisis más profundos y obtener información más detallada sin necesidad de realizar cambios en el conjunto de datos o el esquema subyacentes.").

Los gráficos de líneas también admiten visualizaciones compatibles. Para obtener más información, consulte [Visualizaciones compatibles](visualizations.html#abt-visual__compvis).
