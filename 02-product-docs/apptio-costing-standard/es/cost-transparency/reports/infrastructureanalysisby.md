---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Análisis de infraestructuras por aplicación"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso del informe"
  - "Recopilación de solicitudes"
source_path: "cost-transparency/reports/infrastructureanalysisby.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Análisis de infraestructuras por aplicación

Este informe ofrece un análisis detallado del porcentaje de uso de aplicaciones por torre de TI (informática, almacenamiento y Service Desk).

Este informe está destinado a:

- Propietarios de aplicaciones
- Propietarios de infraestructuras
- Arquitectos de empresa

El informe proporciona una visión de alto nivel de la infraestructura en todas sus aplicaciones. Puede encontrar detalles sobre el almacenamiento informático de la infraestructura, así como una vista de los datos de la nube y los tickets del servicio de asistencia y de ayuda asociados a sus aplicaciones. Puede utilizar este informe para profundizar en los datos sobre los servidores subyacentes y los dispositivos de almacenamiento (unidades lógicas de almacenamiento) que están asociados a cada aplicación. Por ejemplo, puede utilizar los datos de este informe para analizar una migración a la nube.

El informe Análisis de Infraestructuras por Aplicaciones contiene los siguientes elementos:

![](../../resources/images/ct_images/ct%20report%20collections/infrastructure%20analysis%20by.jpg)

| Elemento clave | Descripción |
| --- | --- |
| (1) Recogida de informes | Esta colección de informes proporciona los detalles financieros de TI que necesita para revisar el uso y el gasto de las aplicaciones:   - [Informe de revisión de la solicitud](application-review.html "Este informe proporciona una visión general ejecutiva del gasto en aplicaciones, desglosado por ejecución de aplicaciones (costes operativos) y desarrollo de aplicaciones (inversiones) para sus principales aplicaciones, familias de aplicaciones y los costes de infraestructura subyacentes basados en las torres de TI ATUM (centro de datos, informática, almacenamiento y red). Una instantánea simplificada de cualquier aplicación está disponible con un rápido clic en cualquier gráfico de barras.") (abierto por defecto) - [Informe sobre la cartera de aplicaciones](application-portfolio.html "Este informe amplía la información del informe Revisión de aplicaciones a toda la cartera de aplicaciones. Este informe le permite ver quién es responsable del conjunto global de aplicaciones en su organización de TI, el gasto por unidad de negocio, los generadores de costes desglosados por torre de TI y proveedor, y el impacto de los proyectos relacionados con las aplicaciones.") - [Informe de la lista de aplicaciones](#infrastructure_analysis_by "Este informe ofrece un análisis detallado del porcentaje de uso de aplicaciones por torre de TI (informática, almacenamiento y Service Desk).") - [Análisis de infraestructuras por aplicación](infrastructureanalysisby.html "Este informe ofrece un análisis detallado del porcentaje de uso de aplicaciones por torre de TI (informática, almacenamiento y Service Desk).") (descrito en esta página) - [Aplicaciones nuevas y retiradas](new-retired-apps.html "Este informe proporciona datos relacionados con su recuento de aplicaciones, uso y cambio YTD.") |
| (2) Cortadoras | Los divisores globales de la colección de informes de Aplicaciones persisten de un informe a otro, por lo que los filtros que establezca en este informe podrían afectar a lo que vea en otros informes de Aplicaciones. Para más información, consulte la sección **Rebanadoras** del [informe Revisión de aplicaciones](application-review.dita "(se abre en una pestaña o una ventana nueva)"). |
| (3) Análisis computacional por aplicación | Vea los porcentajes de uso de virtualización y entorno por aplicación. La tabla proporciona un análisis del perfil de virtualización con métricas para el porcentaje de horas físicas, virtuales, de nube privada y de nube pública utilizadas por cada aplicación. También hay un análisis de entorno que muestra el porcentaje de uso en cada entorno (producción, desarrollo, pruebas y RD).    Seleccione cualquier elemento en la columna Nombre de la aplicación de la tabla para ir al [informe detallado Nombre de la aplicación](../reports-v104/applicationnamedetail.html) con detalles sobre ese elemento. |
| (4) Análisis del almacenamiento por aplicaciones | Vea los porcentajes de uso del nivel de almacenamiento y del entorno por aplicación. La tabla proporciona el porcentaje de uso de los niveles 1, 2 y 3, además del porcentaje de uso en cada entorno (producción, desarrollo, pruebas o DR).    Seleccione cualquier elemento en la columna Nombre de la aplicación de la tabla para ir al [informe detallado Nombre de la aplicación](https://tbmcouncil.jiveon.com/docs/DOC-9217 "(se abre en una pestaña o una ventana nueva)") con detalles sobre ese elemento. |
| (5) Análisis de Service Desk por aplicación | Vea los análisis por tipo de contacto con el cliente (incidente, problema, solicitud de cambio o solicitud de servicio) y nivel de gravedad (crítico, alto, medio o bajo) por aplicación.    Seleccione cualquier elemento en la columna Nombre de la aplicación de la tabla para ir al [informe detallado Nombre de la aplicación](../reports-v104/applicationnamedetail.html "(se abre en una pestaña o una ventana nueva)") con detalles sobre ese elemento. |
| (6) Horas de servidor, total OpEx, OpEx por hora, detalles del entorno | Utilice este conjunto de gráficos y tablas para ver el gasto global en aplicaciones por horas de servidor, el coste total y el coste por hora de servidor por entorno, o aplique filtros en la parte superior del informe para ver una vista específica. |

Puede utilizar este informe para responder a las siguientes preguntas:

|  |  |  |
| --- | --- | --- |
|  | • | ¿Qué infraestructura soporta cada aplicación? |

|  |  |  |
| --- | --- | --- |
|  | • | ¿Cuánta infraestructura consumen las aplicaciones? |

|  |  |  |
| --- | --- | --- |
|  | • | ¿Qué parte de mi cartera de aplicaciones se ejecuta en una infraestructura de nube pública? |

|  |  |  |
| --- | --- | --- |
|  | • | ¿Cómo ha cambiado el coste total de propiedad de una aplicación al migrar a una infraestructura de nube pública? |

|  |  |  |
| --- | --- | --- |
|  | • | ¿Qué costes de infraestructura conllevan mis aplicaciones? |

|  |  |  |
| --- | --- | --- |
|  | • | ¿Cuáles son los servidores asociados a mis aplicaciones por entorno? |

|  |  |  |
| --- | --- | --- |
|  | • | ¿Qué niveles de almacenamiento están asociados a mis aplicaciones por entorno? |

|  |  |  |
| --- | --- | --- |
|  | • | ¿Qué aplicaciones utilizan productos de infraestructura no estándar? |

|  |  |  |
| --- | --- | --- |
|  | • | ¿Qué porcentaje de los costes de las aplicaciones se atribuye a los costes de la infraestructura subyacente? |
