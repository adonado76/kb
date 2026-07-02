---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Límite de trayectoria del modelo"
breadcrumb: []
source_path: "studio/troubleshooting/model-pathing-limit.html"
images:
  - "resources/images/studio_images/troubleshooting/modelpath-1.png"
  - "resources/images/studio_images/troubleshooting/modelpath-10.png"
  - "resources/images/studio_images/troubleshooting/modelpath-11.png"
  - "resources/images/studio_images/troubleshooting/modelpath-2.png"
  - "resources/images/studio_images/troubleshooting/modelpath-3.png"
  - "resources/images/studio_images/troubleshooting/modelpath-4.png"
  - "resources/images/studio_images/troubleshooting/modelpath-5.png"
  - "resources/images/studio_images/troubleshooting/modelpath-6.png"
  - "resources/images/studio_images/troubleshooting/modelpath-7.png"
  - "resources/images/studio_images/troubleshooting/modelpath-8.png"
  - "resources/images/studio_images/troubleshooting/modelpath-9.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Límite de trayectoria del modelo

El limitador de trayectorias de modelos impide la creación y el cálculo de modelos que tengan un número muy elevado de trayectorias. El número de rutas de un modelo empezará a crecer exponencialmente a partir de cierto punto y empezará a tener un rendimiento y un tiempo de cálculo extremadamente degradados.

![trayectoria del modelo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-1.png)

Un camino consiste en la ruta que las unidades pueden seguir en un modelo desde la parte inferior (normalmente la fuente de costes) hasta cualquier objeto superior. El número de caminos son todas las permutaciones posibles que pueden tomar las unidades a lo largo de un modelo. A medida que aumenten los objetos y las asignaciones, el número de rutas empezará a crecer exponencialmente.

## Comprender las rutas del modelo

El siguiente modelo tiene un total de 15 trayectorias desde el Nivel 5 (arriba) hasta la Base de Objetos (abajo). El modelo se construyó para resaltar el número de caminos. Actualmente, no hay forma de mostrar este número en el modelo.

![trayectoria del modelo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-2.png)

Si se añade una línea de asignación entre el Nivel 3C y el Nivel 5, se añadirán 3 rutas adicionales al modelo, ya que hay 3 rutas hasta el Nivel 3C. Si trazas visualmente las rutas desde la Base de Objetos hasta el Nivel 3C, hay 3 rutas posibles.

![trayectoria del modelo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-3.png)

El componente de revisión del rendimiento generará una tabla que indicará el número de rutas y ayudará a identificar las áreas problemáticas.

En el siguiente modelo, hay un total de 60 caminos hacia la cima.

![trayectoria del modelo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-4.png)

La siguiente figura muestra el informe de trayectorias de este modelo.

![tabla de rutas del modelo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-5.png)

Para obtener el total de rutas a un objeto determinado, filtre por ese objeto en la categoría A objeto y, a continuación, sume las rutas a la parte inferior. Coincidirá con el modelo anterior (60).

![tabla de rutas del modelo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-6.png)

La columna Cantidad es el número de asignaciones entre A objeto y Desde objeto. El lugar ideal para empezar a investigar dónde se pueden eliminar o combinar asignaciones es el número de Cantidad más alto el más bajo en el modelo o en la tabla. Para este modelo, sería el par de Nivel 1A y Base de objetos. Hay más asignaciones entre el Nivel 5 y el Nivel 3C, pero al estar en la parte superior del modelo, tienen menos impacto.

![tabla de rutas del modelo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-7.png)

![tabla de rutas del modelo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-8.png)

Hay más líneas que van del nivel 3C al nivel 5, pero están más arriba en el modelo. Las asignaciones desde la Base de Objetos hasta el Nivel 1A generan 3 trayectorias por cada trayectoria por encima de ellas. Por lo tanto, reducir los caminos más abajo tiene un mayor impacto. La supresión de una de estas asignaciones reduce el recuento en 12 (20%).

![tabla de rutas del modelo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-9.png)

Eliminar una línea del Nivel 3C al Nivel 5 reduce el recuento en 10.

![tabla de rutas del modelo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-10.png)

Haciendo ambas cosas se obtiene una reducción de 20.

![tabla de rutas del modelo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/modelpath-11.png)

En resumen, el número de rutas de un modelo empezará a aumentar a un ritmo exponencial a medida que se añadan más objetos y asignaciones. En concreto, cuando se añade más de una asignación de salida desde un objeto, el número total de rutas en el modelo aumentará. A medida que aumente el número de objetos con más de 1 ruta de salida, aumentará el número de rutas. La única forma de reducir el número de rutas en un modelo es reducir el número de asignaciones que existen en un modelo. Para obtener ayuda para reducir el número de asignaciones en su modelo, póngase en contacto con su CSM.
