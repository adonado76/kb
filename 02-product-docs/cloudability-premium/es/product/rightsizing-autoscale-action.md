---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Acción de autoescalado para redimensionamiento"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/rightsizing-autoscale-action.html"
images:
  - "images/rightsizing-autoscale-instance-to-asg.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Acción de autoescalado para redimensionamiento

Un reto en la optimización de recursos es dimensionar correctamente las cargas de trabajo que presentan grandes fluctuaciones y picos. Como ilustran las grandes oscilaciones en los datos de las métricas de utilización (CPU, red, memoria y GPU), este escenario suele abordarse sobreaprovisionando el recurso para acomodar los picos más altos de estas cargas de trabajo, lo que se traduce en un exceso de gasto en la nube.

Para adaptar mejor los recursos informáticos a estas cargas de trabajo altamente elásticas, estamos mejorando la recomendación Autoscale. La acción Autoescalado recomienda convertir una única instancia en un Grupo de Autoescalado (ASG). En lugar de una única instancia de gran capacidad, el ASG consta de varias instancias más pequeñas que se activan y desactivan para satisfacer las demandas de esta carga de trabajo elástica. Si su carga de trabajo puede escalarse en varias máquinas, es una opción rentable.

**Uso de la recomendación de autoescala**

El panel de detalles muestra la lista de acciones recomendadas. Cuando se selecciona una acción de Autoescalado, se mostrarán los recuentos de instancias mínimo y máximo. Modelamos el seguimiento de objetivos a partir de los datos de utilización de CPU, red, memoria (si está disponible) y GPU (si está disponible) para derivar estos recuentos de instancias. La recomendación es para un ASG que va de 1 a 4 de tipo c4.4xlarge instancias en el siguiente ejemplo.

![autoescala captura de pantalla](../../../../03-media/cloudability-premium/images/rightsizing-autoscale-instance-to-asg.jpg)

Observando los gráficos de CPU y Memoria anteriores, fíjate en que la leyenda de la derecha representa el número de instancias. En este ejemplo, la línea de puntos amarilla se mueve entre 1 y 3, lo que indica que este rango es suficiente para cubrir la carga de trabajo. A la hora de determinar el número máximo de instancias, recomendamos el número de instancias que coincida con el tamaño de memoria de la instancia original. En concreto, la instancia actual c4.4xlarge tiene 30 GiB, mientras que la instancia recomendada c4.xlarge tiene 7.5 GiB memoria. El original tiene cuatro veces más memoria, por lo que recomendamos un número máximo de instancias que coincida con el límite superior. Recuerde que no se le cobrará por las instancias de un ASG que no estén activas, por lo que se trata de una opción rentable.

[Lea esto](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scaling-target-tracking.html "(se abre en una pestaña o una ventana nueva)") para obtener más información sobre las políticas de escalado de seguimiento de objetivos ASG y los detalles de implementación.

**Consideraciones**

He aquí una lista de cuestiones a tener en cuenta en este momento:

El riesgo se fija en un mínimo de 1, ya que no todas las cargas de trabajo son apropiadas para los ASG.

Los miembros del actual Grupo de Autoescalado quedan excluidos de este tipo de recomendación.

Por el momento sólo se admite Amazon EC2 ( Elastic Cloud Compute).

Quedan excluidas las familias ( T2, T3, T3a, y T4g ).

EC2 por defecto, las políticas de escalado dinámico de seguimiento de objetivos se activan en función de la utilización de la CPU, los bytes de entrada/salida de red o el recuento de peticiones del Application Load Balancer. Opcionalmente, se pueden utilizar otras métricas de Cloudwatch o personalizadas como desencadenantes, con una configuración adicional.

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
