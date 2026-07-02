---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Computación en nube Asignación de atributos"
breadcrumb: []
source_path: "cost-transparency/user-guide/cloudcomputeattributesmapping-9568.html"
images:
  - "resources/images/ct_images/cloudcomputeattributesmapping_1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Computación en nube Asignación de atributos

Nota: Se aplica a: Cloud Cost Management en TBM Studio 12.5 y posteriores

Utilice el archivo Cloud Compute Attributes (adjunto a continuación) para asignar sus atributos de computación, como memoria, almacenamiento y núcleos de CPU, a las columnas correspondientes de la tabla Cloud Service Provider Master Data. Los valores entre Memoria, Almacenamiento y Núcleos CPU vienen determinados por el tipo de instancia que figura en su factura. Estos atributos se utilizan para normalizar el tamaño de los servidores y aparecen en el informe Comparaciones de computación en CBM.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/cloudcomputeattributesmapping_1.png)

El archivo Cloud Compute Attributes debe cargarse manualmente en la tabla Cloud Compute Attributes a partir de TBM Studio 12.5.

**Para descargar el archivo Cloud Compute Attributes** :

1. Haga clic con el botón derecho del ratón en el archivo adjunto y pulse Guardar enlace (o destino) como.
2. Elija dónde desea guardar el archivo y, a continuación, haga clic en Guardar.

Nota: Para obtener las últimas actualizaciones de este archivo, consulte este artículo cada vez que publique contenidos.

| Fecha | Actualizar |
| --- | --- |
| 1/03/2022 | Actualización completa de todos los nuevos tipos de instancia hasta el 3 de enero de 2022 para AWS, Azure y Google Cloud. |
| 3/01/2019 | Se ha añadido la columna Familia de instancias.  Se han añadido nuevos tipos de instancia:   - AWS : a1, c5n, m5a, p3dn, r5, r5d, t3, u, z1d - Azure : S ( SAP Hana en Azure Grandes Instancias) |
| 7 de julio de 2018 | Versión inicial |

[Descargar el archivo de asignación](https://community.apptio.com/viewdocument/updated-hbm-cloud-pricing-data-for-1 "(se abre en una pestaña o una ventana nueva)")
