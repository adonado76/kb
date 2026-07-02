---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Métodos de asignación de costes"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Fundamentos de la TBM"
source_path: "studio/new-uc/concepts-architecture/cost-allocation-method.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Métodos de asignación de costes

La asignación de costes es el proceso de distribuir los costes desde su origen hasta los servicios y los consumidores que se benefician de ellos. Elegir la metodología de asignación adecuada es una de las decisiones más importantes en la implementación de su sistema TBM, ya que determina el grado de precisión con el que su modelo de costes refleja la realidad.

## Asignación directa

**Definición**

La asignación directa imputa los costes que son clara y exclusivamente atribuibles a un único destinatario. No es necesario compartir ni dividir, ya que la relación entre el coste y el consumidor es de uno a uno.

**Cuándo se utiliza** 

- Un coste se asigna a una sola aplicación, servicio o unidad de negocio
- Una factura de proveedor corresponde a un solo cliente
- Un recurso es utilizado exclusivamente por una entidad

**Ventajas y desventajas**

|  |  |
| --- | --- |
| **Ventajas** | **Desventajas** |
| Máxima precisión: sin estimaciones | Solo se aplica a los recursos dedicados |
| Fácil de explicar y defender | La mayoría de los costes de TI son compartidos, lo que limita su aplicabilidad |
| No se requieren datos del conductor | No admite infraestructura compartida |

**Ejemplo**

Un servidor de bases de datos dedicado que solo ejecuta la aplicación CRM tiene un coste de alojamiento de $5,000/month. Este coste se imputa directamente al servicio de CRM sin necesidad de desglosarlo.

Nota:

**Por qué es importante en TBM Studio**

En TBM Studio, la asignación directa se lleva a cabo mediante una correspondencia uno a uno en la configuración de asignación. Cuando el registro de origen tiene un identificador único que se asigna directamente a un único destino, los costes se transfieren sin dividirse. Esto se configura en el Modelador de objetos individuales de Model Studio utilizando condiciones de coincidencia exacta en campos como el ID de la aplicación o el ID del proveedor.

## Asignación indirecta

**Definición**

La asignación indirecta distribuye los costes que se reparten entre varios destinatarios. Dado que el beneficio económico redunda en más de un consumidor, es necesario un método para determinar la parte que le corresponde a cada uno.

**Cuándo se utiliza** 

- La infraestructura se comparte entre varias aplicaciones o unidades de negocio
- Los costes no pueden atribuirse a un único consumidor (por ejemplo, redes compartidas, instalaciones de centros de datos)
- Un equipo presta varios servicios al mismo tiempo

**La necesidad de factores determinantes de la asignación**

La asignación indirecta requiere un criterio de reparto, es decir, un indicador cuantificable que determine cómo distribuir los costes entre los consumidores. La calidad de tu asignación indirecta depende directamente de hasta qué punto tu factor determinante refleja los patrones de consumo reales. Elegir el controlador adecuado es tanto un arte como una ciencia.

**Ejemplo**

Un centro de datos compartido supone un gasto de $500,000/month en instalaciones (electricidad, refrigeración y espacio físico). Este coste se distribuye entre las granjas de servidores ubicadas en el centro de datos en función del espacio de rack ocupado. Si la granja de CRM ocupa el 30 % del espacio en los racks, se le asignan 150 000 dólares del coste de las instalaciones.

## Asignación basada en controladores

**¿Qué es un controlador?**

Un factor determinante es un indicador cuantificable que determina cómo se distribuyen los costes compartidos entre los destinatarios. Los factores determinantes representan la relación causal entre un coste y sus consumidores; responden a la pregunta: «¿Por qué este consumidor asume esta parte del coste?»

**Tipos de controladores habituales**

|  |  |  |
| --- | --- | --- |
| **Tipo de controlador** | **Descripción** | **Ideal para** |
| Plantilla / ETC | Número de empleados o equivalentes a tiempo completo | Informática para usuarios finales, servicio de asistencia técnica, licencias de « SaaS » |
| Volumen de transacciones | Número de transacciones procesadas | Alojamiento de aplicaciones, middleware, servicios de procesamiento |
| Consumo de almacenamiento | GB o TB de almacenamiento utilizado | Infraestructura de almacenamiento, servicios de copia de seguridad |
| CPU / Uso de recursos | Núcleos de CPU, horas de « vCPUs, » o horas de cálculo consumidas | Infraestructura de servidores, computación en la nube |
| Número de usuarios | Número de usuarios activos de un servicio | Licencias de aplicaciones, servicios por usuario |
| Ingresos / Presupuesto | Indicadores financieros de la entidad consumidora | Asignación de gastos generales (la menos precisa) |

**Elegir los controladores adecuados**

  

El mejor conductor tiene tres cualidades:

- **Relación causal:** El factor determinante debe reflejar la causa real del coste. El número de servidores influye más en los costes de computación que el número de empleados.
- **Disponibilidad de los datos:** Los datos del conductor deben estar disponibles de forma fiable en cada periodo. Un controlador perfecto que no puedas instalar no sirve de nada.
- **Proporcionalidad:** El conductor debe tener en cuenta el consumo relativo. Si la aplicación A utiliza el triple de recursos de computación que la aplicación B, el valor de su controlador debería ser aproximadamente tres veces mayor.

**Consideraciones sobre la calidad de los datos de los conductores**

- Los controladores deben ser numéricos. Los valores no numéricos en una columna de ponderación provocan errores de asignación en TBM Studio.
- No se admiten valores negativos para el controlador, ya que provocarán un error en la asignación.
- La falta de datos de control para una entidad de destino da lugar a costes no asignados; dichos costes permanecen en la fuente hasta que se resuelvan.
- Los datos de los conductores deben actualizarse cada período para reflejar los patrones de consumo actuales.

Nota:

Por qué es importante en TBM Studio

En TBM Studio, los controladores se configuran en el Modelador de objetos individuales de Model Studio. Cada asignación especifica una métrica de origen, una columna de ponderación (el factor determinante) y las condiciones de coincidencia que vinculan las filas de origen con las filas de destino. Hay tres opciones de ponderación disponibles: Tabla (valores del conjunto de datos de destino), Métrica (proporcional a la asignación de otra métrica) y Otro factor (valores de una tabla de factores independiente). Comprueba siempre la calidad de los datos de los conductores antes de ejecutar las asignaciones.

## Contabilidad de costes por actividades (ABC)

**Descripción general del concepto**

El sistema de contabilidad de costes por actividades asigna los costes en función de las actividades específicas que se llevan a cabo para prestar un servicio. En lugar de utilizar un simple ratio (como el número de empleados), el método ABC identifica las actividades concretas que intervienen en la prestación de servicios y asigna los costes en función del volumen de cada actividad consumida.

**Cuándo es adecuado el método ABC**

- Dispone de servicios muy variados con diferentes estructuras de costes
- Los factores simples no reflejan con precisión la causalidad de los costes
- Para tomar decisiones sobre precios, es necesario disponer de un cálculo de costes por nivel de servicio muy preciso

## La disyuntiva entre complejidad y precisión

El método ABC ofrece la mayor precisión en la asignación, pero requiere un esfuerzo considerablemente mayor en cuanto a la recopilación y el mantenimiento de datos. Para la mayoría de las organizaciones, la asignación basada en factores determinantes ofrece una precisión suficiente con una carga administrativa mucho menor. Considera el método ABC para tus servicios más costosos o más críticos, y utiliza métodos más sencillos en el resto de casos.

Sugerencia:

Empieza con métodos de asignación más sencillos y ve aumentando su complejidad con el tiempo. Muchas organizaciones comienzan con indicadores basados en el número de empleados o incluso en los ingresos, y a medida que su práctica de gestión del gasto en tecnología (TBM) va madurando, pasan progresivamente a indicadores más precisos basados en el consumo. TBM Studio facilita este proceso: puedes cambiar los controladores sin necesidad de reestructurar el modelo.
