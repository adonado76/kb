---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función bala"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/bullet.html"
images:
  - "resources/images/studio_images/studioimages/studio_bullet_max.png"
  - "resources/images/studio_images/studioimages/studio_bullet_secondsplit.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función bala

◆ Se aplica a: TBM Studio v12.3.4 y posteriores

La función Viñeta permite generar un gráfico de viñetas dentro de una tabla.

## Dónde utilizarlo

La función Viñeta puede utilizarse en las columnas Fórmula de las tablas de los informes.

## Sintaxis

- **Sintaxis base** - Si no está seguro, empiece con esta sintaxis: `=Bullet(performance_measure)`
- **Sintaxis completa** - Esta sintaxis le permite anular muchos valores predeterminados y comportamientos que afectan a la representación del gráfico de viñetas: `=Bullet(performance_measure,[target|min|max|firstSplit|secondSplit=Expression()]*)`

## Argumentos

`performance_measure`

Este argumento obligatorio debe ser el nombre de una columna numérica. Será el valor principal que muestre el gráfico de viñetas.

Guía visual:

![Argumentos](../../../resources/images/studio_images/studioimages/studio_bullet%20function_performance%20measure.png)

## Argumentos opcionales

Se pueden pasar uno o más argumentos opcionales como pares argumento=valor. Esto le permite anular los ajustes que desee, dejando otros ajustes en su comportamiento por defecto.

| Argumento | Valor predeterminado | Significado | Guía visual |
| --- | --- | --- | --- |
| **destino** | Sólo se muestra si se especifica. | Cuál es el valor de la medida comparativa que debe mostrar el gráfico de viñetas, si lo hay. La medida comparativa se representa como una línea roja vertical. | destino |
| **Mín** | El valor más pequeño de la columna para performanceMeasure, o el objetivo especificado. Esto utiliza sólo los valores de la propia tabla mostrada, no las filas que han sido filtradas. | Cuál es el valor mínimo en la escala de los gráficos. | valor mínimo |
| **Máx** | El mayor valor en performanceMeasure, o en el objetivo especificado. Esto utiliza sólo los valores de la propia tabla mostrada, no las filas que han sido filtradas. | Cuál es el valor máximo en la escala de los gráficos. | valor máximo |
| **firstSplit** | (máx.-mín.) \* 0.6 | Cuál es el valor en el que se debe dibujar la caja de fondo más a la izquierda. | primera división |
| **secondSplit** | (máx.-mín.) \* 0.8 | Cuál es el valor al que debe dibujarse la caja de fondo central. | segunda división |

## Señales

Los gráficos de viñetas permiten un valor mínimo negativo y un valor máximo positivo. El gráfico de viñetas se representará igual que si tomara todos los números y les añadiera una cantidad que hiciera que todos tuvieran el mismo signo.

## Ejemplos

En esta sección se ofrecen ejemplos de utilización de la función Viñeta.

**Mostrar Coste** - Esta función de viñetas crea un sencillo gráfico de viñetas que muestra el Coste. El Mínimo y el Máximo se establecerán en función del rango de valores dentro de la columna mostrada.

`=bullet(Cost)`

![ejemplo de gráfico de viñetas](../../../resources/images/studio_images/studioimages/studio_bullet%20function_example%20bullet%20chart.png)

**Comparar Coste con Presupuesto** - Este es un ejemplo que muestra el Coste como medida de rendimiento, y muestra la métrica del presupuesto como sería el objetivo:

`=Bullet(Cost,target=Budget)`

![Comparar el coste con el presupuesto](../../../resources/images/studio_images/studioimages/studio_bullet_compare%20cost%20to%20budget.png)

**Desactivar la** división de fondo - Este ejemplo desactivará las divisiones de fondo siempre que sus gráficos de viñetas contengan sólo números positivos.

`=Bullet(Cost,firstSplit=0,secondSplit=0)`

![Desactivar la división en segundo plano](../../../resources/images/studio_images/studioimages/studio_bullet%20func_table.png)

**Comparar un valor gráfico con 0** - Cuando se calcula una desviación presupuestaria, su signo indica si se está por encima o por debajo del presupuesto. Un gráfico Bullet puede configurarse para representar el valor con signo relativo a 0.

`=Bullet(Variance,Target=0)`

![Comparar un valor gráfico](../../../resources/images/studio_images/studioimages/studio_bullet%20function_simple%20bullet.png)

**Superponer información estadística** - Este ejemplo combina la función Viñeta con la función Percentil. Muestra un gráfico de viñetas en el que un tercio de los valores están a la izquierda de la primera división y un tercio de los valores están a la derecha de la segunda división.

`=Bullet(Cost,Target=0,firstSplit=Percentile(Cost,33),secondSplit=Percentile(Cost,66))`

![Información estadística superpuesta](../../../resources/images/studio_images/studioimages/studio_bullet%20function_table.png)
