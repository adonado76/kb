---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "La tabla de Ratio de Asignación es demasiado grande"
breadcrumb: []
source_path: "studio/troubleshooting/studio-troubleshooting-assignment-ratio.html"
images:
  - "resources/images/studio_images/troubleshooting/assingment-ratio-too-large-rec.png"
  - "resources/images/studio_images/troubleshooting/assingment-ratio-too-large-solution-2.png"
  - "resources/images/studio_images/troubleshooting/assingment-ratio-too-large-solution.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# La tabla de Ratio de Asignación es demasiado grande

El limitador de Ratio de Asignación evita la creación de tablas de Ratio de Asignación demasiado grandes.

El mayor tamaño para las tablas de Ratio de Asignación viene determinado por los siguientes factores:

- El recuento de filas del identificador de la tabla de origen
- El recuento de filas del identificador de la tabla de destino

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/assingment-ratio-too-large-rec.png)

Este error suele deberse a que no se utiliza una asignación de estilo Relación de datos. Si no se utiliza la relación de datos, se crea un gran tipo de asignaciones *de muchos a muchos* o de *todos a todos*. Estas asignaciones tienen un bajo rendimiento y reducen la eficacia de las asignaciones.

## La recomendación de configuración para la tabla Ratio de asignación es un error demasiado grande

Para resolver este error, puede realizar una o varias de las siguientes acciones:

- Añadir relación de datos a la asignación afectada.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/assingment-ratio-too-large-solution.png)
- Añada un filtro De o A a la asignación afectada.

  ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/assingment-ratio-too-large-solution-2.png)
- Reducir el número de filas de identificadores en los objetos fuente.
- Reducir el número de filas de identificadores en los objetos de destino.
