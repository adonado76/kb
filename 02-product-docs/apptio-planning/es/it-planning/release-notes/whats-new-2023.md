---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "notas de la versión 2023"
breadcrumb:
  - "Planning"
  - "Notas del release"
source_path: "it-planning/release-notes/whats-new-2023.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# notas de la versión 2023

## 3.60 - 25 de diciembre de 2023

A partir del lunes 25/12/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.60. Apptio lanza las siguientes funciones en esta versión menor.

- Creación asíncrona de planes (Beta) : El proceso de creación de planes es ahora asíncrono. Los usuarios pueden iniciar el proceso de creación del plan y seguir utilizando la aplicación Planificación para realizar otras tareas. Una vez creado el plan, el usuario recibirá una notificación. *En la versión beta, esta función sólo estará disponible en los entornos sandbox (no principales).* Para saber más, consulte [Creación de planes asíncronos.](../planning/create-budget-plan.html)
- Automatizado Data Management : Los ajustes de conexión se configuran automáticamente cuando se activa la integración ADM desde el Perfil de la empresa. Para obtener más información, consulte [Requisitos previos](../planning/adm/adm_prerequisites.html).
- Confirmación de Borrado de Línea de Gas to - Se mostrará un diálogo de confirmación antes de borrar una línea de gasto. Esta función está disponible en Gastos > Nueva vista. Para obtener más información, consulte [Eliminación de partidas individuales](../planning/working-with-apex-line-items.html "En este tema se explica cómo gestionar las partidas de Apex en la aplicación, lo que incluye añadir, insertar, duplicar, importar, exportar y eliminar partidas.").

## 3.59 - 11 de diciembre de 2023

A partir del lunes 12/11/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.59. Apptio lanza las siguientes funciones en esta versión menor.

## Comparación de planes sobre mano de obra

Ahora es posible comparar los datos Laborales entre dos planes utilizando la Nueva Vista de Gastos. Para saber más, consulte [Comparar los efectivos laborales](../planning/analyze-labor-headcount.html)

## Datos de actividad laboral ETC en Apptio BI

Ahora es posible crear informes Apptio BI para la Actividad Laboral utilizando ETC como unidad de cantidad además de Horas como unidad de cantidad actualmente soportada. Para obtener más información, consulte [los datos sobre la actividad laboral a tiempo completo](../planning/ssr/fte-labor-activity-data.html "Actualmente, los datos disponibles en Apptio BI sólo admiten datos de horas, pero para IIP la planificación de la Actividad Laboral está habilitada utilizando tanto Horas como la unidad ETC. Esta función permite a los usuarios crear informes de asignación utilizando ETC para que puedan analizar el informe de asignación utilizando la capacidad, los detalles de utilización y los datos de asignación mensual por recurso.").

## 3.58 - 27 de noviembre de 2023

A partir del lunes 27/11/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.58. Esta versión sólo contiene actualizaciones de mantenimiento.

Sólo versión de mantenimiento
:   Esta versión contiene actualizaciones de mantenimiento del sistema.

## 3.57 - 13 de noviembre de 2023

A partir del lunes 13/11/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.57. En esta versión menor Apptio lanzará soporte para la Importación Automatizada de Reales desde la Transparencia de Costes a la Gestión de Gastos a través de Data Management Automatizado.

## Importación automatizada de datos reales

Ahora será posible importar automáticamente los datos reales de Transparencia de costes a Gestión de gastos mediante Data Management automatizado. Para obtener más información sobre ApptioOne la planificación y la Data Management integración automatizada, consulte [la descripción general de ADM.](../planning/adm/adm_overview.html "Costing & Planning está integrado con el servicio de plataforma Automated Data Management que permite compartir datos de forma automática desde Costing & Planning Cost (Costing Standard) a Costing & Planning Plan ( Planning), y aporta la capacidad de importar datos del plan bajo demanda desde Costing Standard a un plan específico.")

Para obtener más información sobre cómo importar datos reales con Automated Data Management, visite [Importar datos reales](../planning/adm/adm_import_actuals.html "La importación de datos reales transfiere los datos históricos de gastos desde Apptio Costing a Apptio Planning, donde pueden utilizarse para realizar previsiones, análisis de variaciones y comparaciones de planes.").

## 3.56 - 30 de octubre de 2023

A partir del lunes 30/10/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.56. Esta versión sólo contiene actualizaciones de mantenimiento.

Sólo versión de mantenimiento
:   Esta versión contiene actualizaciones de mantenimiento del sistema.

## 3.55 - 16 de octubre de 2023

A partir del lunes 16/10/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.55. Esta versión sólo contiene actualizaciones de mantenimiento.

Sólo versión de mantenimiento
:   Esta versión contiene actualizaciones de mantenimiento del sistema.

## 3.54 - 3 de octubre de 2023

A partir del lunes 10/03/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.54. Apptio lanza las siguientes funciones en esta versión menor.

## Identificador único externo para líneas de gastos

Las líneas de gastos ahora admiten el Código Único Externo. Los usuarios pueden definir un código único para cada línea de gasto.

Al actualizar los gastos existentes:

- El Código de Partida tiene prioridad sobre el Código Externo si ambos están presentes.
- Si falta el Código de Partida, se utiliza el Código Externo para actualizar los gastos existentes.
- En caso de que el Código de Partida coincida entre las líneas existentes y las importadas pero el Código Externo sea diferente, la operación se trata como una actualización del Código Externo.

Para activar esta función, vaya a Perfil de empresa > Configuración y haga clic en Activar código externo y Guardar cambios.

Para obtener más información, consulte [Identificador único externo](../planning/external-unique-identifier.html "Cuando importas o actualizas datos de gastos (por ejemplo, mano de obra, actividad laboral, contratos, activos) desde sistemas externos (sistemas de RR. HH., bases de datos de proveedores, etc.), Necesita un identificador único y coherente para hacer coincidir las líneas de su plan con los registros del sistema de origen.").

## Integrated Investment Planning Características

## Actualizar los datos de la lista de proyectos

En ApptioOne Plan Release 3.54, hemos simplificado el proceso de actualización de la lista de proyectos utilizando los proyectos de Reference Data > Projects. Utilice la opción Actualizar datos del proyecto del menú de acciones Proyectos > Lista para actualizar los proyectos de la Lista de proyectos con Datos de referencia > Proyectos.

![imagen](../../resources/images/it%20planning_images/proj-list-data.png)

Para más información, visite la sección [Actualizar datos de referencia](../planning/iip/project-list-document.html) en el plan.

## Seleccione Grupos de proyectos en el menú desplegable Proyectos

Ahora es posible seleccionar Grupo(s) de Proyectos en el desplegable Proyectos. Al seleccionar un grupo de proyectos se seleccionarán automáticamente todas las entidades hijas, ya sean grupos de proyectos o proyectos.

![imagen](../../resources/images/it%20planning_images/pg-projects.png)

Nota: En caso de que tenga una jerarquía de proyectos en la que el Grupo de Proyectos no tenga ningún proyecto hoja, dichos grupos de proyectos no se mostrarán actualmente en el desplegable de Proyectos. Por ejemplo, considere la siguiente jerarquía de proyectos. En este caso, el Grupo de Proyectos 1 no aparece en el desplegable de proyectos, pero sí aparecen el Proyecto Group2, el Proyecto Group3 y el Grupo de Proyectos 4. Se trata de una limitación de la versión 3.54, estamos trabajando en su mejora para mostrar todos los grupos de proyectos.

Proyectos Group1

- Proyecto Group2
  - Project1
  - Project2
- Proyecto Group3
  - Project3
  - Project4
  - Proyecto Group4
    - Project5

## Resumen de la actividad laboral

Ahora es posible ver los atributos relacionados de un Recurso como Proveedor, Ubicación, Código Externo, Rol, etc. en Gastos > Actividad Laboral.

Para resumir los datos de la actividad laboral por atributos de recursos laborales relevantes, como Proveedor, Ubicación, Rol, habilite los atributos requeridos en el cuadro de diálogo Mostrar/Ocultar columnas…

![imagen](../../resources/images/it%20planning_images/3.54-labor.png)

## 3.53 - 18 de septiembre de 2023

A partir del lunes 18/09/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.53. Apptio lanza la compatibilidad con el tipo de coste en la gestión de gastos.

## Clase de coste en la Gestión de gastos

Los clientes que utilicen Integrated Investment Planning ahora pueden ver el Tipo de Coste como una columna fuera de la caja en la Gestión de Gastos. Esto ayudará a identificar los gastos reales como de construcción o de ejecución. A partir de ahora será posible extraer los datos reales a medida que se construyen o se ejecutan en los planes de previsión. Si no se indica el valor, se aplicará el valor por defecto Ejecutar a los datos reales cargados.

![imagen](../../resources/images/it%20planning_images/release-notes/3.53-rn_987x238.png)

## 3.52 - 4 de septiembre de 2023

A partir del lunes 09/04/2023, los principales inquilinos de producción comienzan a actualizarse a la versión 3.52. Apptio está lanzando soporte para Guardar Comparación Año-a-Fecha (YTD) en Atajo de Comparación.

## Guardar comparación interanual en el acceso directo a la comparación

Las comparaciones de planes creadas mediante el acceso directo a comparaciones también admitirán y guardarán la comparación interanual (YTD) para los planes de previsión. Para obtener más información, consulte [Comparar versiones o planes.](../planning/compare-versions-plans.html "Puede comparar los datos financieros entre dos períodos o versiones del mismo plan, o entre dos planes diferentes. Estas comparaciones ponen de manifiesto las diferencias entre periodos y partidas para ayudarle a comprender los cambios y las desviaciones.")

## 3.51 - 21 de agosto de 2023

A partir del lunes 21/08/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.51. Esta versión sólo contiene actualizaciones de mantenimiento.

Sólo versión de mantenimiento
:   Esta versión contiene actualizaciones de mantenimiento del sistema.
:   Creación de planes asíncronos - Debido a un problema de producción observado recientemente, hemos desactivado temporalmente la función de creación de planes asíncronos. La creación del plan se ejecutará como una solicitud sincrónica como antes hasta que volvamos a activar la función. Esta función volverá a estar disponible en la versión ApptioOne 3.54.

## 3.50 - 7 de agosto de 2023

A partir del lunes 08/07/2023, los principales inquilinos de producción comienzan a actualizarse a la versión 3.50. Apptio está lanzando soporte para Soft Plan Delete en esta versión menor.

## Plan de supresión suave

El proceso de eliminación del plan se realiza ahora en dos pasos.

- Eliminación suave : el plan se elimina de la interfaz de usuario en cuanto un administrador hace clic en el botón Eliminar de la página Planes. Los usuarios ya no podrán acceder al plan eliminado.
- Borrado permanente : los datos del plan se borran automáticamente dos días después del borrado permanente.

Los administradores ya no tienen que esperar a que se ejecute el largo proceso de eliminación de planes; pueden eliminar un plan rápidamente y continuar con otras tareas. En caso de que borres accidentalmente algún plan, hay un plazo de dos días para restaurar los datos del plan registrando un ticket de soporte en Apptio.

► Más información: [Administrar planes](../planning/manage-plans.html "Con la página Planes, podrá gestionar sus planes de forma fácil e intuitiva.")

## 3.49 - 24 de julio de 2023

A partir del lunes 24/07/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.49. Apptio lanza la compatibilidad con la creación asíncrona de planes y el control de acceso a nivel de proyecto (Beta) en esta versión menor.

## Control de acceso a nivel de proyecto (Beta)

- Sólo PII: Conceda permisos a usuarios como gestores de proyectos/productos en función de cada proyecto. (Independiente del presupuesto del departamento).
- Sólo PII: Estos usuarios pueden ver los gastos de uno o varios proyectos utilizando el filtro Jerarquía de proyectos.

más información sobre [:Control de acceso a nivel de proyecto](../planning/iip/project-level-access-control.html)

## Creación de planes asíncronos

El proceso de creación de planes es ahora asíncrono. Los usuarios pueden iniciar el proceso de creación del plan y seguir utilizando la aplicación Planificación para realizar otras tareas. Una vez creado el plan, el usuario recibirá una notificación.

► Aprende sobre: [Creación de planes asíncronos](../planning/create-budget-plan.html)

## 3.48 - 10 de julio de 2023

A partir del lunes 07/10/2023, los principales inquilinos de producción comienzan a actualizarse a la versión 3.48. Esta versión sólo contiene actualizaciones de mantenimiento.

Sólo versión de mantenimiento
:   Esta versión contiene actualizaciones de mantenimiento del sistema.

## 3.47 - 26 de junio de 2023

A partir del lunes 26/06/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.47. Apptio está lanzando soporte para Añadir y eliminar automáticamente dimensiones personalizadas en la página automatizada Data Management > Mapeo de Entidades en esta versión menor.

## Automatizado Data Management

Esta función es aplicable si está activada la opción Data Management automatizada.

Costing & Planning está integrado con el servicio de plataforma Automated Data Management que permite compartir datos de forma automatizada desde Costing & Planning Cost (Costing Standard) a Costing & Planning Plan ( Planning), y aporta la capacidad de importar datos del plan bajo demanda desde Costing Standard a un plan específico. Para obtener más información, consulte [Descripción general de ADM](../planning/adm/adm_overview.html "Costing & Planning está integrado con el servicio de plataforma Automated Data Management que permite compartir datos de forma automática desde Costing & Planning Cost (Costing Standard) a Costing & Planning Plan ( Planning), y aporta la capacidad de importar datos del plan bajo demanda desde Costing Standard a un plan específico.").

- Añadir automáticamente la asignación de entidades en Automated Data Management cuando se crea una nueva dimensión personalizada en ITP
- Eliminar automáticamente la asignación de entidades en Automated Data Management cuando se elimina una dimensión personalizada en ITP

► Más información: [Asignación de entidades de dimensiones personalizadas](../planning/adm/custom-dimension-entitiy-metric.html)

## 3.46 - 12 de junio de 2023

A partir del lunes 06/12/2023, los principales inquilinos de producción comienzan a actualizarse a la versión 3.46. Esta versión sólo contiene actualizaciones de mantenimiento.

Sólo versión de mantenimiento
:   Esta versión contiene actualizaciones de mantenimiento del sistema.

## 3.45 - 29 de mayo de 2023

A partir del lunes 29/05/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.45. Esta versión sólo contiene actualizaciones de mantenimiento.

Sólo versión de mantenimiento
:   Esta versión contiene actualizaciones de mantenimiento del sistema.

## 3.44 - 15 de mayo de 2023

A partir del lunes 15/05/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.44. Apptio está lanzando soporte para rangos de fechas personalizados con fuentes de datos de Planificación en esta versión menor.

## Intervalos de fechas personalizados para los informes de Apptio BI

ApptioOne Las fuentes de datos de planificación en Apptio BI ahora admiten los siguientes periodos personalizados para las visualizaciones:

- Mes
- Trimestre
- Medio
- Año

Estos periodos personalizados se añaden a los intervalos de fechas existentes. También puede utilizar la opción Desplazar y comparar con estos periodos personalizados. Para obtener más información, visite [Rangos de fechas personalizados](../planning/ssr/custom-date-ranges.html "Los clientes de Cálculo de costes y planificación pueden ahora crear informes plurianuales utilizando intervalos de fechas personalizados.").

## 3.43 - 2 de mayo de 2023

A partir del lunes 05/02/2023, los principales inquilinos de producción comienzan a actualizarse a la versión 3.43. Apptio lanza una ocultación de datos sensibles mejorada en esta versión menor.

## Mayor ocultación de datos sensibles

Si tiene una estructura organizativa en la que hay usuarios que gestionan el personal y las finanzas de sus respectivos departamentos o grupos de departamentos, debe proporcionarles permisos de edición para los respectivos departamentos o grupos de departamentos. Pero al mismo tiempo, si desea que estos usuarios puedan ver los datos financieros de la mano de obra o el recuento de la mano de obra en una jerarquía de departamento superior, excluyendo los datos sensibles para la visibilidad y el conocimiento, tendrá necesidades muy específicas para gestionar los datos sensibles de la mano de obra para este caso de uso.

Por ejemplo:

![imagen](../../resources/images/it%20planning_images/release-notes/esdh-example.png)

En el ejemplo anterior, al usuario CCO2 se le ha dado acceso de Editor en el departamento APPDEV. Dado que los permisos descienden en cascada de arriba a abajo en la jerarquía de objetos de coste, CCO2 obtendrá automáticamente el acceso de Editor en la jerarquía de objetos de coste hija para APPDEV, tanto si se proporciona acceso específico al usuario CCO2 como si no.

Tenga en cuenta que el usuario CCO2 no tiene acceso a la visualización de columnas sensibles en el nivel APPDEV. Pero el usuario CCO2 tiene acceso a las columnas sensibles en APPDEV L3, una jerarquía de objetos de coste hijo en APPDEV.

Con los nuevos cambios en ApptioOne Planificación 3.43 versión, hemos introducido un permiso diferente comportamiento en cascada para los permisos de datos sensibles. Lo que permite controlar los permisos a nivel granular.

En el ejemplo anterior, dado que el usuario CCO2 no tiene permiso para ver las columnas sensibles en el nivel APPDEV, el mismo permiso descenderá en cascada en la jerarquía de departamentos hasta que encuentre un objeto de coste/departamento, ya sea grupo u hoja, en el que se proporcione el permiso para ver las columnas sensibles. Si encuentra uno, entonces ese permiso tiene prioridad sobre el permiso de nivel superior.

Debido a este cambio, ahora es posible proporcionar al usuario CCO2 acceso para ver columnas sensibles en APPDEV L3 aunque CCO2 no tenga permiso para ver columnas sensibles en un objeto de coste de nivel superior APPDEV.

También observará que al usuario CCO2 se le ha concedido acceso explícito para ver columnas sensibles en los objetos de coste de hoja APP-BO y APP-SALES, pero no hay ningún permiso explícito Can View Sensitive Columns concedido en APP-LOB. Pero independientemente de eso CCO2 podrá ver columnas sensibles en APP-LOB porque el permiso del objeto de coste de nivel superior APPDEV L3 se extenderá en cascada a los objetos de coste hijos de nivel inferior. En resumen, no es necesario dar permiso explícito para ver columnas sensibles en todos los objetos de coste de hoja de APPDEV L3 si el permiso para ver columnas sensibles se proporciona en APPDEV L3, se extenderá en cascada a los objetos de coste de nivel inferior bajo APPDEV L3.

Compruebe las capturas de pantalla siguientes para entender la diferencia entre el comportamiento antiguo y el nuevo a la hora de gestionar los permisos de datos confidenciales.

## Comportamiento anterior (Antes de ApptioOne Plan 3.43 )

![imagen](../../resources/images/it%20planning_images/release-notes/esdh-prev.png)

## Nuevo comportamiento (Tras la publicación de ApptioOne Plan 3.43 )

![imagen](../../resources/images/it%20planning_images/release-notes/esdh-current.png)

El ejemplo anterior se refiere específicamente a los permisos de visualización de columnas sensibles, pero las mismas reglas se aplican también a los permisos de visualización de datos financieros sensibles.

NOTA: Los permisos de datos no sensibles (Editor, Propietario y Sólo ver) funcionan igual que antes. El cambio es específico sólo para los permisos de datos sensibles.

## 3.42 - 19 de abril de 2023

A partir del lunes 19/04/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.42. Esta versión sólo contiene actualizaciones de mantenimiento.

Sólo versión de mantenimiento
:   Esta versión contiene actualizaciones de mantenimiento del sistema.

## 3.41 - 12 de abril de 2023

A partir del lunes 04/12/2023, los principales inquilinos de producción comienzan a actualizarse a la versión 3.41. Esta versión sólo contiene actualizaciones de mantenimiento.

Sólo versión de mantenimiento
:   Esta versión contiene actualizaciones de mantenimiento del sistema.

## 3.40 - 20 de marzo de 2023

A partir del lunes 20/03/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.40. Esta versión menor anuncia el lanzamiento de la función Lista de proyectos.

## Lista de proyectos

Los clientes que utilizan Integrated Investment Planning ahora pueden ver todos los proyectos o inversiones junto con sus atributos en una vista de lista a nivel de plan. Mediante la vista de lista, los usuarios administradores pueden ahora añadir, editar o eliminar proyectos a nivel de plan.

![imagen](../../resources/images/it%20planning_images/project-list.png)

![imagen](../../resources/images/it%20planning_images/project-list-view.png)

► Más información: [Lista de proyectos](../planning/iip/project-list-document.html)

## 3.39 - 20 de febrero de 2023

A partir del lunes 20/02/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.39. Esta versión sólo contiene actualizaciones de mantenimiento.

Sólo versión de mantenimiento
:   Esta versión contiene actualizaciones de mantenimiento del sistema.

## 3.38 - 6 de febrero de 2023

A partir del lunes 02/06/2023, los principales inquilinos de producción comienzan a actualizarse a la versión 3.38. Esta versión sólo contiene actualizaciones de mantenimiento.

Sólo versión de mantenimiento
:   Esta versión contiene actualizaciones de mantenimiento del sistema.

## 3.37 - 23 de enero de 2023

A partir del lunes 23/12/2023, los principales inquilinos de producción comenzarán a actualizarse a la versión 3.37. Esta versión menor lanza la posibilidad de Activar/Desactivar la pestaña de Actividad Laboral de Gastos y mejoras en la Nueva Vista de Gastos.

## Activar/Desactivar la pestaña Actividad Laboral

Los clientes que utilicen [Integrated Investment Planning](../planning/iip/gs-integrated-investment-planning.html) ahora pueden activar o desactivar la pestaña Actividad laboral en la página Gastos utilizando la configuración de la página Perfil de la empresa.

## Página de gastos Nueva vista

La página de gastos Nueva vista se actualiza para mostrar las subpestañas Todos, Opex y Capex en la pestaña Gastos > Resumen. Ahora también es posible actualizar los datos de referencia desde la nueva vista.

Para activar "Nueva vista" en Gastos, consulte [Activar tabla de partidas de Apex.](../planning/enable-apex-line-item-table.html)
