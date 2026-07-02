---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Asignaciones directas frente a indirectas"
breadcrumb: []
source_path: "cost-transparency/configuration/buallocate.html"
images:
  - "resources/images/ct_images/6857_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Asignaciones directas frente a indirectas

Las asignaciones directas se basan en el consumo. Las asignaciones indirectas se basan en una proporción seleccionada, como el personal total por departamento.

## Costes directos

Los costes directos pueden asignarse a un producto, departamento o proyecto concreto. La mano de obra, el software, el equipamiento y las materias primas son ejemplos de costes directos. Los costes directos pueden identificarse con un objeto de coste específico. Un gran porcentaje de los costes directos procede de la mano de obra y los materiales.

## Costes indirectos

Los costes indirectos suelen incluir la infraestructura que mantiene una empresa en funcionamiento. Los costes indirectos pueden incluir artículos como material de limpieza, servicios públicos, alquiler de equipos de oficina, ordenadores de sobremesa y teléfonos móviles.

## Cómo se aplican los costes directos e indirectos en el modelo de costes Apptio

Los costes directos e indirectos se calculan en la parte superior del modelo de costes utilizando cuatro objetos: Servicios empresariales, Asignaciones directas de servicios, Asignaciones indirectas de servicios y Asignación de unidades empresariales. El modelo se muestra a continuación.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6857_1.png)

Los costes de los Servicios Empresariales se asignan al objeto modelo Asignaciones Directas de Servicio basándose en el campo Servicio\_Asignaciones Directas de Servicio. El campo se encuentra en el conjunto de datos Todos los servicios empresariales que respalda el objeto modelo Servicios empresariales y en el conjunto de datos Maestro de asignaciones directas de servicios que respalda el objeto modelo Asignaciones directas de servicios.

Los costes de Servicios empresariales se imputan al objeto Indirectos de imputación de servicios en función del campo Comprobación de DUA. El campo se encuentra en el conjunto de datos Todos los servicios empresariales que respalda tanto el objeto modelo Servicios empresariales como el objeto modelo Asignaciones directas de servicios.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
