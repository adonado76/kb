---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos de barras"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Visualizaciones"
source_path: "studio/report-studio/visualizations/rs-bar.html"
images:
  - "resources/images/studio_images/rs-bar.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de barras

Un gráfico de barras muestra los valores como barras horizontales, lo que facilita la comparación de métricas entre categorías. Los gráficos de barras son especialmente eficaces cuando se comparan valores entre muchas categorías.

## Cuándo utilizar un gráfico de barras

Utiliza un gráfico de barras cuando quieras:

- Compare valores entre múltiples categorías
- Clasificar las categorías de mayor a menor
- Resalte las diferencias claramente de un vistazo

## Añadir un gráfico de barras a un informe

1. Añadir un gráfico de barras desde el panel Visualizaciones de la barra de herramientas
2. Haga clic en el gráfico de barras para habilitar los paneles Datos y Formato.
3. Panel de datos
   1. Seleccione el objeto modelo en el menú desplegable
   2. Categorías: define cómo se agrupan los datos a lo largo del eje utilizando una dimensión. Haga clic aquí o arrastre para añadir dimensiones desde el Explorador de dimensiones
   3. Valores: especifica la métrica o métricas que se muestran como barras
   4. Leyenda: divide los valores en varias series basadas en una dimensión.
   5. Filtros: limita los datos que se muestran en el gráfico según las condiciones seleccionadas
   6. Resultados a mostrar: indique el número de barras que desea mostrar
   7. Configurar ordenación: controla el orden de las barras por valor en orden ascendente o descendente.
4. Panel de formato
   1. Propiedades generales: consulte [Propiedades de los componentes.](../components/components.html#abt-comp__comprop)
   2. Propiedades específicas del gráfico de barras
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
      4. Barras
         1. Acolchado entre barras (grosor de las barras)
         2. Relleno entre grupos (espacio entre grupos)
      5. Etiquetas de datos
         1. Alternar para mostrar las etiquetas de datos: las opciones son dentro o fuera de la barra.
         2. Elija el tamaño de la fuente, el estilo (negrita, cursiva, subrayado) y el color
         3. Establecer colores automáticamente: asigna automáticamente colores a las barras en función de los datos y el tema seleccionados.
         4. Defina el contorno y el color de la etiqueta

Ejemplo: Gráfico de barras

![ejemplo de diagrama de barras](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rs-bar.png)

Los gráficos de barras admiten fórmulas personalizadas y dimensiones de fórmulas. Para obtener más información, consulte [Fórmulas personalizadas.](../create-first/custom-formula.html "Las fórmulas personalizadas (también denominadas dimensiones de fórmula) le permiten definir nuevas dimensiones calculadas utilizando campos existentes en su modelo de datos. Esto permite realizar análisis más profundos y obtener información más detallada sin necesidad de realizar cambios en el conjunto de datos o el esquema subyacentes.")

Los gráficos de barras también admiten visualizaciones compatibles. Para obtener más información, consulte [Visualizaciones compatibles](visualizations.html#abt-visual__compvis).

## Gráficos de barras apiladas

Los gráficos de barras se pueden convertir en barras apiladas para mostrar las contribuciones de las subcategorías dentro de cada categoría, manteniendo visible el valor total.
