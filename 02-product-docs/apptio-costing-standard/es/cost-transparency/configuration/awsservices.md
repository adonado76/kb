---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "AWS Cartografía de servicios"
breadcrumb: []
source_path: "cost-transparency/configuration/awsservices.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# AWS Cartografía de servicios

Apptio los conectores CBM y AWS de DataLink le permiten asignar partidas de facturación desde las partidas de facturación de su proveedor de nube a los atributos de ATUM, incluidas las torres y subtorres de TI, la jerarquía de servicios TBM, así como una unidad de medida normalizada.

Se aplica a: Cloud para Costing Standard y Cloud Business Management en TBM Studio 12.5.x

## Visión general

Estas asignaciones te permiten hacer lo siguiente:

- Analizar diversos servicios en nube de múltiples proveedores utilizando una clasificación común de servicios en nube
- Ver el coste, el consumo y los costes unitarios de todos los servicios de nube pública de forma similar en varios proveedores
- Asignar automáticamente los costes de la nube a las torres de recursos informáticos adecuadas

## Actualizaciones cartográficas

Dado que los proveedores de la nube actualizan sus ofertas de servicios de forma constante y rápida, las correspondencias creadas y mantenidas por Apptio pueden quedar obsoletas. Para hacer frente a este entorno dinámico, Apptio actualiza mensualmente los archivos cartográficos. La acción que debes realizar depende de si utilizas el Multicloud Connector:

- Conector Multicloud. Para automatizar la ingesta de la facturación en la nube, la asignación ATUM se realiza en el preprocesador de facturación en la nube Apptio. Los archivos de asignación se guardan en una ubicación central y la asignación se produce antes de que la factura llegue al entorno CBM del cliente. Si se producen lagunas en el mapeo de ATUM, no es necesaria ninguna acción por su parte. En su lugar, Apptio identifica las lagunas, las rellena y, a continuación, actualiza el archivo de asignación para garantizar que esas lagunas se eliminan de su entorno.
- AWS Conector. Si utiliza el antiguo conector AWS, las asignaciones de ATUM siguen realizándose en CBM a través del conjunto de datos de búsqueda de proveedores de servicios en la nube, al que debe añadir el archivo de asignación de servicios AWS. El archivo de asignación puede actualizarse automáticamente a través del conector heredado AWS o sobrescribiendo manualmente el conjunto de datos con el archivo de asignación.

Para actualizar el archivo de asignación:

1. Haga clic con el botón derecho del ratón en el archivo adjunto y, a continuación, en Guardar enlace (o destino) como.
2. Navegue hasta el lugar donde desea guardar el archivo y, a continuación, haga clic en Guardar.
3. Descomprima y abra el archivo.cvs en una aplicación adecuada, como Microsoft Excel.
4. Seleccione el archivo de la versión de ATUM que desee.
5. Inicie sesión en Apptio TBM Studio.
6. En el Explorador de proyectos, vaya a **Tablas > AWS Asignación de servicios**
7. Compruebe el archivo AWS Service Mapping y sobrescríbalo con el archivo .csv actualizado.

El archivo cartográfico se actualiza con frecuencia. Consulte este artículo para conocer el contenido más reciente.

## Carencias en la cartografía

Si es usted usuario de AWS y encuentra lagunas en la cartografía, envíe por correo electrónico una lista de esas lagunas a Apptio en [cloudmapping@apptio.com](mailto:cloudmapping@apptio.com "(se abre en una pestaña o una ventana nueva)"). Haremos todo lo posible por colmar las lagunas detectadas en la próxima actualización cartográfica. Para su correo electrónico, exporte y adjunte el informe ATUM Mapping Quality (en la colección de informes Maintenance), e incluya la siguiente información para cada partida de proveedor de servicios en nube con un campo Subtower en blanco:

- Proveedor
- Producto
- Elemento
- Procedimiento
- Coste (opcional, pero útil para comprender el impacto de las carencias)

## Cartografía automatizada para ATUM 2.1 y 3.0

A partir de abril de 2019, CBM se actualizó para admitir la asignación automatizada de servicios de proveedores de nube a las clasificaciones de ATUM. CBM puede asignar servicios de proveedores de nube pública a ATUM 1.0, 2.0, 2.1 y 3.0, en función de los requisitos de su organización.

## Cambiar el historial

| Fecha | ATUM v1.0 | ATUM v2.0 | Actualizar |
| --- | --- | --- | --- |
| 30/11/2020 | v1.35 | v2.25 | Incluye nuevas entradas para ATUM v1 y v2 y las lagunas en los informes de los clientes a finales de Nov 2020 |
| 12/10/2020 | v1.33 | v2.23 | Incluye nuevas entradas para ATUM v1 y v2 y las lagunas en los informes de los clientes a finales de septiembre de 2020 |
| 09/01/2020 | v1.32 | v2.22 | Incluye nuevas entradas para ATUM v1 y v2 y las lagunas en los informes de los clientes a partir de agosto de 2020 |
| 22/05/2020 | v1.31 | v2.21 | Incluye nuevas entradas para ATUM 1.0 y 2.0 y las lagunas comunicadas por los clientes |
| 23/04/2020 | v1.30 | v2.20 | Incluye nuevas entradas para ATUM 1.0 y 2.0 y las lagunas comunicadas por los clientes |
| 23/01/2020 | v1.29 | v2.19 | Incluye nuevas entradas para ATUM 1.0 y 2.0 y las lagunas comunicadas por los clientes |
| 15/11/2019 | v1.28 | v2.18 | Incluye nuevas entradas para ATUM 1.0 y 2.0 y las lagunas comunicadas por los clientes |
| 09/06/2019 | v1.27 | v2.17 | Incluye nuevas entradas para ATUM 1.0 y 2.0 y las lagunas comunicadas por los clientes |
| 06/03/2019 | v1.26 | v2.14 | Incluye nuevas entradas para ATUM 1.0 y 2.0 y las lagunas comunicadas por los clientes |
| 24/04/2019 | v1.25 | v.2.13 | Incluye nuevas entradas para ATUM v1 y v2 y las lagunas comunicadas por los clientes |
| 9 de abril de 2019 | v1.24 | v.2.12 | Incluye nuevas entradas para ATUM v1 y v2 |
| 15/2/2019 | v1.23 | v.2.11 | Incluye nuevas entradas para ATUM v1 y v2 |
| 4 de diciembre de 2018 | v1.22 | v2.10 | Incluye nuevas entradas para ATUM v1 y v2 |
| 23/10/2018 | v1.21 | v2.9 | Incluye nuevas entradas para ATUM v1 y v2 |
| 28/8/2018 | v1.20 | v2.8 | Incluye entradas adicionales de instancias puntuales y entradas de RI para las familias de instancias R4 y R5 |
| 16/08/2018 | v1.19 | v2.07 | Incluye nuevas entradas para ATUM v1 & v2 |
| 12/07/2018 | v1.18 | v2.06 | Incluye nuevas entradas para ATUM v1 & v2 |
| 18/04/2018 | v1.17 | v2.05 | Incluye nuevas entradas para ATUM v1 & v2 |
| 16/03/2018 | v1.16 | v2.04 | Incluye nuevas entradas para ATUM v1 & v2 |
| 01/11/2018 | v1.15 | v2.03 | Incluye nuevas entradas para ATUM v1 & v2 |
| 13/12/2017 | v1.14 | v2.02 | Incluye nuevas entradas para ATUM v1 & v2 |
| 27/10/2017 | v1.13 | v2.01 | Incluye nuevas entradas para ATUM v1 & v2  Actualización de las asignaciones que faltan en ATUM v1 |
| 09/08/2017 | v1.12 | v2.0 | Actualizado ATUM v1 lagunas cartográficas |
| 27/07/2017 | v1.11 | v2.0 | Incluye gran cantidad de nuevas entradas basadas en lagunas conocidas y AWS Pricing API  ATUM v2 cartografía incluida como archivo adicional v2.0 |
| 15/05/2017 | v1.10 |  | Incluye nuevas entradas basadas en el contenido de la API de precios AWS |
| 13/03/2017 | v1.9.1 |  | Incluye nuevas entradas basadas en el contenido de la API de precios AWS |
| 19/01/2017 | v1.9 |  | Incluye una gran cantidad de nuevas entradas basadas en el contenido de la API de precios AWS |
|  | v1.8 |  | Incluye nuevas entradas para las lagunas conocidas |
|  | v1.7 |  | Incluye una gran cantidad de nuevas entradas basadas en el contenido de la API de precios AWS |
| 10/06/2016 | v1.6 |  | Varias lagunas en las subtorres | Nuevo contenido de la API de fijación de precios AWS | Subtorres y unidades de medida depuradas  *Nota sobre v1.6 : se ha añadido una nueva columna, ProductCode,. Este nuevo dato no afectará a las búsquedas y se ha añadido para facilitar el proceso de actualización de la cartografía* |
|  | v1.5.1 |  | Incluye una gran cantidad de nuevas entradas basadas en el contenido de la API de precios AWS |
|  | v1.5 |  | Incluye algunas entradas nuevas CloudSearch + una entrada de soporte por defecto (donde UsageType y Operación están en blanco en la factura) |
|  | v1.4 |  | Incluye un gran número de nuevas entradas para nuevos productos y regiones |

Puede descargar el archivo de asignación de la Comunidad Apptio :

[https://community.apptio.com/viewdocument/aws-services-mapping](https://community.apptio.com/viewdocument/aws-services-mapping "(se abre en una pestaña o una ventana nueva)")

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
