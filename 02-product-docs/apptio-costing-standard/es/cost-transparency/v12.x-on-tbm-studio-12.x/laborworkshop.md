---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Taller laboral"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/laborworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Taller laboral

## Preparación de los datos laborales

Puede ponerse manos a la obra y preparar su trabajo revisando los siguientes puntos de control:

1. Si aún no lo has hecho, carga tus datos Laborales incluyendo:
   - Efectivos reales
   - Plantilla prevista
2. Siguiendo las prácticas habituales de Apptio prácticas habituales, clasifique cada conjunto de datos brutos en la categoría de Trabajo.
3. Si procede, aplique un filtro de fechas a sus datos laborales.

## Acerca del identificador laboral

Anteriormente, el identificador del conjunto de datos maestros de mano de obra se rellenaba automáticamente. Esto cambió en R12 y ahora debe asignar un campo a esta columna en el conjunto de datos maestros de mano de obra. Considere hasta qué punto necesita que los datos sean granulares y establezca su identificador en consecuencia. Por ejemplo, si está calculando los costes a nivel de empleado, asigne el ID de empleado al ID de mano de obra.

Es posible que prefiera que el identificador sea el número de identificación del empleado, como en el ejemplo anterior. Sin embargo, no existen informes estándar que muestren ese nivel de detalle. Los informes basan los datos en atributos como el centro de costes, la función u otra información, así que considere la posibilidad de asignar estas combinaciones en la clave para los clientes más grandes o si el ID es demasiado sensible para mostrarlo en el modelo.

## Acerca de las Claves del Trabajo

Las claves para el conjunto de Datos Maestros de Mano de Obra son todas generadas por el sistema y no deben ser alteradas.

| Clave | La clave de campo se basa en | Lógica |
| --- | --- | --- |
| **Coste Fuente\_Labor Clave** | Coste CenterCost PoolCost Sub Pool  Fuente de costes Metacampo clave | Añada el texto Clave de mano de obra al metacampo Centro de coste, Pool de costes, Subpool de costes y Clave de origen de costes |
| **Clave de proyecto laboral** | Definido por el usuario durante la asignación | Considere la posibilidad de utilizar el código de proyecto, ya que debe vincular el objeto Trabajo y el objeto Proyectos en el modelo |
| **Clave de Recursos Laborales** | Torre de recursos informáticos  Subtorre de recursos informáticos | Añadir el texto Recurso\_Trabajo a la Torre de Recursos Informáticos y a la Subtorre de Recursos Informáticos |
| **Clave de seguimiento Labor\_Time** | Identificación laboral | Añadir el texto Labor\_Time Tracking al ID de Labor |

## Asignar datos a los datos maestros de personal

Asigne sus datos laborales al conjunto de datos maestros laborales. La mayor parte de la cartografía debería explicarse por sí misma en este punto.

Si establece su identificador en el ID del empleado, asigne **=1** al campo Recuento laboral. Si ha utilizado otro identificador (como el centro de coste), asigne el campo de recuento de personal de su conjunto de datos al campo Recuento de personal.

Al asignar el recuento planificado, asegúrese de asignar el valor del recuento al campo Recuento planificado (en lugar de al campo Recuento). En 12.7 ahora puede aprovechar la función Column Map en su conjunto de datos brutos para asignar a los datos maestros de mano de obra ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(se abre en una pestaña o una ventana nueva)") )

Puntos a tener en cuenta:

- Asigne su conjunto de datos laborales al conjunto de datos maestros laborales.

## Revisar el objeto Labor en los modelos

| Modelo | Acciones |
| --- | --- |
| **Coste** | Asegúrese de que los valores fluyen hacia el objeto Labor.  Las claves que unen los dos conjuntos de datos incluyen Centro de Coste, Pool de Coste, Sub Pool de Coste y Metacampo Clave de Fuente de Coste.  Es posible que tenga que ajustar la asignación para ponderar por otro valor si su identificador único no era el ID individual del empleado. |
| **Presupuesto** | Asegúrese de que los valores fluyen hacia el objeto Labor.  Las claves que unen los dos conjuntos de datos incluyen Centro de Coste, Pool de Coste, Sub Pool de Coste y Metacampo Clave de Fuente de Coste.  Es posible que tenga que ajustar la asignación para ponderar por otro valor si su identificador único no era el ID individual del empleado. |
| **Previsión** | Asegúrese de que los valores fluyen hacia el objeto Labor.  Las claves que unen los dos conjuntos de datos incluyen Centro de Coste, Pool de Coste, Sub Pool de Coste y Metacampo Clave de Fuente de Coste.  Es posible que tenga que ajustar la asignación para ponderar por otro valor si su identificador único no era el ID individual del empleado. |
| **CapEx** | Asegúrese de que los valores fluyen hacia el objeto Labor.  Las claves que unen los dos conjuntos de datos incluyen Centro de Coste, Pool de Coste, Sub Pool de Coste y Metacampo Clave de Fuente de Coste.  Es posible que tenga que ajustar la asignación para ponderar por otro valor si su identificador único no era el ID individual del empleado. |
| **CapEx Presupuesto** | Asegúrese de que los valores fluyen hacia el objeto Labor.  Las claves que unen los dos conjuntos de datos incluyen Centro de Coste, Pool de Coste, Sub Pool de Coste y Metacampo Clave de Fuente de Coste.  Es posible que tenga que ajustar la asignación para ponderar por otro valor si su identificador único no era el ID individual del empleado. |
| **Previsión de inversiones** | Asegúrese de que los valores fluyen hacia el objeto Labor.  Las claves que unen los dos conjuntos de datos incluyen Centro de Coste, Pool de Coste, Sub Pool de Coste y Metacampo Clave de Fuente de Coste.  Es posible que tenga que ajustar la asignación para ponderar por otro valor si su identificador único no era el ID individual del empleado. |

Las torres de TI aún no se han asignado, por lo que todavía no fluirán valores al objeto Torres de recursos de TI.

## Revisar los informes laborales

Los siguientes informes se actualizan después de haber configurado el objeto Trabajo:

- Revisión laboral
- Revisión laboral - Detalles
- Análisis laboral
- Dimensiones de los datos - Mano de obra
- Validez laboral

Para ver los detalles de estos informes (incluida la navegación, las funciones, los objetivos y las preguntas a las que responde cada informe), consulte la Guía del usuario de Costing Standard disponible en la Ayuda en línea.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
