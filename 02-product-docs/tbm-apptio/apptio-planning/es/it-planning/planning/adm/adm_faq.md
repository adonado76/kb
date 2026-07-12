---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "FAQ: Automatización Data Management"
breadcrumb:
  - "Planning"
  - "Solución de problemas y preguntas frecuentes"
source_path: "it-planning/planning/adm/adm_faq.html"
images:
  - "resources/images/gear.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# FAQ: Automatización Data Management

- [¿Dónde puedo ver y editar los ajustes de conexión de Costing Standard ?](adm_faq.html#FAQAutomatedDataManagement__WherecanIviewandedittheCostingStandardconnectionsettings)
- [¿Puedo cambiar el entorno Costing Standard (desarrollo, producción) al utilizar Data Management automatizado?](adm_faq.html#FAQAutomatedDataManagement__CanIchangetheCostingStandardenvironmentdevelopmentproductionwhenusingAutomatedDataManagement)
- [¿Puedo conectarme a la instancia Costing Standard en otro entorno Apptio?](adm_faq.html#FAQAutomatedDataManagement__CanIconnecttoCostingStandardinstanceinanotherApptioenvironment)
- [¿Dónde puedo ver y editar las asignaciones de conjuntos de datos para las dimensiones de los datos de referencia, los datos reales y los datos del plan después de activar Automated Data Management?](adm_faq.html#FAQAutomatedDataManagement__WherecanIviewandeditthedatasetmappingsforreferencedatadimensionsactualsandplandataafterAutomatedDataManagementisenabled)
- [¿Qué ocurre si no quiero activar la opción Data Management automatizada para determinadas funciones? Por ejemplo, en la implementación anterior de Cost Transparency Integration , sólo pude habilitar la compartición de datos de referencia o la compartición de datos reales o la publicación de datos del plan según mis necesidades.](adm_faq.html#FAQAutomatedDataManagement__WhatifIdonotwanttoenableAutomatedDataManagementforcertainfunctionsForexampleintheearlierCostTransparencyIntegrationimplementationIwasabletoenableonlythosereferencedatasharingoractualssharingorpublishingplandataaspermyneed)
- [¿Cómo puedo consultar el estado de Automated Data Management?](adm_faq.html#FAQAutomatedDataManagement__HowcanIviewtheAutomatedDataManagementstatus)
- [¿Cómo puedo borrar la entidad/dimensión personalizada desde Automated Data Management > Entity Mapping para la dimensión personalizada que ya ha sido borrada en Apptio Planning?](adm_faq.html#FAQAutomatedDataManagement__HowcanIdeletethecustomentitydimensionfromAutomatedDataManagementEntityMappingforthecustomdimensionthathasalreadybeendeletedinApptioPlanning)
- [He añadido una nueva dimensión personalizada en Apptio Planning. Quiero importar datos a esta dimensión personalizada desde Costing Standard. ¿Qué debo hacer?](adm_faq.html#FAQAutomatedDataManagement__IhaveaddedanewcustomdimensioninApptioPlanningIwanttoimportdataintothiscustomdimensionfromCostingStandardWhatshouldIdo)
- [Dado que la mayoría de los ajustes de configuración se han trasladado a Automated Data Management UI, ¿qué ocurre con el panel Cost Transparency
  Integration de la versión antigua de Planning?](adm_faq.html#FAQAutomatedDataManagement__Since)

## ¿Dónde puedo ver y editar los ajustes de conexión de Costing Standard ?

Después de activar Automated Data Management, puede comprobar si la configuración de la conexión es adecuada navegando a Automated Data Management > Conexiones. Para activar la integración automatizada de Data Management, consulte Activar la integración automatizada de Data Management en el plan ApptioOne. Cualquier cambio en los detalles de la conexión debe hacerse en la página **Automated Data Management > Connections**. Consulte [Conexiones](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-connections "(se abre en una pestaña o una ventana nueva)") para obtener más información.

## ¿Puedo cambiar el entorno de Costing Standard (desarrollo, producción) cuando utilizo Automated Data Management?

Automated Data Management también conocido como Automated Data Management sólo admite entornos de desarrollo en TBM Studio. Los cambios se importarán o publicarán únicamente en el entorno de desarrollo.

## ¿Puedo conectarme a una instancia de Costing Standard en otro entorno de Apptio?

En la actualidad, Automated Data Management no admite la conexión de la instancia Costing
Standard en un entorno Apptio diferente. Sólo puede configurar los ajustes de conexión a la instancia Costing Standard que esté utilizando el mismo entorno que el de la instancia Planning . Para configurar los ajustes de conexión, consulte [Conexiones](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-connections "(se abre en una pestaña o una ventana nueva)").

## ¿Dónde puedo ver y editar las asignaciones de conjuntos de datos para las dimensiones de datos de referencia, los datos reales y los datos planificados después de habilitar la función « Data Management » (Asignaciones de datos de referencia)?

Cualquier cambio en las asignaciones de conjuntos de datos puede realizarse en la página Automated Data Management **> Entity Mapping**. Consulte [Gestión de entidades](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=management-entity-planning "(se abre en una pestaña o una ventana nueva)") para obtener más información.

## ¿Qué ocurre si no deseo habilitar la función « Data Management » para determinadas funciones? Por ejemplo, en la implementación anterior de Cost Transparency Integration, pude habilitar solo el intercambio de datos de referencia o el intercambio de datos reales o la publicación de datos del plan según mis necesidades.

Si no desea utilizar Automated Data Management para determinadas funciones, asegúrese de que estas funciones específicas no están asignadas en la página Automated Data Management > Entity Mapping. Consulte [Gestión de entidades](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=management-entity-planning "(se abre en una pestaña o una ventana nueva)") para obtener más información.

## ¿Cómo puedo ver el estado de la función « Data Management » (Comprar y pagar automáticamente)?

El estado Data Management se puede ver desde la página Estado en **Data Management**. Para obtener más información, consulte [Estado](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=management-status "(se abre en una pestaña o una ventana nueva)").

Sin embargo, si quieres obtener un registro de errores detallado para solucionar problemas de compartición de datos, sigue los pasos que se indican a continuación:

1. En el Apptio Planning menú, seleccione Configuración (![imagen](../../../../../../03-media/apptio-planning/resources/images/gear.png)) y, a continuación, seleccione Cost Transparency Integration.
2. Seleccione la pestaña Estado.

   Esta página muestra los detalles de los trabajos de Automated Data Management y más información sobre cada uno de ellos, si la hay.

| Campo | Descripción |
| --- | --- |
| Inicio y fin | Las horas de inicio y fin del trabajo correspondiente |
| Iniciado por | ID de correo electrónico del usuario que inició el trabajo |
| Estado | El progreso del trabajo: QUEUE, SUCCESS, SUCCESS WITH WARNINGS, o FAIL |
| Acciones | Acciones de seguimiento que deben realizarse:  - Publicar datos una vez que los trabajos de importación se hayan realizado correctamente (por ejemplo, publicar datos de referencia después de la importación).  - Ver, para buscar y descargar registros de errores de trabajos fallidos. |

## ¿Cómo puedo eliminar la entidad/dimensión personalizada de Automated Data Management > Entity Mapping para la dimensión personalizada que ya se ha eliminado en Apptio Planning?

La versión beta no permite eliminar entidades/dimensiones personalizadas desde Automated Data Management > Entity Mapping. Sin embargo, puede eliminar el nombre del conjunto de datos en la página Asignación de entidades para desactivar las actualizaciones de datos. Si desea eliminar la propia entidad de la página, le recomendamos que registre un ticket de soporte para que podamos realizar la acción en el back-end. Esta función estará disponible con la versión general, y los usuarios finales podrán eliminar las entidades personalizadas no deseadas de los mapas de entidades.

## He añadido una nueva dimensión personalizada en Apptio Planning. Quiero importar datos a esta dimensión personalizada desde Costing Standard. ¿Qué debo hacer?

Estamos trabajando en una solución para agregar automáticamente la dimensión personalizada recién creada en Automated Data Management > Entity Mapping. Sin embargo, en esta versión beta le recomendamos que siga los siguientes pasos para habilitar la dimensión personalizada recién creada para la actualización automática de datos.

1. Cree una nueva dimensión personalizada en Planificación.
2. Cree un conjunto de datos en TBM Studio que desee utilizar para importarlo a la dimensión personalizada recién creada.
3. En la página Planificación, vaya a Perfil de empresa > Configuración, desactive la opción **Data Management automatizada** y guarde los cambios.
4. Ahora, siguiendo los mismos pasos anteriores, vuelva a activar Automated Data Management y guarde los cambios. Deshabilitando y volviendo a habilitar Automated Data Management sincronizará automáticamente la dimensión personalizada recién agregada en Entity Mapping. Consulte [Acceso automatizado a Data Management](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=started-access-automated-data-management "(se abre en una pestaña o una ventana nueva)") para obtener más información sobre cómo habilitar la función.

## Dado que la mayoría de los ajustes de configuración se han trasladado a la interfaz de usuario automatizada de Data Management, ¿qué ocurre con el panel de integración de transparencia de costes de la versión anterior de Planning?

En la versión beta, una vez activada la opción Data Management automatizada, el panel de integración Costing
Standard seguirá estando disponible, aunque sólo para ver el estado de varios trabajos de intercambio de datos y para importar datos reales de Costing Standard a Planning.

Antes de generalizar esta posibilidad, se prevé automatizar por completo la importación de datos reales, de forma similar a la importación de datos de referencia. Una vez que se produzca este cambio, la pestaña Importar desaparecerá del panel de integración de Costing Standard . Después de este cambio, el panel sólo se utilizará para los informes de estado automatizados de Data Management.
