---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Instalación de componentes"
breadcrumb: []
source_path: "cost-transparency/technology-integration/install-_component.html"
images:
  - "resources/images/ct_images/trb-comp-1.jpg"
  - "resources/images/ct_images/trb-comp.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Instalación de componentes

Para permitir la integración de los datos de IBM Turbonomic Action con IBM Apptio, se han desarrollado tres nuevos componentes. Estos componentes están actualmente detrás de la bandera Beta en TBM Studio, localizada bajo la pestaña Proyecto dentro de Activar Características. En consecuencia, sólo los usuarios con acceso de administrador a Apptio pueden hacerlos visibles en la sección Disponible de la pestaña Componentes en esta fase.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-comp.jpg)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-comp-1.jpg)

Nota: Asegúrese de que la Versión de los Componentes en la Configuración del Proyecto está ajustada a la Versión 120. Una vez instalados los componentes, puede revertir la Versión de componentes a la plantilla deseada o a la anterior.

## Componente de optimización de TI híbrida

El primer componente a instalar es el NUEVO componente de *Optimización de TI Híbrida*. Este componente introduce un conjunto de nuevos conjuntos de datos maestros, métricas (tanto modeladas como calculadas) y asignaciones de modelos. Estos elementos están diseñados para dar soporte a una arquitectura que permita modelar e informar sobre las optimizaciones de la Infraestructura TI Híbrida.

Dado que este componente está destinado a clientes existentes, puede requerir la personalización de determinadas búsquedas en tablas, métricas y asignaciones para alinearse con el modelo Apptio existente dentro del nuevo marco de Optimización de TI híbrida.

Para obtener información más detallada sobre el componente, consulte la descripción proporcionada al navegar hasta el componente en el sistema.

## Turbonomic - Componente Acciones

Mientras que el primer componente, *Hybrid IT Optimization*, establece el marco, el segundo componente, Turbonomic - Actions, instala las tablas y los conjuntos de datos maestros necesarios para permitir la integración perfecta de los datos de *IBM Turbonomic Action* -mediante Datadrop- en IBM Apptio 's TBM Studio.

Nota: El componente *Optimización de TI híbrida* debe instalarse primero, ya que la tabla maestra de Turbo Actions depende de dependencias de búsqueda en tres tablas editables incluidas con el componente *Optimización de TI híbrida*.

Para más detalles sobre el contenido de este componente, consulte la descripción que aparece al navegar hacia el componente.

## Optimización de TI híbrida - Componente de informes

El tercer y último componente es el de *Optimización de TI híbrida - Informes*. Este componente instala dos informes que visualizan información práctica de la integración. Proporciona:

- Finanzas de TI y el Propietario del Servicio Técnico (Proveedor de TI) con una visión de Ahorros Potenciales y Realizados desde una perspectiva de costes.
- Propietario de la solución/aplicación (consumidor de TI) con una visión de los ahorros potenciales y realizados desde la perspectiva de los cargos.

Para más detalles sobre el contenido de este componente, consulte la descripción que aparece al navegar hacia el componente.
