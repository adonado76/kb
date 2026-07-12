---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Asignaciones de recursión"
breadcrumb: []
source_path: "studio/model_studio/recursion-allocations.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu594.png"
  - "resources/images/studio_images/studioimages/studio_distributing_evenly.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Asignaciones de recursión

**Se aplica a** : TBM Studio 12.0 y posteriores

La premisa básica de la asignación recursiva es que algún valor permanece en una o más de las unidades objetivo después de cada iteración. Con cada iteración, el valor en las unidades de destino aumenta y el valor restante en las unidades de origen disminuye hasta que queda una cantidad mínima en las unidades de origen.

En una asignación por recursión, los objetos de origen y destino deben tener unidades idénticas.

Al definir una asignación recursiva, se establecen tres parámetros:

- **Precisión** - Especifica el valor mínimo que debe existir en la tabla de origen para que se ejecute una asignación Recursiva. Si el valor cae por debajo del mínimo, no se realizarán más iteraciones. El valor es la cantidad total movida para la iteración, no una cantidad por fila.
- **Número máximo de iteraciones** - Especifica el número máximo de veces que se repetirá la asignación. Si se alcanza el valor de precisión antes de que se haya realizado el número máximo de iteraciones, no se realizarán las iteraciones restantes.
- **Usar modo incremental** - Cuando está marcada, el valor de origen de cada iteración es el total del valor original más el valor asignado al objetivo de la iteración anterior. Cuando se comprueba al final de la recursión, el valor total de ambos objetos será mayor que el valor de la fuente original.

## Se requieren tablas de origen y destino únicas

Puede tener varias asignaciones recursivas en un modelo, pero cada asignación recursiva debe tener tablas de origen y destino únicas y no deben solaparse. Por ejemplo, supongamos que tiene cinco tablas en un modelo:

> A -> B -> C -> D -> E -> F

Podría crear asignaciones Recursivas entre las tablas A y C y las tablas D y F, pero no podría crear una tercera asignación Recursiva entre las tablas B y E. La tercera asignación se solaparía con las dos primeras.

## Cómo funciona la asignación recursiva

La premisa básica de la asignación recursiva es que algún valor permanece en una o más de las unidades objetivo después de cada iteración. Con cada iteración, el valor en las unidades de destino aumenta y el valor restante en las unidades de origen disminuye hasta que queda una cantidad mínima en las unidades de origen.

Por ejemplo, suponga que tiene una tabla de origen y una tabla de destino cada una con las siguientes unidades:

- Región Occidental
- Región central
- Región Oriental

  -----------------------------------
- Servicio de asistencia
- Servicio de servidores
- Servicio telefónico

Las regiones occidental, central y oriental se asignan a sí mismas el 100% de su valor. Los servicios de Help Desk, Servidores y Teléfono asignan su valor a las tres regiones, así como entre sí. Supongamos que el 10% de los costes de servicio se asignan a las tres regiones en cada iteración. El 90% restante de los costes de los servicios se reparten entre ellos.

Tras la primera iteración, el 10% del coste de los servicios se ha asignado a las regiones, lo que deja el 90% del coste en los servicios. Tras la iteración dos, algo menos del 20% del coste se ha asignado a las regiones, lo que deja algo más del 80% del coste en los servicios. Las iteraciones continúan hasta que se ha completado el número especificado de iteraciones, o la cantidad restante en los servicios ha caído por debajo del valor introducido en el campo **Precisión**. Con cada iteración, aumenta el valor total de las regiones y disminuye el de los servicios.

## Requisitos

Los siguientes son los requisitos para una asignación recursiva:

- La tabla de origen y la tabla de destino deben tener unidades idénticas
- Algún valor debe permanecer en una o más de las unidades objetivo después de cada iteración

## Directrices

Las asignaciones recursivas requieren mucha más capacidad de procesamiento que las asignaciones estándar. Mantener los plazos de tramitación dentro de lo razonable:

- Utilizar un número limitado de asignaciones recursivas en un modelo determinado
- Utilizar el menor número posible de iteraciones
- Ajuste el valor de precisión lo más alto posible

## Opciones de distribución

Hay tres opciones de distribución:

- Incluso
- Peso por
- Relación de datos

## Incluso

La opción **Par** es la opción por defecto y está en vigor cuando las opciones **Ponderar por** y **Relación de datos** no están seleccionadas.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_distributing_evenly.png)

Distribuye la asignación uniformemente entre todas las unidades identificadas en la tabla de destino por la propiedad **A.** Por ejemplo, si hay una tabla de destino de solicitudes con cinco solicitudes y se están asignando 100.000 dólares, se asignarán 20.000 dólares a cada solicitud.

## Peso por

La opción **Ponderar por** distribuye la asignación en función de la proporción (tamaño relativo) de los valores de una columna seleccionada.

Por ejemplo, supongamos que hay cinco aplicaciones con distintos números de usuarios, como se muestra en la tabla siguiente, y que se asignan 100.000 dólares. Desea ponderar la distribución por el número de usuarios. Los 100.000 $ se distribuirían como se indica a continuación en la columna **Asignación** :

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu594.png)

Nota: Si intenta ponderar una asignación por una columna numérica que contiene al menos un valor no numérico, la ponderación será ignorada. Para corregir el problema, elimine los valores no numéricos de la columna.

## Relación de datos

La opción **Relación de datos** distribuye la asignación uniformemente entre las unidades que hacen coincidir los valores de una columna de la tabla de origen con los valores de una columna de la tabla de destino. Por ejemplo, supongamos que la tabla de origen incluye información sobre las aplicaciones. Tanto la tabla de origen como la de destino incluyen una columna de **Categoría de aplicación**. Una de las categorías se identifica como **Bases de Datos**, pero hay dos aplicaciones de bases de datos: Oracle y SAP. El valor de las entradas de la base de datos de la tabla de origen se agregaría y se asignaría uniformemente a las entradas de la base de datos de la tabla de destino. Si se asignaran 20.000 dólares, se dividirían en 10.000 para Oracle y 10.000 para SAP.

Puede especificar más de una relación. Si especifica más de una relación, todas las relaciones deben coincidir para que se asigne el valor.
