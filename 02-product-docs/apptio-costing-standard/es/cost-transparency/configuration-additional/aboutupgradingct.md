---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Acerca de la actualización de la Norma de cálculo de costes"
breadcrumb: []
source_path: "cost-transparency/configuration-additional/aboutupgradingct.html"
images:
  - "resources/images/ap_images/ui-tbar-settings.png"
  - "resources/images/ct_images/11151_1.png"
  - "resources/images/ct_images/11151_5.png"
  - "resources/images/ct_images/ct-about-1.png"
  - "resources/images/ct_images/ct-comp-vers.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Acerca de la actualización de la Norma de cálculo de costes

- Se aplica a: TBM Studio 12.x y posteriores, en Plantilla v102 y posteriores

El proceso de actualización de Costing Standard implica la actualización de las siguientes capas.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/11151_1.png)

## Plataforma

La plataforma (o base de código Apptio ), denominada TBM Studio, es un conjunto de funciones y capacidades que permiten realizar tareas que impulsan las aplicaciones Apptio, como crear modelos, cargar conjuntos de datos, imputar costes y crear informes. TBM Studio también incluye el motor de cálculo Apptio.

El objetivo es actualizar cada trimestre todos los clientes de TBM Studio 12.x a la última versión. En un esfuerzo por mantener nuestras aplicaciones actualizadas con las últimas funciones y mejoras de rendimiento, programamos un mantenimiento obligatorio durante un intervalo de fechas específico. Para conocer las fechas, póngase en contacto con su Customer Success Manager o con el [equipo de CS-Upgrade](https://community.apptio.com/docs/DOC-9207 "(se abre en una pestaña o una ventana nueva)").

**Control de versiones**. R12 es un atajo que hace referencia a la versión actual del producto base TBM Studio . Las versiones incrementales de TBM Studio se representan como 12.1, 12.2, etc. Para actualizar a una nueva versión de TBM Studio, póngase en contacto con su Customer Success Manager.

Para ver la versión de TBM Studio que está ejecutando, seleccione ![](../../../../../03-media/apptio-costing-standard/resources/images/ap_images/ui-tbar-settings.png) > Acerca de.

La siguiente ventana muestra la versión de TBM Studio :

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-about-1.png)

## Capa de aplicaciones

Las aplicaciones son componentes predefinidos que utilizan las capacidades de la plataforma para lograr un caso de uso. Los componentes de la aplicación pueden contener los siguientes elementos de contenido:

- Conjuntos de datos maestros
- Objetos modelo
- Taxonomía
- Métricas
- Perspectivas
- Informes

**Control de versiones**. El versionado de las aplicaciones Apptio se refleja como versiones de plantilla. La plantilla v106, por ejemplo, es el número de versión asignado a los componentes de la aplicación publicados con TBM Studio 12.6. Es posible utilizar versiones anteriores de la plantilla (por ejemplo, Plantilla v105 en TBM Studio 12.6 ) pero no viceversa. Por ejemplo, no puede ejecutar Plantilla v106 en TBM Studio 12.5.

Para ver la versión de plantilla que está ejecutando, abra TBM Studio y seleccione *Proyecto > Configuración del proyecto*.

Se abre el cuadro de diálogo Editar configuración del proyecto, que muestra la versión del componente.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-comp-vers.png)

**Guía de actualización**

Las actualizaciones de la aplicación quedan a su discreción:

- Cambie a una nueva plantilla de aplicación si desea utilizar las últimas funciones y mejoras introducidas por esa plantilla.
- Puede optar por actualizarse a una nueva versión de la plataforma, pero permanecer en la versión actual de su plantilla de aplicación. Por ejemplo, puede elegir actualizar a TBM Studio 12.6, pero permanecer en Plantilla v104 si no necesita las últimas funciones.
- Puede omitir las versiones de plantilla. Por ejemplo, puede pasar de la aplicación Plantilla v104 a v106, saltándose la Plantilla v105. Sin embargo, si opta por saltarse versiones, deberá actualizar todos sus componentes para evitar posibles problemas.

Nota: Para acceder a una plantilla de aplicación actual, debe actualizarse a la versión mínima de la plataforma que admita dicha plantilla. Por ejemplo, no puede acceder a la plantilla v106 a menos que esté en TBM Studio 12.6 y posteriores.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/11151_5.png)

Debe actualizar TBM Studio antes de actualizar la plantilla de la aplicación.

Para obtener instrucciones paso a paso:

- Actualización desde la plantilla v103, consulte [Actualización Costing Standard Desde la plantilla v103 a la última versión](../v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/upgradect.html).
- Actualice desde Plantillas v104 o posterior, consulte [Actualización Costing Standard Desde la plantilla v104+ hasta la última versión](../v12.x-on-tbm-studio-12.x/upgradect-v104.html).

## Capa de taxonomía TBM

La Taxonomía TBM es un marco para asignar costes de TI con un enfoque estándar que permite a los líderes tecnológicos gestionar y optimizar las TI como un negocio. La actualización de una versión a otra es una decisión impulsada por el cliente y no está directamente relacionada con las actualizaciones de la plataforma o los contenidos. Los archivos de referencia de cada versión de ATUM están disponibles en el producto. Pasar de una versión de ATUM a otra exige modificar los datos y las estrategias de asignación para asignar los costes a las nuevas categorías. Para más información, consulte el
