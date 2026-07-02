---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Taller de control del tiempo"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/ttworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Taller de control del tiempo

## Preparación de los datos de Control Horario

1. Si aún no lo ha hecho, cargue sus datos de Seguimiento Horario incluyendo:
   - Lista de tareas
   - Horas trabajadas por empleado
2. Siguiendo las prácticas habituales de Apptio las prácticas habituales, clasifique cada conjunto de datos brutos en la categoría de Seguimiento del tiempo:
3. Si procede, aplique un filtro de fechas a sus datos de seguimiento del tiempo:

## Acerca del identificador de seguimiento del tiempo

El identificador del objeto de Control Horario está predefinido y no debe modificarse. Incluye:

- Identificación laboral
- ID de tarea
- ID de proyecto

## Acerca de las teclas de control del tiempo

Las claves para el conjunto de Datos Maestros de Control Horario son todas generadas por el sistema y no deben ser alteradas.

| Clave | La clave de campo se basa en | Lógica |
| --- | --- | --- |
| **Clave de seguimiento Labor\_Time** | Identificación laboral | Añadir el texto Labor\_Time Tracking con Labor ID |
| **Cronometraje\_Proyecto Clave** | ID de proyecto | Añada el texto Time Tracking\_Project con el ID del proyecto |
| **Seguimiento del tiempo\_Clave de la torre de TI** | Torre de recursos informáticos  Subtorre de recursos informáticos | Añada el texto Time Tracking\_IT Tower Key con IT Resource Tower y IT Resource Sub Tower |

Al asignar el ID del empleado al ID de la mano de obra, el sistema establecerá automáticamente una conexión entre los objetos de la mano de obra y del seguimiento del tiempo. Cuando se establezca esta conexión, el coste de ese empleado fluirá al objeto de Control Horario, pero será más granular, ya que ahora se dividirá en función de las actividades para las que el empleado esté realizando el seguimiento de horas.

## Columnas computadas comunes necesarias para el seguimiento del tiempo

A menudo no existe una lista única de tareas y todos los metadatos sobre esas tareas. Es posible que tenga que extraer datos de uno o varios sistemas. Siempre que el ID de la tarea sea el mismo en los distintos sistemas, puede utilizar la función LOOKUP para trasladar la información relacionada con la tarea, como las horas reales o las horas planificadas, a un único conjunto de datos (como la lista original de tareas de un proyecto).

## Asignar datos a los datos maestros de seguimiento del tiempo

Asigne sus datos de seguimiento horario al conjunto de datos maestros de seguimiento horario. La mayor parte de la cartografía debería explicarse por sí misma en este punto. No hay requisitos cartográficos inusuales. En 12.7 ahora puede aprovechar la función Mapa de columnas en su conjunto de datos sin procesar para asignarlos a los datos maestros de seguimiento de tiempo ( [Mapear columnas](https://community.apptio.com/docs/DOC-10561 "(se abre en una pestaña o una ventana nueva)") )

## Revisar el objeto de Control Horario en los modelos

| Modelo | Acciones |
| --- | --- |
| Coste | Asegúrese de que los valores fluyen hacia el objeto de Control Horario.  De la mano de obra a la gestión de tiempos, asigne utilizando la referencia basada en datos. También puede asignar desde Seguimiento del tiempo a las torres de TI según sea necesario.  Desde Control Horario, puede asignar a Proyectos en función del ID del proyecto. Lo ideal es asignar utilizando la Referencia basada en datos. Si no puede utilizar una referencia basada en datos, comente sus opciones con su asesor. |
| Presupuesto | Asegúrese de que los valores fluyen hacia el objeto de Control Horario.  De la mano de obra a la gestión de tiempos, asigne utilizando la referencia basada en datos. También puede asignar desde Time Tracking a IT Towers según sea necesario[ VM1 ].  Desde Control Horario, puede asignar a Proyectos en función del ID del proyecto. Lo ideal es asignar utilizando la Referencia basada en datos. Si no puede utilizar una referencia basada en datos, comente sus opciones con su asesor. |
| CapEx | Asegúrese de que los valores fluyen hacia el objeto de Control Horario.  Del objeto Mano de obra al objeto Seguimiento del tiempo, asigne utilizando la Referencia basada en datos. Del Control Horario a los Proyectos, asigne utilizando la Referencia Basada en Datos.  Si no puede utilizar una referencia basada en datos, comente sus opciones con su asesor. |
| CapEx Presupuesto | Asegúrese de que los valores fluyen hacia el objeto Seguimiento del tiempo[ VM2 ].  Del objeto Mano de obra al objeto Seguimiento del tiempo, asigne utilizando la Referencia basada en datos. Del Control Horario a los Proyectos, asigne utilizando la Referencia Basada en Datos.  Si no puede utilizar una referencia basada en datos, comente sus opciones con su asesor |

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
