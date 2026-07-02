---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Añadir datos a la tabla Biblioteca de servicios"
breadcrumb: []
source_path: "boit/service-library-table.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Añadir datos a la tabla Biblioteca de servicios

La tabla Biblioteca de servicios incluye información sobre los servicios que ofrece su organización. Puede añadir datos a la tabla cargando los datos desde otra fuente, como una hoja de cálculo Excel. Cargue los datos en una tabla independiente y, a continuación, añada la tabla a la tabla de la biblioteca de servicios. Consulte [Cargar un archivo de datos](../studio/data_studio/upload-data-file.html "Se aplica a: TBM Studio 12.0 y posteriores. TBM Studio acepta datos de archivos planos en formatos separados por comas, tabulaciones, tuberías, tildes, dos puntos y punto y coma. Antes de poder cargar datos, debe crear una tabla en la que se cargarán los datos, si no existe ya.") para obtener más información.

Si los datos originales de la biblioteca de servicios se anexaron a la tabla Todos los servicios comerciales, anexe el mismo archivo de datos sin procesar a la tabla Biblioteca de servicios. No añada todos los servicios empresariales directamente a la biblioteca de servicios; en su lugar, añada sólo el archivo sin procesar. Para más información, véase [Añadir datos](../studio/data_studio/append-data.html "Se aplica a: TBM Studio 12.0 y posteriores").

Datos necesarios de la biblioteca de servicios

- **Precio** - El precio interno fijado para el servicio comercial. Se utiliza en Billing Standard cuando se utilizan cálculos de Precio x Cantidad.
- **Metodología de fijación de precios** - El método utilizado para calcular los valores de devolución o reembolso de Billing Standard .
- **Publicado** - Indica si una partida debe incluirse en las facturas de devolución. Valores: Sí, No.
- **Categoría de Servicio** - Representa el segundo nivel en la taxonomía (jerarquía) de Servicios. Valores recomendados: Desarrollo, Operaciones, Seguridad y conformidad, Estrategia y planificación
- **ID de servicio** - Un identificador único para el servicio.
- **Nombre del** servicio - El nombre del servicio. Representa el tercer nivel de la taxonomía (jerarquía) de los Servicios.
- **Oferta de servicio** - La opción de servicio representada por este elemento. Representa el cuarto nivel de la taxonomía (jerarquía) de los Servicios. Las opciones de servicio ofrecen una elección a los consumidores de la unidad de negocio dentro de un servicio. Por ejemplo, la oferta de portátiles puede incluir: Portátil ultraportátil, Portátil estación de trabajo y Portátil estándar. Las ofertas de correo electrónico pueden incluir: Oro, Plata y Bronce.
- **Tipo de Servicio** - Representa el primer nivel en la taxonomía (jerarquía) de Servicios. Valores recomendados: Servicios de aplicaciones empresariales, Servicios de entrega, Servicios de infraestructura, Servicios al usuario final y Servicios de plataforma.
- **Unidad de medida** - La unidad utilizada para rastrear y prorratear el coste de un servicio empresarial a una o más unidades de negocio. Las unidades de negocio consumen unidades de un servicio. Por ejemplo: buzones de correo electrónico, usuarios de aplicaciones, almacenamiento asignado, etc.

Servicio recomendado Datos de la biblioteca

- **Descripción** - Una descripción del servicio adaptada al consumidor. Si se rellena el campo Descripción larga, se utilizará esa descripción en lugar de esta.
- **Etapa del ciclo de vida** - Estado actual de un servicio. Los valores típicos son: En servicio, Fuera de servicio, Puesta de sol, Incorporación
- **Descripción larga** - Una descripción más detallada del servicio. Si se rellena este campo, se utilizará el texto en lugar del texto del campo Descripción.

Datos opcionales de la biblioteca de servicios

- **Gestor de servicios** - La persona de TI principal responsable del aprovisionamiento y funcionamiento del servicio empresarial.
- **Propietario del servicio** - La persona de TI responsable de la prestación global del servicio empresarial. Sus responsabilidades incluyen la estrategia, definición, selección y rendimiento financiero del servicio.

**Jerarquía de servicios recomendada**

La jerarquía de servicios recomendada por el Consejo TBM puede consultarse aquí: [Taxonomía TBM v2.0](../atum/tbm-taxonomy-v2-definition/intro-taxonomy.html)
