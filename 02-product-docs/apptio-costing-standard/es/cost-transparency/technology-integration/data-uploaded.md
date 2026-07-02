---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Carga útil de datos"
breadcrumb: []
source_path: "cost-transparency/technology-integration/data-uploaded.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Carga útil de datos

Como se describe en los requisitos previos, el flujo de datos se inicia en IBM Turbonomic. Una vez configurado el tipo de objetivo IBM Apptio, los datos, incluidas las acciones Turbo pendientes y Turbo ejecutadas, se transfieren a IBM Apptio 's Datadrop. A partir de ahí, los conectores Datalink transmiten los datos a IBM Apptio 's TBM Studio para su posterior procesamiento.

Se cargarán los cuatro archivos siguientes

- Acciones pendientes Turbo On Prem
- Acciones Turbo On Prem Ejecutadas
- Acciones pendientes de Turbo Cloud
- Acciones ejecutadas de Turbo Cloud

Los expedientes se distinguen por dos dimensiones clave:

- **Estado de la acción** : PENDIENTE o EJECUTADA.
- **Entrega** : CLOUD o ON-PREM.

La distinción clave radica en los datos que se transmiten. Para CLOUD, sólo se envían datos agregados, que incluyen 14 columnas, en contraste con las 25 columnas enviadas para los datos On-Prem. Las principales razones de esta diferencia de granularidad son las siguientes:

- Los datos On-Prem se cuantifican utilizando el modelo y los datos de IBM Apptio, ya que IBM Turbonomic no proporciona detalles financieros para los entornos On-Prem. Para realizar estos cálculos, se requiere un mayor nivel de granularidad, razón por la cual se incluyen columnas detalladas, como Id de entidad e Id de acción. Por el contrario, los datos de la nube ya vienen con el ahorro de $ precalculado, según lo determinado por IBM Turbonomic, lo que elimina la necesidad de detalles tan granulares.
- IBM Apptio no está diseñado para almacenar datos granulares de la Nube, ese es el propósito del producto Cloudability. De forma similar a cómo se ingieren las facturas de nube de los CSP sin incluir la información más detallada (por ejemplo, el Id. del recurso), esta integración también evita el envío de datos granulares de optimización de la nube.

Los conjuntos de 25 columnas para los datos On-Prem y 14 columnas para los datos Cloud se seleccionaron cuidadosamente mediante un esfuerzo de colaboración entre IBM Apptio y IBM Turbonomic. Este ejercicio se centró en identificar las columnas más importantes que serían valiosas tanto para la modelización como para la elaboración de informes en la integración.
