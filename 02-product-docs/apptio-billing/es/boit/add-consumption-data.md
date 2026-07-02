---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Añadir datos de consumo para el cálculo de Precio x Cantidad"
breadcrumb: []
source_path: "boit/add-consumption-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Añadir datos de consumo para el cálculo de Precio x Cantidad

Utilice los datos de consumo cuando desee cobrar a las unidades de negocio en función de su consumo de servicios en lugar de asignaciones de costes basadas en factores como el número de empleados. Si no se conocen datos de consumo adicionales, utilice una lista de los ID de servicio, que puede facilitarse adjuntando los datos brutos de la biblioteca de servicios. No añada la tabla de la propia biblioteca de servicios, pero sí los datos añadidos a la biblioteca de servicios.

Los datos de consumo suelen extraerse de muchas fuentes, como los datos de VM Clusters y las aplicaciones CMDB. Cuando cargue los datos de consumo, asigne a las tablas el nombre del sistema que proporciona los datos y colóquelas en una categoría de Consumo.

Después de cargar los datos de alimentación de consumo, añada las tablas a la tabla Datos maestros de alimentación de consumo. Consulte [Añadir datos](../studio/data_studio/append-data.html "Se aplica a: TBM Studio 12.0 y posteriores") para obtener más información.

A continuación se describen los campos de Datos maestros de alimentación de consumo. Todos los campos son obligatorios.

- ID **de unidad de negocio** : Un identificador único para cada unidad de negocio al nivel más granular, que coincide con el Ident de la tabla de datos maestros de asignación de unidades de negocio.
- **Publicado** : Campo específico del cliente para proporcionar más información sobre el cargo de una línea individual expuesto sólo cuando un usuario mira los detalles del consumo del servicio. Los valores válidos son "Sí" o "No"
- **Cantidad** : Importe o cantidad utilizada para ponderar y prorratear los costes del Servicio de Empresa del objeto Imputaciones de Servicio Directas a la Unidad de Negocio. La cantidad depende de la unidad de medida seleccionada. Por ejemplo, el correo electrónico puede asignarse en función del número de buzones por departamento o de la cantidad total de almacenamiento de correo electrónico por departamento. Otros ejemplos podrían ser el número de usuarios de aplicaciones empresariales por departamento.
- ID **de servicio** : El identificador único para el nombre del servicio en el nivel más granular, que coincide con el ID de servicio en la tabla Todos los servicios empresariales.
- **Fuente** : La tabla que se añade al conjunto de datos maestros.
