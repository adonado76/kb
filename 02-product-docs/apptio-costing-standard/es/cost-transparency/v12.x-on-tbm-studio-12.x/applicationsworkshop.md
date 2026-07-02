---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Taller de aplicaciones"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/applicationsworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Taller de aplicaciones

Preparación de los datos de la aplicación

1. Si aún no lo has hecho, carga los datos de tu aplicación incluyendo:
   - Lista de aplicaciones
   - Detalles de la solicitud complementaria
2. Siguiendo las prácticas habituales de Apptio las prácticas habituales, clasifique cada conjunto de datos brutos en la categoría de Aplicaciones.
3. Si procede, aplique un filtro de fechas a los datos de su solicitud.

## Acerca del identificador de aplicaciones

El identificador del conjunto de datos maestros de aplicaciones es el ID de aplicación. Debe ser un identificador único para cada solicitud que se rastree dentro de Apptio

## Acerca de las claves de aplicación

Las claves del conjunto de Datos Maestros de Aplicaciones son todas generadas por el sistema. La lógica recomendada figura en el cuadro siguiente.

| Clave | La clave de campo se basa en | Lógica recomendada |
| --- | --- | --- |
| Ticket\_App Key (En 11.6 ) | Definida por el usuario | ="Ticket\_App Key"&&Identificación de la aplicación Utilice esta clave sólo si instala el componente Service Desk. Para establecer un vínculo entre el Service Desk y las aplicaciones, debe tener un ID de aplicación vinculado a los tickets sobre esa aplicación. |
| Clave Project\_App | ID de aplicación | ="Clave Proyecto\_App"&&Identificación de la aplicación Utilice esta clave sólo si instala el componente Proyectos. Para establecer un vínculo entre Proyectos y Aplicaciones, debe tener un ID de aplicación vinculado a proyectos sobre esa aplicación. |
| Clave Server\_App | Definida por el usuario | ="Server\_App Key"&&Identificación de la aplicación |
| Clave App\_Service | Definida por el usuario | ="App\_Service"&&Nombre de la aplicación Si desea que sus servicios sean grupos de aplicaciones, puede utilizar Grupo de aplicaciones en lugar de Nombre de aplicación en la fórmula anterior. |
| Almacenamiento\_App Clave | Definida por el usuario | ="Storage\_App"&& ID de aplicación |

## Columnas computadas comunes necesarias para las aplicaciones

No es necesario crear columnas computadas específicas. Variará en función de los datos y de las necesidades del cliente en cuanto a la forma de hacer pivotar los datos.

## Asignar datos a los datos maestros de las aplicaciones

Asigne los datos de su aplicación al conjunto de datos maestros de aplicaciones. La mayor parte de la cartografía debería explicarse por sí misma en este punto. Lo más probable es que las unidades reales, el recuento de solicitudes y las unidades presupuestadas se establezcan en =1. En 12.7 ahora puede aprovechar la función Column Map en su conjunto de datos sin procesar para asignarlos a los Datos Maestros de las Aplicaciones (Map Columns )

## Añadir uniones a los datos maestros de las aplicaciones

Una sus conjuntos de datos maestros de servidor y almacenamiento al conjunto de datos maestros de aplicaciones. El paso Unir vincula la tabla actual con otras tablas haciendo coincidir los valores de una columna de la tabla actual con los valores de una columna de otra tabla. (Unir datos )

| Conjunto de datos | Acciones |
| --- | --- |
| Aplicaciones Datos maestros | Añade un paso de unión. Cree un nuevo enlace entre los Datos Maestros de Aplicaciones y los Datos Maestros de Servidores.  **De** : `Applications Master Data.Application ID`  **Para** : `Servers Master Data.App Consumer`  Cree un nuevo enlace entre los Datos Maestros de Aplicaciones y los Datos Maestros de Almacenamiento.  **De** : `Applications Master Data.Application ID`  **Para** : `Storage Master Data.App Consumer` |

## Revisar el objeto Aplicaciones en los modelos

| Modelo | Acciones |
| --- | --- |
| Coste | Asegúrese de que los valores fluyen hacia el objeto Aplicaciones. De Proyectos a Aplicaciones, asigne utilizando la Referencia basada en datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen los Proyectos con las Aplicaciones son las columnas Clave\_Proyecto\_Aplicación en ambos conjuntos de datos.  De Servidores a Aplicaciones, asignar utilizando la Reverencia basada en Datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen Servidores y Aplicaciones son las columnas Server\_App Key en ambos conjuntos de datos.  De Entradas a Aplicaciones, asigne utilizando la Referencia basada en datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen Tickets y Solicitudes son las columnas Clave Ticket\_App en ambos conjuntos de datos.  De Almacenamiento a Aplicaciones, asigne utilizando la Referencia basada en datos, con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen el Almacenamiento y las Aplicaciones son la Clave Storage\_App en el lado del Almacenamiento y la Clave Storage\_App en el lado de las Aplicaciones. |
| Presupuesto | Asegúrese de que los valores fluyen hacia el objeto Aplicaciones. De Proyectos a Aplicaciones, asigne utilizando la Referencia basada en datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen los Proyectos con las Aplicaciones son las columnas Clave\_Proyecto\_Aplicación en ambos conjuntos de datos.  De Servidores a Aplicaciones, asignar utilizando la Reverencia basada en Datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen Servidores y Aplicaciones son las columnas Server\_App Key en ambos conjuntos de datos.  De Entradas a Aplicaciones, asigne utilizando la Referencia basada en datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen Tickets y Solicitudes son las columnas Clave Ticket\_App en ambos conjuntos de datos.  De Almacenamiento a Aplicaciones, asigne utilizando la Referencia basada en datos, con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen el Almacenamiento y las Aplicaciones son la Clave Storage\_App en el lado del Almacenamiento y la Clave Storage\_App en el lado de las Aplicaciones. |
| CapEx | Asegúrese de que los valores fluyen hacia el objeto Aplicaciones. De Proyectos a Aplicaciones, asigne utilizando la Referencia basada en datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen los Proyectos con las Aplicaciones son las columnas Clave\_Proyecto\_Aplicación en ambos conjuntos de datos. |
| CapEx Presupuesto | Asegúrese de que los valores fluyen hacia el objeto Aplicaciones. De Proyectos a Aplicaciones, asigne utilizando la Referencia basada en datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen los Proyectos con las Aplicaciones son las columnas Clave\_Proyecto\_Aplicación en ambos conjuntos de datos. |

## Revisar los informes de aplicación

Los siguientes informes se actualizan después de haber configurado el objeto Aplicaciones:

- Revisión de la solicitud
- Cartera de aplicaciones
- Lista de aplicaciones
- Análisis de infraestructuras por aplicación
- Aplicaciones nuevas y retiradas
- App Review - Detalle
- App - Detalle
- App - Detalle - Grupos de costes
- App - Detalle - IT Towers
- App - Detalle - Servidores
- App - Detalle - Almacenamiento
- App - Detalle - Entradas
- App Infra Tabla de asignación
- Reseña de la aplicación - Family Detail
- Aplicaciones Validez
- Dimensiones de los datos - Aplicaciones
- Calidad de datos - Recursos informáticos
- Calidad de datos - Servicios
- Torre IT Detalle
- Infra - Detalles de la aplicación

Para ver los detalles de estos informes (incluida la navegación, las funciones, los objetivos y las preguntas a las que responde cada informe), consulte la Guía del usuario de Costing Standard disponible en la Ayuda en línea.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
