---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "ServiceNow Introducción"
breadcrumb:
  - "Costing Standard"
  - "Integraciones tecnológicas"
  - "ServiceNow"
source_path: "cost-transparency/technology-integration/servicenow/sn-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# ServiceNow Introducción

La integración entre IBM, Apptio y ServiceNow es una integración bidireccional diseñada para conectar los datos operativos y de configuración de ServiceNow con los modelos financieros de IBM Apptio, y para mostrar la información sobre costes y TCO de Apptio en ServiceNow.

Este enfoque permite a las organizaciones establecer ServiceNow como el sistema operativo de registro (CMDB, CSDM, Discovery, EA, DPM) y utilizar IBM Apptio como el sistema financiero de registro para los costes tecnológicos, el TCO y la lógica de asignación. El resultado es una visión unificada y fiable de los costes, el consumo y el valor en todas las aplicaciones, servicios y carteras digitales.

La integración se lleva a cabo a través de dos vías complementarias:

- **Ingress** : Incorporar datos de ServiceNow a IBM Apptio utilizando conectores prescriptivos Datalink
- **Salida** : Introducir información de TCO (coste total de propiedad) de IBM Apptio en ServiceNow utilizando aplicaciones certificadas IBM Apptio de la tienda ServiceNow

1. **Evaluación de la preparación**

   Antes de iniciar la integración técnica, considere ponerse en contacto con nuestra organización de Servicios Profesionales para realizar la evaluación de preparación « Apptio » ( ServiceNow ).

   Esta evaluación ayudará a validar la integridad de la CMDB, la alineación del CSDM, la cobertura del descubrimiento y la calidad de los datos antes de la integración.

   Su objetivo es identificar qué áreas están preparadas para la integración, qué casos de uso clave se verán favorecidos y, por lo tanto, qué beneficios o valor empresarial se pueden esperar.
2. **Ingress: Incorporando datos de ServiceNow a Apptio**

   Ingress se centra en obtener datos operativos, de configuración y de relaciones de alta calidad de ServiceNow en IBM Apptio para impulsar modelos de costes precisos y consumibles.
3. **¿Qué datos se ingieren?**

   Mediante el uso de conectores prescriptivos IBM Apptio Datalink, IBM Apptio ingesta datos de almacenes de datos clave ServiceNow, entre los que se incluyen:
   - Elementos de configuración de la CMDB (infraestructura, aplicaciones, servicios)
   - Relaciones entre servicios (catálogo de servicios) y aplicaciones alineadas con CSDM
   - Datos operativos, como tickets, incidentes y volúmenes de tareas (cuando corresponda)
   - Metadatos organizativos y de propiedad (por ejemplo, departamentos, centros de costes)

   Estos datos constituyen la base estructural para el TCO de las aplicaciones, el TCO de los servicios y el reembolso/repercusión de costes en IBM Apptio.

   Seis conectores listos para usar de Datalink incorporan datos en 33 tablas de ServiceNow.

   Nota: Se puede utilizar un conector 7thcustom para incorporar cualquier tabla adicional, según sea necesario.

   Consejo: Al configurar estos conectores Datalink, utilice la casilla de verificación Predeterminado. Esto seleccionará automáticamente los campos más importantes necesarios para fines de asignación y generación de informes en IBM Apptio, al tiempo que ofrece flexibilidad para añadir o eliminar campos según sea necesario.

   |  |  |  |
   | --- | --- | --- |
   | **Datalink Conector** | **IBM Apptio componente** | **Mesas en ServiceNow** |
   | ServiceNow Finanzas | Activos fijos | alm\_activo |
   | Referencia general | cmn\_ubicación |
   | cmn\_centro\_de\_costes |
   | cmn\_departamento |
   | Proyectos | pm\_proyecto |
   | ServiceNow Activos de infraestructura - Inferior | Centro de datos | cmdb\_ci\_centro\_de\_datos |
   | cmdb\_ci\_sala\_de\_ordenadores |
   | cmdb\_ci\_zona |
   | cmdb\_ci\_rack |
   | Red | cmdb\_ci\_netgear |
   | Almacenamiento | cmdb\_ci\_dispositivo\_de\_almacenamiento |
   | cmdb\_ci\_volumen\_de\_almacenamiento |
   | cmdb\_ci\_msd |
   | cmdb\_ci\_servidor\_de\_almacenamiento |
   | Dispositivos de usuario final | cmdb\_ci\_ordenador |
   | ServiceNow Activos de infraestructura - Superior | Sistema principal | cmdb\_ci\_mainframe |
   | cmdb\_ci\_mainframe\_lpar |
   | Servidores | cmdb\_ci\_servidor |
   | Base de datos | cmdb\_ci\_base\_de\_datos |
   |  | cmdb\_ci\_db\_instancia |
   | ServiceNow Relaciones Infra | Relaciones Infra | cmdb\_rel\_ci |
   | svc\_ci\_asoc |
   | ServiceNow Mesa de servicio | Tíquets | incidencia |
   | Problema |
   | solicitud\_de\_cambio |
   | sc\_solicitud |
   | tarea\_ci |
   | ServiceNow Aplicaciones y servicios | Middleware | cmdb\_ci\_servidor\_de\_aplicaciones |
   | cmdb\_ci\_app |
   | Aplicaciones | cmdb\_ci\_aplicación\_empresarial |
   | Servicios | oferta\_de\_servicios |
   | cmdb\_ci\_servicio |
   | cmdb\_ci\_capacidad\_empresarial |
   | **6 conectores** | **15 componentes** | **33 Tablas** |

   Para comenzar con la configuración de los conectores de entrada de Datalink, consulte la siguiente documentación: [Datalink Conector de entrada de ServiceNow : IBM Documentación](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-datalink-servicenow-ingress-connector "(se abre en una pestaña o una ventana nueva)")
4. **Introducir datos en el modelo de costes « IBMApptio » (El modelo de costes de la industria de la energía de EE. UU. para la transición a una economía de bajas emisiones de carbono).**

   Una vez que los datos se hayan incorporado mediante los conectores de entrada de Datalink, aproveche nuestra organización de servicios profesionales para que le ayude a conectar las nuevas fuentes de datos de ServiceNow con los respectivos conjuntos de datos maestros y objetos de modelo de IBM Apptio. Basándose en los casos de uso y los datos incluidos a través de la integración, pueden ayudar a desconectar/reconexionar el modelo y a validar la configuración y los informes mejorados.
5. **Salida: Publicación de « Apptio » (La economía de la nube) TCO Insights Volver a « ServiceNow » (La economía de la nube)**

   Egress se centra en dar a conocer los fiables análisis financieros de IBM Apptio directamente en ServiceNow,, donde ya trabajan arquitectos, propietarios de servicios y líderes digitales.

   **Aplicaciones certificadas « Apptio » en la tienda « ServiceNow »**

   IBM Apptio ofrece **dos aplicaciones certificadas** disponibles en la tienda ServiceNow para dar soporte a casos de uso de salida:
   - **IBM Apptio Coste total de propiedad (TCO) de la aplicación para una arquitectura empresal (EA) de tipo « ServiceNow »**

     Aplicaciones de superficies TCO, factores de coste y tendencias directamente en una EA (arquitectura empresarial) de tipo « ServiceNow » para respaldar las decisiones de racionalización y modernización de aplicaciones.
   - **IBM Apptio Coste total de propiedad del servicio para la gestión de carteras digitales (DPM) de ServiceNow**

     Integra información sobre el coste total de propiedad (TCO) de los servicios en ServiceNow DPM, lo que permite a los propietarios de productos y servicios digitales planificar, crear, ejecutar y calcular el coste de sus carteras utilizando una única solución.

   **Cómo funciona Egress**

   1. **Instala las aplicaciones certificadas IBM Apptio**

      Instale las aplicaciones adecuadas de IBM Apptio de la tienda ServiceNow en función de sus casos de uso de EA y/o DPM.
   2. **Crear informes de TCO en IBM Apptio**

      Cree informes de TCO de aplicaciones y servicios en IBM Apptio TBM Studio, incluyendo los desgloses y métricas necesarios.
   3. **Configurar el conector de salida de Datalink**

      Utilice IBM Apptio Datalink para enviar de forma segura los datos de TCO desde IBM Apptio a ServiceNow.
   4. **Revise la información en los paneles nativos de ServiceNow.**

      IBM Apptio Las métricas de TCO aparecen directamente en los espacios de trabajo de EA y DPM de ServiceNow, lo que proporciona contexto financiero sin que los usuarios tengan que salir de ServiceNow.Para comenzar con la configuración de Egress, consulte la siguiente documentación: [Configurar una conexión Egress de ServiceNow (aplicaciones y servicios) - Documentación de IBM](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-configure-servicenow-egress-connection-apps-services "(se abre en una pestaña o una ventana nueva)")

   Nota: Además de los dos casos de uso de Egress prescriptivos, también se puede aprovechar el conector genérico para enviar cualquier dato de IBM Apptio a ServiceNow. Para empezar, consulte la siguiente documentación: [Configurar una conexión de salida de E ServiceNow (genérica) - Documentación de IBM](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-configure-servicenow-egress-connection-generic "(se abre en una pestaña o una ventana nueva)")
