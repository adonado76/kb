---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Mapear las unidades de medida"
breadcrumb: []
source_path: "it-benchmarking/configuration/map-uom.html"
images:
  - "resources/images/it_benchmarking_images/map-uom-map.jpg"
  - "resources/images/it_benchmarking_images/map-uom.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Mapear las unidades de medida

Se han definido unidades de medida estándar para los datos de referencia proporcionados por la aplicación Apptio Benchmarking Infrastructure. Para iluminar los informes de Benchmarking, debe asignar sus unidades de medida a la unidad de medida de la aplicación.

Cuando creó el proyecto Costing Standard , definió las unidades de medida de su infraestructura informática. Si ha aceptado las definiciones de proyecto por defecto, éstas coinciden con las unidades de medida estándar definidas en los datos de referencia. En la medida de lo posible, debe hacer coincidir las unidades de medida de los datos de referencia con la unidad de medida de su proyecto Costing Standard . El mapeo completo de las unidades de medida proporciona los datos de evaluación comparativa más completos de los informes. Las unidades de medida se asignan siguiendo las instrucciones de la aplicación, como se muestra a continuación.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/map-uom.jpg)

**Requisitos previos**

Antes de poder mapear las subtorres y las piscinas de costes, debes tener:

Importado el benchmarking AIB.

Instalado el componente CTF-Benchmarking ( [https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=costing-standard-foundation-module-configuration](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=costing-standard-foundation-module-configuration "(se abre en una pestaña o una ventana nueva)") ).

Incorporación de los datos de evaluación comparativa de AIB a los datos maestros de evaluación comparativa.

**Para asignar la columna Unidad de medida de referencia en el conjunto de datos Datos maestros de la fuente de costes**

Abra el conjunto de datos Datos maestros de la fuente de costes.

1. En la pestaña Fuentes de datos, edite la fuente de datos Datos maestros de composición de referencia.
2. Asigne la columna Unidad de medida de referencia a =Unidad de medida.

**Asignar las unidades de medida**

Seleccione la pestaña Informes.

1. En la página de inicio, seleccione Benchmarking.
2. En la barra de herramientas de navegación de Benchmarking, seleccione el icono Mapa resaltado a continuación.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/map-uom-map.jpg)

1. Seleccione la pestaña Unidad de medida.
2. Siga las instrucciones de la página de mapas.

La correspondencia debe ser unívoca.
