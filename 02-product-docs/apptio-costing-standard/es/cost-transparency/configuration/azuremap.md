---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Azure Cartografía de servicios"
breadcrumb: []
source_path: "cost-transparency/configuration/azuremap.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Azure Cartografía de servicios

Apptio los conectores CBM y AWS de DataLink le permiten asignar partidas de facturación desde las partidas de facturación de su proveedor de nube a los atributos de ATUM, incluidas las torres y subtorres de TI, la jerarquía de servicios TBM, así como una unidad de medida normalizada.

Se aplica a: Cloud para Costing Standard en TBM Studio 12.5.x

## Visión general

Estas asignaciones te permiten hacer lo siguiente:

- Analizar diversos servicios en nube de múltiples proveedores utilizando una clasificación común de servicios en nube
- Ver el coste, el consumo y los costes unitarios de todos los servicios de nube pública de forma similar en varios proveedores
- Asignar automáticamente los costes de la nube a las torres de recursos informáticos adecuadas

Puede descargar los archivos cartográficos de la Comunidad Apptio :

[https://community.apptio.com/viewdocument/azure-services-mapping](https://community.apptio.com/viewdocument/azure-services-mapping "(se abre en una pestaña o una ventana nueva)")

## Actualizaciones cartográficas

Dado que los proveedores de nubes actualizan sus ofertas de servicios de forma constante y rápida, las correspondencias creadas y mantenidas por Apptio pueden quedar obsoletas. Para hacer frente a este entorno dinámico, Apptio actualiza mensualmente los archivos cartográficos. La acción que debes realizar depende de si utilizas el Multicloud Connector.

Los archivos de asignación actualizados se adjuntan a este artículo y se incluyen en la tabla de historial de cambios que figura a continuación.

- Conector Multicloud. Para automatizar la ingesta de la facturación en la nube, la asignación ATUM se realiza en el preprocesador de facturación en la nube Apptio. Los archivos de asignación se guardan en una ubicación central y la asignación se produce antes de que la factura llegue al entorno CBM del cliente. Si se producen lagunas en el mapeo de ATUM, no es necesaria ninguna acción por su parte. En su lugar, Apptio identifica las lagunas, las rellena y, a continuación, actualiza el archivo de asignación para garantizar que esas lagunas se eliminan de su entorno.
- Azure Conector. Si utiliza el antiguo conector Azure, las asignaciones de ATUM siguen realizándose en CBM a través del conjunto de datos de búsqueda de proveedores de servicios en la nube, al que debe añadir el archivo de asignación de servicios Microsoft Azure. El archivo de asignación debe actualizarse manualmente sobrescribiendo el conjunto de datos con el archivo de asignación.

Para actualizar el archivo de asignación:

1. Haga clic con el botón derecho del ratón en el archivo adjunto y, a continuación, en Guardar enlace (o destino) como.
2. Navegue hasta el lugar donde desea guardar el archivo y, a continuación, haga clic en Guardar.
3. Descomprima y abra el archivo.cvs en una aplicación adecuada, como Microsoft Excel.
4. Seleccione el archivo de la versión de ATUM que desee.
5. Inicie sesión en Apptio TBM Studio.
6. En el Explorador de proyectos, vaya a Tablas > Microsoft Azure Asignación de servicios.
7. Compruebe el archivo Microsoft Azure Service Mapping y sobrescríbalo con el archivo.csv actualizado.

El archivo cartográfico se actualiza con frecuencia. Consulte este artículo para conocer el contenido más reciente.

## Cartografía automatizada para ATUM 2.1 y 3.0

A partir de abril de 2019, CBM se actualizó para admitir la asignación automatizada de servicios de proveedores de nube a las clasificaciones de ATUM. CBM puede asignar servicios de proveedores de nube pública a ATUM 1.0, 2.0, 2.1 y 3.0, en función de los requisitos de su organización.

## Cambiar el historial

Los archivos de Microsoft Azure Mapping Services se han actualizado en las fechas siguientes. Apptio recomienda que haga clic en **Acción > Seguir** para que se le notifique cuándo hay disponibles archivos de mapas recién actualizados.

| Fecha de adición | Versión | Descripción |
| --- | --- | --- |
| 30 de noviembre de 2020 | 2.19 | Nuevas entradas para ATUM 2.0 y las lagunas comunicadas por los clientes. |
| 12 de octubre de 2020 | 2.17 | Nuevas entradas para ATUM 2.0 y lagunas comunicadas por los clientes a partir de finales de septiembre de 2020 |
| 1 de septiembre de 2020 | 2.16 | Nuevas entradas para ATUM 2.0 y lagunas comunicadas por los clientes a partir de agosto de 2020. |
| 22 de mayo de 2020 | 2.15 | Nuevas entradas para ATUM 2.0 y las lagunas comunicadas por los clientes. |
| 23 de abril de 2020 | 2.14 | Nuevas entradas para ATUM 2.0 y las lagunas comunicadas por los clientes. |
| 30 de enero de 2020 | 2.13 | Nuevas entradas para ATUM 2.0 y las lagunas comunicadas por los clientes. |
| 15 de noviembre de 2019 | 2.12 | Nuevas entradas en Azure para colmar las lagunas señaladas por los clientes. |
| 3 de junio de 2019 | 2.11 | Nuevas entradas para ATUM 1.0 y 2.0 y lagunas comunicadas por los clientes. |
| 7 de marzo de 2019 | 2.10 | Nuevas entradas basadas en el contenido de la API de fijación de precios de marzo de Azure con ATUM 2.0 y las diferencias comunicadas por los clientes. |
| 15 de enero de 2019 | 2.9.2 | Se ha corregido el formato de las columnas y se han añadido los datos que faltaban. |
| 10 de enero de 2019 | 2.9.1 | Corrección del expediente de diciembre. |
| 26 de diciembre de 2018 | 2.9 | Incluye nuevas entradas basadas en diciembre Azure Pricing API Content con ATUM 2.0 y las lagunas de los informes de los clientes. |
| 24 de octubre de 2018 | 2.8.1 | Se ha añadido una nueva columna, Subtower 2.0, como copia directa de SubTower 2.0 para resolver problemas de casos en las funciones de búsqueda de CCM. |
| 23 de octubre de 2018 | 2.8 | Incorporó un gran número de cambios en los nombres de los servicios introducidos por Azure a mediados de octubre de 2018 |
| 20 de septiembre de 2018 | 2.7 | Incluye nuevas entradas basadas en Ago Azure Precios API Contenido con ATUM 2.0. |
| 7 de mayo de 2018 | 2.6 | Incluye nuevas entradas basadas en abril Azure Pricing API Content con ATUM 2.0 y las lagunas en los informes de los clientes. |
| 2 de marzo de 2018 | 2.5 | Incluye nuevas entradas basadas en febrero Azure Precios API Contenido con ATUM 2.0. |
| 19 de enero de 2018 | 2.4 | Incluye nuevas entradas basadas en enero Azure Precios API Contenido con ATUM 2.0. |
| 9 de enero de 2018 | 2.3 | Incluye nuevas entradas basadas en el contenido de la API de precios de diciembre Azure con ATUM 2.0 y actualizaciones con asignaciones de contadores renombradas Azure. |
| 8 de septiembre de 2017 | 2.2 | Incluye todos los servicios de las nuevas entradas basadas en el contenido de la API de precios de septiembre Azure con ATUM 2.0. |
| 27 de julio de 2017 | 2.1 | Incluye todos los servicios de las nuevas entradas basadas en julio Azure Pricing API content with ATUM 2.0. |
| 24 de mayo de 2017 | 2.0 | Añadidos nuevos campos ATUM 2.0 (Torre 2.0, Subtorre 2.0, Tipo de servicio, Categoría de servicio, Nombre del servicio); Incluye todos los servicios del catálogo de servicios publicado en mayo de 2017. |
| 24 de enero de 2017 | 1.5.1 | Se ha actualizado un error tipográfico del catálogo de servicios de Azure en el que Windows Azure Storage aparecía mal etiquetado como Windows Azure Service Bus for Resource GUID5E7A80E5-0273-44B8-A179-E4F62EA6EC9F. |
| 19 de enero de 2017 | 1.5 | Incluye todos los servicios del catálogo de servicios publicado en enero de 2017. |
| 4 de diciembre de 2016 | 1.4 | Incluye todos los servicios del catálogo de servicios publicado en Nov 2016 | gran número de Mejoras en la normalización de Unidades. |
| 23 de mayo de 2016 | 1.3 | Incluye todos los servicios del catálogo de servicios publicado en abril de 2016. |
| 2 de febrero de 2016 | 1.2 | Publicación inicial. |

Puede descargar los archivos cartográficos de la Comunidad Apptio :

[https://community.apptio.com/viewdocument/azure-services-mapping](https://community.apptio.com/viewdocument/azure-services-mapping "(se abre en una pestaña o una ventana nueva)")

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
