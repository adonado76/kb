---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Actualización de la norma de cálculo de costes"
breadcrumb:
  - "Costing Standard"
  - "Administración"
  - "Actualización de la norma de cálculo de costes"
source_path: "cost-transparency/admin/upgrade-cs.html"
images:
  - "resources/images/studio_images/ucs-1.png"
  - "resources/images/studio_images/ucs-2.png"
  - "resources/images/studio_images/ucs-3.png"
  - "resources/images/studio_images/ucs-4.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Actualización de la norma de cálculo de costes

El proceso de actualización de Costing Standard implica actualizaciones en las siguientes capas.

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ucs-1.png)

## Capa de plataforma

La plataforma (o código base de Apptio ), denominada TBM Studio, es un conjunto de funciones y capacidades que le permiten realizar tareas que impulsan las aplicaciones Apptio, como crear modelos, cargar conjuntos de datos, asignar costes y crear informes. TBM Studio también incluye el motor de cálculo « Apptio ».

El objetivo es actualizar todos los clientes de Server 12.x a la última versión cada trimestre. Con el fin de mantener nuestras aplicaciones actualizadas con las últimas funciones y mejoras de rendimiento, programamos un mantenimiento obligatorio durante un intervalo de fechas específico. Para conocer las fechas, ponte en contacto con tu gestor de éxito del cliente o consulta este [calendario.](https://community.ibm.com/community/user/viewdocument/tbm-studio-and-applications-r12-rel "(se abre en una pestaña o una ventana nueva)")

**Control de versiones**. R12 Es un acceso directo que hace referencia a la versión actual del producto base TBM Studio. Las versiones incrementales de TBM Studio se representan como 12.11.x. Para actualizar a una nueva versión de TBM Studio, ponte en contacto con tu gestor de éxito del cliente.

Para ver la versión del servidor que está ejecutando, seleccione ![](_-1365910950.) > Acerca de.

La siguiente ventana muestra la versión del servidor:

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ucs-2.png)

## Capa de aplicaciones (Contenido)

Las aplicaciones son componentes predefinidos que utilizan las capacidades de la plataforma para lograr un caso de uso. Los componentes de la aplicación pueden contener los siguientes elementos de contenido:

- Conjuntos de datos maestros
- Objetos modelo
- Taxonomía
- Métricas
- Perspectivas
- Informes

**Control de versiones**. El control de versiones de las aplicaciones de Apptio se refleja como versiones de plantillas. La plantilla v120, por ejemplo, es el último número de versión de la plantilla. Es posible utilizar versiones anteriores de plantillas (por ejemplo, la plantilla v107 o la plantilla v109 ) en la última versión del servidor.

Para ver la versión de la plantilla que está ejecutando, abra TBM Studio y seleccione *Proyecto > Configuración del proyecto*.

Se abre el cuadro de diálogo Editar configuración del proyecto, que muestra la versión del componente.

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ucs-3.png)

## Guía de actualización

Las actualizaciones de la aplicación quedan a su discreción:

- Cambie a una nueva plantilla de aplicación si desea utilizar las últimas funciones y mejoras introducidas por esa plantilla.
- Puede optar por permanecer en la versión actual de la plantilla de la aplicación, incluso después de actualizar a la última versión del servidor. Por ejemplo, puede optar por permanecer en la plantilla v109, incluso si la última versión del servidor tiene la plantilla v120
- Puede omitir las versiones de plantilla. Por ejemplo, puede actualizar desde la plantilla de aplicación v107 a v110, omitiendo la plantilla v109.
- Puede optar por actualizar solo algunos componentes cuyas últimas funciones le interesen. Tenga cuidado con las dependencias de los componentes disponibles en la pantalla de instalación de componentes o en la guía de configuración.

Nota: Para acceder a una plantilla de aplicación actual, debe actualizar a la versión mínima de la plataforma que admita dicha plantilla. Por ejemplo, no se puede acceder a la plantilla v106 a menos que se utilice TBM Studio 12.6 y versiones posteriores.

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ucs-4.png)

Debe actualizar TBM Studio antes de actualizar la plantilla de la aplicación.

Para obtener instrucciones paso a paso sobre cómo actualizar la plantilla, haga clic [aquí](con-ver-lay.html).

## Capa de taxonomía TBM

La taxonomía TBM es un marco para asignar los costes de TI mediante un enfoque estándar que permite a los responsables tecnológicos gestionar y optimizar las TI como un negocio. La actualización de una versión a otra es una decisión que depende del cliente y no está directamente relacionada con las actualizaciones de la plataforma o del contenido. Los archivos de referencia para cada versión de ATUM están disponibles en el producto. Pasar de una versión de ATUM a otra requiere cambios en los datos y las estrategias de asignación para asignar los costes a las nuevas categorías.
