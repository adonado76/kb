---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Configuración opcional"
breadcrumb: []
source_path: "cost-transparency/configuration/optionalconfig.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configuración opcional

Los siguientes elementos son opcionales. Configure una o más de las siguientes funciones según sea necesario.

- [Introduzca los costes estimados no relacionados con el proveedor](estmatednonprov.html "Los costes estimados de no proveedores introducidos manualmente corresponden principalmente a los nuevos clientes de Cloud Cost Management que no han actualizado los datos reales con su GL en Costing Standard. Para cualquiera que disponga de Costing Standard, la mejor opción es manejar los costes de los no proveedores a partir de los reales en el modelo de costes de Costing Standard. Existe un enlace entre los dos modelos (modelo CT Cost y modelo CCM Cloud Invoice) que permite hacerlo a través del objeto IT Resource Towers.")
- [Identificar los servicios compartidos](idsharedservices.html "Una parte de sus costes de nube podría atribuirse a los servicios de infraestructura de nube pública compartidos entre los departamentos que crean aplicaciones en la nube pública. Un buen ejemplo es el Soporte Empresarial, cuyos costes podrían ser una gran cantidad global que debe asignarse a los servicios en la nube que consumen directamente los equipos y departamentos de su organización. Los costes de estos servicios de infraestructura compartidos pueden asignarse a aquellos servicios que se consumen directamente, garantizando que los costes para los departamentos de aplicaciones tengan en cuenta todos los costes derivados del uso de proveedores de nube pública.")
- [Mapa AWS Marketplace to ATUM](mapawstoatum.html "Si consumes servicios de AWS Marketplace, debes ingerir y modelar esas facturas igual que tus facturas de servicios de AWS. AWS crea un archivo de facturación de AWS Marketplace independiente para cada informe de facturación que configure que se cree en sus preferencias de facturación.")
- Multidivisa:
  - Para nuevos clientes, actualice el Azure EA Detailed Bill Master Data.CurrencyCode con el código de moneda de la factura.
  - Para clientes existentes, siga estas instrucciones: [Configurar Cloud Cost Management para multidivisa](multicurrency.html "Puede activar la compatibilidad multidivisa para los productos de Apptio Cloud.").
- [Informes diarios/hora - Ampliar o modificar](clouddailyhourlyreports.html "Los informes diarios/hora se basan en un formato de datos que permite un almacenamiento y consulta rápidos y eficientes de conjuntos de datos de gran volumen (como las facturas de nube muy granulares, como el informe de costes y uso de AWS ). En consecuencia, la ampliación del esquema de los conjuntos de datos implicados y la modificación de los informes creados a partir de dichos conjuntos de datos requieren cierta configuración")
