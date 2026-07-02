---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Mapas de árboles"
breadcrumb: []
source_path: "studio/reports/tree-map.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep334.png"
  - "resources/images/studio_images/studioimages/studio/stu559.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Mapas de árboles

**Se aplica a** : TBM Studio 12.0 y posteriores

Una de las mejores formas de representar las proporciones relativas de los valores es utilizar un mapa arbóreo. Los mapas de árbol muestran rectángulos anidados que representan datos jerárquicos (estructurados en forma de árbol). En la siguiente imagen se muestra un ejemplo de mapa de árboles:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep334.png)

## Visualizar valores en un mapa de árbol

Un mapa de árbol puede mostrar un único valor, como el coste, o puede comparar dos valores, como el plan presupuestario y los datos reales. Cuando se comparan valores, se utiliza el color para indicar la variación entre los valores. Se muestra una escala para ayudarle a juzgar el grado de la variación.

El porcentaje de varianza se calcula restando el segundo valor del primer valor y dividiendo el resultado por el segundo valor. Por ejemplo, suponga que tiene los siguientes datos:

| Unidad de negocio | Coste | Presupuesto | Varianza |
| --- | --- | --- | --- |
| Ventas | 1.000 | 800 | -20 % |
| Marketing | 2.000 | 2100 | 5 |
| I+D | 3000 | 2.700 | -11 % |
| Soporte | 2.500 | 2.800 | 11 % |
| Ingeniería | 1.500 | 1.500 | 0 % |

El gráfico se crea utilizando la configuración que se muestra en la siguiente imagen:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu559.png)

## Crear un mapa de árboles

Para crear un mapa de árbol:

1. Crea una tabla.
2. Seleccione **Mapa del Árbol** en la pestaña **Ad Hoc**.
3. Utilice las opciones de la pestaña **Mapa del Árbol** para configurar el mapa.

Nota: La visualización del Mapa del Árbol admite hasta 4 columnas en la leyenda.
