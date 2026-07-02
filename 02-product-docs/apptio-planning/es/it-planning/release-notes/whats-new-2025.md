---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Notas de la versión 2025"
breadcrumb:
  - "Planning"
  - "Notas del release"
source_path: "it-planning/release-notes/whats-new-2025.html"
images:
  - "resources/images/it_planning_images/3.84-ibm.jpg"
  - "resources/images/it_planning_images/3.86a.jpg"
  - "resources/images/it_planning_images/3.86b.jpg"
  - "resources/images/it_planning_images/3.88-1.jpg"
  - "resources/images/it_planning_images/3.88-2.jpg"
  - "resources/images/it_planning_images/3.88-3.jpg"
  - "resources/images/it_planning_images/5.5a.png"
  - "resources/images/it_planning_images/5.5b.png"
  - "resources/images/it_planning_images/5.5c.png"
  - "resources/images/it_planning_images/pln-3.89.png"
  - "resources/images/it_planning_images/release-notes/3.84-1.jpg"
  - "resources/images/it_planning_images/release-notes/3.84.jpg"
  - "resources/images/it_planning_images/release-notes/3.91.png"
  - "resources/images/it_planning_images/release-notes/384-1.jpg"
  - "resources/images/it_planning_images/release-notes/5.13.2.png"
  - "resources/images/it_planning_images/release-notes/5.6a.png"
  - "resources/images/it_planning_images/release-notes/5.7a.png"
  - "resources/images/it_planning_images/release-notes/5.7b.png"
  - "resources/images/it_planning_images/release-notes/5.7c.png"
  - "resources/images/it_planning_images/release-notes/5.8a1.png"
  - "resources/images/it_planning_images/release-notes/5.8b.png"
  - "resources/images/it_planning_images/release-notes/5.8c.png"
  - "resources/images/it_planning_images/release-notes/5.8d.png"
  - "resources/images/it_planning_images/release-notes/ml-1.png"
  - "resources/images/it_planning_images/release-notes/ml-2.png"
  - "resources/images/it_planning_images/th-lp.png"
  - "resources/images/it_planning_images/th-menu.png"
  - "resources/images/it_planning_images/thimg.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Notas de la versión 2025

## Lanzamiento 5.14 Sandbox: 22-26 de diciembre de 2025 | Principal: 29 de diciembre de 2025 - 2 de enero de 2026

**Los planes de previsión ahora admiten más períodos reales.**

Los planes de previsión ahora ofrecen mayor flexibilidad al trabajar con datos reales. Anteriormente, los planes de previsión se limitaban a un máximo de 12 períodos reales, independientemente de la duración total del plan. Con esta actualización, los planes de previsión pueden incluir todos los periodos reales disponibles dentro del plazo del plan, lo que permite un contexto histórico más preciso y una mejor previsión en horizontes de planificación más largos.

Para obtener más información, consulte la documentación de ayuda sobre [la creación de planes](https://www.ibm.com/docs/en/SSKZJE8/it-planning/planning/create-plan.html "(se abre en una pestaña o una ventana nueva)").

**API de importación de planes**

Hemos introducido las API de importación de planes, que permiten la importación programática de datos de planes dentro de Apptio Planning. Estas API permiten la ingesta automatizada de datos de planes procedentes de herramientas de terceros, scripts de automatización y otros sistemas, al proporcionar una forma estandarizada de importar planes.

**Principales características**

- **Importar datos de gastos del plan:** El punto final POST importa los datos del plan para todos los tipos de gastos compatibles (como mano de obra, actividad laboral, contratos, activos y otros) utilizando la opción Actualizar o Reemplazar.
- **Archivo de ayuda sobre errores de importación de planes de exportación:** El punto final GET exporta un archivo de ayuda en formato CSV que contiene los errores de importación de datos de los planes, lo que permite a los usuarios analizar y solucionar los fallos de importación.

Para obtener más información, consulte la documentación de ayuda [Plan APIs](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=apis-plan-api "(se abre en una pestaña o una ventana nueva)").

**Corrección de errores**

- Se ha añadido una opción para actualizar automáticamente la página «Estado de la integración de costes de Apptio » cuando hay actualizaciones disponibles, lo que elimina la necesidad de actualizar la página manualmente.
- Se ha solucionado un problema por el que no se mostraban las diferencias entre planes, incluso cuando el usuario tenía los mismos permisos en ambos planes.
- Se ha actualizado el texto de ayuda del cuadro de diálogo «Finalizar plan» para comunicar claramente el comportamiento esperado una vez finalizado el plan.

## 5.13.2 - Todos los entornos: 24 de diciembre de 2025

Control de acceso a nivel de plan: mejoras en la publicación masiva

Hemos mejorado los permisos a nivel de plan para facilitar a los administradores y responsables del proceso presupuestario la gestión y aplicación de los permisos de usuario en todos los planes.

**¿Cuál era el problema?**

Anteriormente, la gestión de permisos a nivel de plan no disponía de una forma eficaz de publicar esos permisos en todos los planes o sincronizarlos con los permisos globales de objetos de coste. Esto a menudo requería actualizaciones manuales, aumentaba el riesgo de inconsistencias entre los planes y dificultaba garantizar que los usuarios tuvieran el acceso correcto a gran escala.

**¿Qué se ha mejorado?**

Los administradores y los propietarios del proceso presupuestario ahora pueden seleccionar una o más filas de permisos en Configuración del plan > Permisos de usuario y publicarlas de forma masiva en todos los planes o en los datos de referencia. En el menú desplegable, seleccione:

- **Publicar permisos seleccionados en todos los planes**
- Aplica los permisos de usuario seleccionados en todos los planes
- Se actualizan los permisos existentes para emparejar usuarios y departamentos.
- Se añaden permisos para nuevos usuarios en los departamentos correspondientes.
- **Publicar permisos seleccionados para datos de referencia**
- Publica los permisos seleccionados en los datos de referencia de Permisos de objetos de coste, manteniendo los permisos globales sincronizados con los cambios a nivel de plan.

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.13.2.png)

## 5.13 - Sandbox: 8-12 de diciembre de 2025 | Principal: 15-19 de diciembre de 2025

**Horizonte de planificación ampliado: ahora hasta 10 años**

Ahora puede crear planes que abarquen hasta 10 años, ampliando el máximo anterior de 6 años. Esta mejora proporciona una mayor flexibilidad para la planificación financiera estratégica a largo plazo, la previsión de inversiones plurianuales y la modelización de escenarios.

**¿Qué está cambiando?**

- Ahora puede seleccionar una duración de **hasta 10 años** al crear un nuevo plan.
- Todas las vistas de gastos, gráficos resumidos y comparaciones entre planes son totalmente compatibles con el plazo ampliado de 10 años.
- En una próxima versión estarán disponibles opciones de diseño adicionales para controlar la granularidad mensual, trimestral y anual en la tabla Gastos.

  Para obtener más información, consulte [Creación de planes](../planning/create-plan.html).

**Editar líneas externas**

Ahora es mucho más fácil gestionar las líneas externas gracias a las completas funciones de edición integradas en el producto: ya no es necesario exportar, modificar sin conexión e importar de nuevo.

**Novedades**

- **Edita o elimina líneas externas directamente en la interfaz de usuario** desde **Gastos → Nueva vista**, sin utilizar el flujo de trabajo de exportación/importación.
- **Disponible para los usuarios con el permiso** « ExternalLineEdit » (Proceso de presupuesto), incluido de forma predeterminada para los administradores y los propietarios del proceso de presupuesto.
- **Habilite el modo de edición** para una sola línea externa o para todas las líneas externas a la vez para realizar actualizaciones más rápidas y eficientes.
- **Elimine líneas externas de forma individual o masiva**, eliminando la restricción anterior que exigía eliminar todas las líneas a la vez.
- **Importar elementos externos sigue estando** disponible para añadir nuevos elementos externos.

  Para obtener más información, consulte [Partidas externas](../planning/ext-li.html "Las partidas externas le permiten gestionar datos de planes que proceden de sistemas externos e incorporarlos a Apptio Planning para su visualización y análisis, sin permitir que los usuarios finales los editen.").

**Planificar API**

Hemos introducido nuevas **API de planes** que permiten el acceso programático a los planes y a los datos de los planes dentro de Apptio Planning. Estas API permiten una integración más profunda con herramientas de BI, scripts de automatización y sistemas descendentes, al proporcionar una forma estandarizada de recuperar planes y exportar los gastos de los planes.

**Principales características**

- **Recuperar todos los planes disponibles para un usuario** : utilice el nuevo punto final GET /planning/api/v1/plans para obtener una lista de los planes a los que puede acceder el usuario autenticado, incluidos los ID y los nombres de los planes.
- **Exportar datos de gastos del plan a través de la API** : el punto final POST /planning/api/v1/plans/{planId }/expenses/export permite exportar datos del plan (resumen, mano de obra, contratos, activos, etc.) en formato « CSV » para su procesamiento externo.

  Para obtener más información, consulte [Plan API](../planning/plan-api.html "Las API REST de planificación de « Apptio » proporcionan un acceso seguro y programático a los planes, los datos de planificación, los metadatos y los elementos relacionados dentro de « Apptio Planning». Estas API están diseñadas para facilitar la automatización y las integraciones de sistemas en casos de uso relacionados con la planificación, la previsión, el análisis, la gobernanza y el intercambio de datos.").

**Nueva interfaz de usuario del perfil de la empresa**

El diseño actualizado presenta un aspecto más limpio e intuitivo que organiza los ajustes por áreas de funciones, lo que le ayuda a navegar más fácilmente por las distintas configuraciones y a descubrir fácilmente las funciones y capacidades que se pueden activar o desactivar.

**Corrección de errores**

- Se ha corregido un problema por el que el texto del menú desplegable Marcadores no se veía completamente.
- Cuando la opción «Ver actualizado» está activada, las columnas «Última actualización» y «Modificado por» se muestran automáticamente y se fijan en el lado izquierdo para una mejor visibilidad.
- Se ha solucionado un problema que provocaba que la creación del plan fallara cuando los datos cargados superaban los límites de caracteres. Los datos que superan los límites permitidos ahora se truncan automáticamente y se muestra un mensaje de advertencia para que los usuarios puedan decidir si desean continuar con la carga.

## 5.12 - 1 de diciembre de 2025

Control de acceso a nivel de plan

Apptio La planificación ahora admite el control de acceso a nivel de plan, lo que permite a los administradores gestionar el acceso de los usuarios por plan. Esta mejora proporciona mayor flexibilidad y seguridad al garantizar que los derechos de visibilidad y edición se definan a nivel de cada plan individual.

**¿Qué está cambiando?**

1. **Nueva página de permisos de usuario a nivel de plan** : ahora cada plan incluye una página **de permisos de usuario** dentro de Plan > Configuración. Los administradores pueden conceder acceso a departamentos específicos directamente a nivel del plan, sustituyendo la dependencia anterior de los permisos globales de objetos de coste. La nueva página de permisos de usuario a nivel de plan también incluye funciones de búsqueda y filtrado para facilitar la gestión. Las actualizaciones de los permisos de usuario se registrarán en el historial de cambios.
2. **Los permisos globales de objetos de coste ahora sirven como plantilla** : los permisos globales ya no controlan el acceso automáticamente. En su lugar:
   1. **Nuevo plan (sin línea base):** los permisos de objetos de coste globales se copian en el plan al crearlo.
   2. **Nuevo plan (con línea de base):** los permisos de usuario del plan de línea de base se copian en el nuevo plan.

   Importante:
   - Ahora se debe conceder acceso **explícitamente** a los usuarios a nivel del plan.
   - Los permisos globales de objetos de coste por sí solos *no* proporcionan acceso a los planes.
   - En una próxima versión, añadiremos una opción para copiar los permisos de los permisos globales de objetos de coste o del plan de referencia al crear un nuevo plan.

   Para aplicar de forma masiva los permisos globales existentes a un plan, los administradores pueden:
   1. Exportar desde Permisos globales de objetos de coste (Configuración > Permisos de objetos de coste)
   2. Importa el archivo « CSV » a la página «Permisos de usuario» del plan (Plan > Configuración > Permisos de usuario)

   En una próxima versión se incluirá una opción de sincronización automática entre los permisos globales de objetos de coste y los permisos de usuario a nivel de plan.

**Comportamiento comparativo**

- Si un usuario no tiene acceso a los mismos departamentos en ambos planes que se comparan, los datos de los departamentos restringidos se ocultarán (se mostrará el icono del ojo).
- Para los campos de datos confidenciales de Gastos > Mano de obra, las comparaciones solo mostrarán valores cuando el usuario tenga acceso a datos confidenciales en *ambos* planes.

**Comportamiento de actualización**

- Los planes existentes conservarán su acceso actual.
- Durante la actualización, los permisos a nivel de plan se completarán automáticamente en función de la configuración actual de permisos de objetos de coste.

Para obtener más información, consulte la documentación de ayuda sobre [permisos de objetos de coste](../planning/manage-cost-object.html).

Campos de hipervínculo

Ahora puedes crear columnas personalizadas de tipo Enlace en Apptio Planning, lo que te permite adjuntar URL, como tickets de Jira, documentación o recursos externos, directamente a tus elementos de línea para una navegación rápida.

- Añade columnas de tipo enlace en la configuración de tu esquema.
- Al hacer clic en un enlace, este se abre en una nueva pestaña del navegador.
- Los campos de enlace son totalmente compatibles con la nueva vista y aparecen como de solo lectura en la vista heredada.

Esta mejora le ayuda a mantener las referencias externas vinculadas a sus datos de planificación para facilitar el seguimiento y agilizar la navegación. Para obtener más información, consulte la documentación de ayuda sobre [los tipos de atributos compatibles](../planning/manage_schema.html "Los esquemas definen la estructura de los datos en la planificación de Apptio. Especifican las tablas, los campos y las relaciones que determinan cómo se almacena, vincula y muestra la información en las pestañas de gastos, como Mano de obra, Contratos, Activos y Finanzas.").

Corrección de errores

- Se ha corregido un problema por el que la fecha de inicio de la prórroga del contrato en la nueva vista comenzaba en la fecha de finalización del contrato en lugar de al día siguiente.

## 5.11 - 17 de noviembre de 2025

Menú desplegable mejorado para departamentos y proyectos

Ahora es más fácil navegar por los planes gracias a las nuevas mejoras en los menús desplegables.

**Menú desplegable del departamento:**

- Selección múltiple de departamentos en todos los niveles jerárquicos
- Editar gastos de varios departamentos a la vez (cuando se utiliza la selección múltiple)
- Edita los gastos de todos los departamentos propios desde la vista «Todos los departamentos»
- Indicadores visuales claros para departamentos de solo lectura
- Vea de un vistazo el recuento de departamentos a nivel de grupo

**Menú desplegable del proyecto:**

- Expanda o contraiga las jerarquías de proyectos para navegar más rápidamente
- Nueva opción «Valor en blanco» en el menú desplegable Proyecto para filtrar los gastos no relacionados con proyectos
- Indicadores visuales claros para departamentos de solo lectura
- Vea de un vistazo el recuento de proyectos a nivel de grupo

Ahora se admiten comparaciones de planes para todos los años (incluidos los planes de 6 años)

Hemos eliminado una limitación anterior que impedía añadir comparativas de planes a planes con una duración de 6 años. Ahora puede añadir comparaciones entre todos los años de su plan, incluidos los planes de 6 años y los planes plurianuales.

Capacidad ampliada de dimensiones personalizadas

Ahora puede definir hasta 40 dimensiones personalizadas, lo que supone un aumento con respecto al límite anterior de 13, lo que le ofrece una flexibilidad significativamente mayor para modelar y segmentar sus datos.

Nuevas mejoras en la vista

**Acciones del flujo de trabajo trasladadas a la interfaz de usuario de nivel superior**

En la nueva vista, ahora se puede acceder directamente a las acciones Enviar, Aprobar/Devolver y Abrir/Finalizar desde la página Gastos, en lugar de tener que hacerlo desde el menú de puntos suspensivos.

**Duplicar varias filas en la nueva vista**

Ahora puede seleccionar y duplicar varias filas a la vez en la nueva vista.

- Utilice la casilla de verificación para seleccionar varias filas.
- Haga clic en el icono Duplicar para copiarlos.
- Las filas duplicadas se insertan directamente debajo de las originales, copiando todos los valores excepto los campos generados por el sistema.

Esta mejora permite replicar varias filas de forma más rápida y sencilla, lo que ahorra tiempo y reduce el esfuerzo manual.

Corrección de errores

- Las carpetas del menú Plan ahora aparecen predeterminadas en estado contraído.
- Se ha solucionado un problema que impedía eliminar carpetas de planes vacías.
- Se ha solucionado un problema por el que los menús desplegables de la vista Nueva vista requerían un doble clic para expandirse. El menú desplegable ahora se expande con un solo clic, en consonancia con el comportamiento de la vista heredada.
- Se ha corregido un problema por el que el campo «Duración» de los contratos mostraba un valor incorrecto. Ahora muestra correctamente la duración del contrato en meses, con dos decimales.

## 5.10 - 27 de octubre de 2025

Marcar los planes como «Activos»

Los administradores ahora pueden [marcar los planes como activos](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=plans-tag-as-active "(se abre en una pestaña o una ventana nueva)") para identificar fácilmente y priorizar los planes más importantes.

- **Marcar como activo:** Marque los planes como activos al crear un nuevo plan o desde la página Planes.
- **Navegación más sencilla:** los planes activos se muestran con la etiqueta «Activo» y siempre aparecen en la parte superior del menú desplegable Plan.
- **Configuración predeterminada del usuario:** al iniciar sesión, los usuarios pasan automáticamente a un plan activo (si hay varios, se selecciona el más reciente).
- **Planes archivados:** los planes archivados no se pueden marcar como activos; si se archiva un plan activo, su etiqueta se elimina automáticamente.

Esto hace que sea más rápido y fácil encontrar y trabajar con los planos que más importan.

Ahora se admite la visualización de partidas actualizadas para vistas de departamentos de grupo.

La función «Ver elementos de línea actualizados» se ha mejorado para admitir situaciones en las que los usuarios ven un grupo o varios departamentos simultáneamente.

Anteriormente, la opción Ver partidas actualizadas solo funcionaba al visualizar un único departamento. Con esta versión, la función ahora opera cuando se seleccionan departamentos agrupados, lo que permite a los usuarios identificar cambios en un ámbito más amplio.

Nueva vista: comparaciones añadidas a contratos, activos y actividad laboral

Ahora puede añadir comparaciones en las pestañas Contratos, Activos y Actividad laboral utilizando la nueva vista.

Anteriormente, las comparaciones solo estaban disponibles en las pestañas Resumen, Mano de obra y Otros. Con esta mejora, ahora puede analizar y comparar datos en todas las pestañas, lo que le ofrece una visión más completa de sus planes y le permite obtener información más detallada sobre las tendencias y variaciones de los costes.

Nueva vista: mejoras en el comportamiento de la búsqueda del menú Filtro

Hemos mejorado el comportamiento del menú de filtro cuando los usuarios realizan una búsqueda para que el filtrado sea más intuitivo y se ajuste al comportamiento habitual de las hojas de cálculo (por ejemplo, Excel). Anteriormente, al introducir una consulta de búsqueda, todos los elementos, incluidos aquellos que no coincidían con la búsqueda, permanecían seleccionados de forma predeterminada. Esto a menudo causaba confusión y resultados de filtrado inesperados.

**¿Qué ha cambiado?**

- **Filtrado de búsqueda más inteligente:** cuando un usuario escribe una consulta de búsqueda en el cuadro de filtro, la opción Seleccionar todo se desmarca automáticamente y solo permanecen seleccionados los elementos que coinciden con la búsqueda. Para seleccionar todos los resultados coincidentes, utilice la opción Seleccionar todos los resultados de búsqueda.
- **Comportamiento de selección precisa:** cualquier cambio que realice después de la búsqueda, como marcar o desmarcar elementos, ahora solo se aplicará a los elementos que se muestran actualmente en los resultados. Si lo desea, puede seleccionar **Añadir selección actual al filtro** para añadir los nuevos resultados de búsqueda al filtro que ya tiene aplicado.
- **Manejo de la selección vacía:** al deseleccionar todos los elementos, ahora se mostrará correctamente un conjunto de resultados vacío.
- **Borrar búsqueda Restablecer:** Al borrar la consulta de búsqueda, se restaura la lista completa con todos los elementos seleccionados de forma predeterminada.

Corrección de errores

- Se ha solucionado un problema por el que al añadir comparaciones de planes se producía un error para los clientes que utilizaban calendarios de 13 períodos.
- Se ha corregido un problema por el que las entradas de fecha en la vista Nueva siempre se aplicaban en formato MM/DD/AAAA, ignorando la configuración regional del usuario. Los campos de fecha ahora siguen correctamente el formato de fecha regional del usuario.
- Se ha corregido un problema por el que al filtrar por nombre de categoría de cuenta no se obtenían resultados correctos cuando varias categorías de cuenta compartían el mismo nombre.
- Se ha resuelto un problema por el que el sistema no mostraba un mensaje de advertencia cuando faltaban datos necesarios en una columna oculta marcada como campo obligatorio.

## 5.9 - 6 de octubre de 2025

Nueva vista: editar mientras se está agrupado en la tabla de gastos

Ahora puede añadir, eliminar y duplicar filas en la nueva vista, incluso cuando está en modo agrupado. Anteriormente, las acciones de edición estaban limitadas por agrupaciones, lo que obligaba a desagrupar antes de realizar cambios. Con esta actualización, puedes editar directamente en modo agrupado, lo que agiliza y hace más eficiente la gestión de tus gastos sin interrumpir tu flujo de trabajo.

Corrección de errores

- Se ha corregido un problema por el que el filtro de partidas individuales mostraba los valores de Código y Nombre cuando eran idénticos. Ahora, el filtro solo muestra el código en la lista de opciones si el código y el nombre son iguales.
- Se ha corregido un problema por el que los atributos personalizados configurados como *numéricos* no mostraban los totales en la fila Total. La fila Total ahora agrega y muestra correctamente los valores de las dimensiones de tipo numérico.
- Se ha resuelto un problema por el que al actualizar los datos de referencia de un plan se podían eliminar involuntariamente los factores de variación y las explicaciones existentes.
- Se ha corregido un problema por el que los atributos personalizados de tipo *Fecha* no respetaban la configuración regional del usuario. Los valores de fecha ahora se muestran en el formato correcto según la configuración regional configurada.
- Se ha corregido un problema por el que la nueva vista permitía a los usuarios introducir más de 255 caracteres en el campo Código externo. Aunque el campo se guardó, posteriormente generaría un error. El código externo ahora está limitado correctamente a 255 caracteres.
- Hemos solucionado un problema por el que, al importar datos a la pestaña Actividad laboral, a veces se marcaban recursos como duplicados cuando se asignaban a varios centros de coste. La causa principal fue que el proceso de importación evaluó el recurso antes que la función laboral del proyecto y el centro de costes del recurso, a diferencia de la secuencia de entrada manual de la interfaz de usuario. El proceso de importación sigue ahora la misma secuencia que la interfaz de usuario, lo que garantiza la coherencia y evita errores de duplicados falsos cuando un recurso está asociado a varios centros de coste.
- Se ha corregido un problema por el que al hacer clic en el espacio vacío entre las opciones de filtro no se seleccionaba correctamente el valor más cercano al clic del ratón.
- Se ha solucionado un problema por el que las comparaciones entre un plan presupuestario y un plan de previsión no se cargaban y daban lugar a un error.
- Se ha resuelto un problema por el que la página Resumen no se cargaba cuando se aplicaba la opción Agrupar por.
- Se ha solucionado un problema por el que el botón Desbloquear no se mostraba a los usuarios administradores en el nivel de departamento terminal.
- Se ha corregido un problema por el que al expandir un grupo con un valor vacío/nulo en Planificación se ocultaban sus partidas. Las partidas individuales ahora se muestran correctamente cuando se agrupan por una columna que contiene valores en blanco.
- Se ha resuelto un problema en el análisis de variaciones por el que las agrupaciones de objetos de coste no se cargaban como se esperaba al expandirlas.

## 5.8 - 22 de septiembre de 2025

**Carpetas del plan**

Mantén tu espacio de trabajo organizado a medida que aumenta el número de planes. Con las carpetas de planes, puede agrupar planes relacionados, optimizar la navegación y gestionarlos de forma más eficiente.

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.8a1.png)

**Características principales:**

- Los administradores pueden crear una estructura de carpetas sencilla de un solo nivel para agrupar planes
- Los planes y las carpetas se ordenan automáticamente por orden alfabético para facilitar la navegación
- Archivar, desarchivar o eliminar carpetas completas (con todos sus planes) en una sola acción
- La estructura de carpetas ahora se refleja en el menú desplegable Plan en toda la aplicación

**Hacer que el campo «Moneda» sea de solo lectura**

La columna «Moneda» de la tabla «Gastos» ahora se puede configurar como «Acceso restringido» desde el esquema. Cuando está habilitado, solo los usuarios con el **EditRestrictedDimensions** permiso pueden modificar los valores monetarios de las partidas individuales.

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.8b.png)

**Actualizar datos reales: selección de varios meses**

La actualización de los datos reales ahora es más flexible. En el modal Actualizar datos reales, puede:

- Utilice el menú desplegable de selección múltiple para elegir varios meses a la vez
- Seleccione rápidamente todos los meses disponibles con la nueva opción «Seleccionar todo»

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.8c.png)

**Añadir fila en nueva vista**

Hemos actualizado la forma de añadir filas en la tabla Nueva vista > Gastos para que coincida mejor con la vista anterior.

Ahora los usuarios pueden:

- Añade una nueva línea utilizando la fila vacía en la parte inferior de la tabla
- Utilice las acciones del menú contextual para insertar una fila arriba o abajo

Vea los campos obligatorios resaltados directamente en la tabla, incluidos los campos ocultos que deben completarse

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.8d.png)

**Corrección de errores**

- La función «Exportar todo» ahora incluye correctamente las columnas de mes, incluso cuando están ocultas en la tabla.
- Las columnas de porcentajes en las tablas de gastos agrupadas ahora muestran los valores agregados correctos en lugar de 0 % o NULL. Si todas las filas comparten el mismo porcentaje, el grupo muestra ese porcentaje. Si las filas contienen porcentajes diferentes, el grupo muestra el recuento único de valores.
- Los nombres de los proyectos ahora se importan correctamente cuando se utiliza la configuración del idioma japonés.
- La gestión de gastos ahora muestra por defecto el mes natural actual del año fiscal activo al navegar. Anteriormente, los inquilinos con calendarios fiscales distintos al periodo enero-diciembre no se ajustaban correctamente.
- Apptio BI Ahora respeta correctamente los permisos de objetos de coste de Planning, lo que garantiza que los usuarios puedan ver datos financieros confidenciales (por ejemplo, la remuneración base) cuando se les concede acceso en Planning.
- El botón «Enviar todos los cambios y finalizar» ahora funciona como se esperaba. Cuando se selecciona, todos los objetos de coste pendientes se aprueban automáticamente y el plan se finaliza.
- Se ha corregido un problema por el que los filtros de columna de la página Gastos no tenían en cuenta correctamente los caracteres especiales o los signos de puntuación en los valores.

## 5.7 - 8 de septiembre de 2025

**Identificadores basados en códigos para proveedores, ubicaciones, funciones y dimensiones personalizadas.**

El proveedor, la ubicación, la función y las dimensiones personalizadas ahora utilizarán el código en lugar del nombre como identificador único.

Este cambio permite actualizar los nombres sin afectar al identificador único, lo que reduce el riesgo de discrepancias en los datos cuando se producen cambios en los nombres.

**Impacto:**

- **Importación de datos del plan:** Debe importar el código en lugar del nombre para el proveedor, la ubicación, la función y las dimensiones personalizadas. Esto también se aplica a los conjuntos de datos que hacen referencia a estas dimensiones, como las tarifas laborales, las reglas de asignación de mano de obra y las partidas de gastos.
  - Las importaciones de planes aceptarán campos de proveedor, ubicación, función y dimensiones personalizadas utilizando [Nombre de la dimensión] (por ejemplo, proveedor) o [Nombre de la dimensión] Código (por ejemplo, código de proveedor). Dado que el código será igual al nombre, los archivos de importación de planes existentes seguirán funcionando sin cambios.
- **Exportación de datos del plan:** al exportar datos, los campos Código y Nombre se pueden exportar como columnas separadas cuando se utiliza *Exportar todo* o *Exportar diseño*. Por ejemplo, la dimensión Proveedor se exportará como **Proveedor** (para Código) y **Nombre del proveedor** (para Nombre).
  - Nota: *La exportación para reimportación* exportará el código de «Proveedor», «Ubicación» y «Función»
- **Apptio Integración de costes:** si está integrando Apptio Costing a través de Cost Transparency Integration (CTI) o Automated Data Manager (ADM), revise y actualice su configuración en Data Studio para asegurarse de que el campo **Código** está asignado correctamente. Los planes publicados en Apptio Costing ahora exportarán **el código** del proveedor, la ubicación, la función y las dimensiones personalizadas. Si sus transformaciones utilizan estos campos, compruebe que sus asignaciones sean correctas.
- **Apptio Conjuntos de datos de costes:** los conjuntos de datos listos para usar que admiten la integración con Apptio Planning se han actualizado para admitir identificadores basados en códigos. Esta actualización está disponible en Apptio Costing Release r12.11.16.

Nota: Las dimensiones existentes se migrarán automáticamente copiando el valor actual del nombre en la nueva columna Código para Proveedor, Ubicación, Función y dimensiones personalizadas, lo que garantiza que las tablas de integración existentes sigan funcionando. Si ya existe un atributo personalizado llamado «Código», se renombrará como « Code2 ».

![identificador de base de código](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.7a.png)

En los menús desplegables de la tabla Gastos, los valores de dimensión ahora se mostrarán como **Código - Nombre** (por ejemplo, « LOC001 : Nueva York»). Si el código y el nombre son iguales, el menú desplegable solo mostrará el código para evitar valores duplicados.

![formato del nombre en clave](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.7b.png)

**Agrupación mejorada en la nueva vista**

Las columnas agrupadas aparecen en una sola columna con una jerarquía clara, totales y grupos ordenables. También puede arrastrar columnas al panel Agrupar por para aplicar o reorganizar rápidamente la agrupación.

![agrupación mejorada](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.7c.png)

**Nuevas guías de formación en la aplicación**

El centro de formación integrado en la aplicación acaba de mejorar con dos nuevas guías paso a paso:

- **Planes de edición** : aprenda a actualizar y gestionar los datos de gastos en sus planes.
- **Comparación de planes y análisis de variaciones** : descubre cómo comparar planes e interpretar las diferencias clave para tomar mejores decisiones.

Acceda a las guías directamente desde el producto, sin necesidad de iniciar sesión ni abrir pestañas adicionales.

**Corrección de errores**

- Se ha corregido un problema por el que los gráficos de cascada de gastos mostraban todas las barras en azul en lugar de utilizar los colores correctos para las variaciones positivas y negativas.
- Se ha actualizado la lógica de la interfaz de usuario para que solo se muestre el KPI de cargos en las páginas Resumen, Panel de control y Gastos cuando la actividad laboral está habilitada en el perfil de la empresa.
- Se ha resuelto un problema que impedía la importación automática de datos reales a la gestión de gastos a través del Administrador de datos automatizado (ADM) cuando el período de datos reales estaba cerrado en la gestión de gastos. Esto garantiza que se respeten los períodos de cierre, manteniendo la integridad de los datos durante las importaciones.

## 5.6 - Del 4 al 17 de agosto de 2025

**Actualiza a un PostgreSQL**

Estamos actualizando todos los entornos principales a PostgreSQL como parte del lanzamiento de 5.6. Esta actualización ofrece un rendimiento mejorado, escalabilidad y compatibilidad con la plataforma a largo plazo. Su entorno se actualizará en el día de actualización designado durante la semana 1 (del 4 al 10 de agosto) o la semana 2 (del 11 al 17 de agosto) del periodo de lanzamiento. Las actualizaciones se procesan por orden alfabético, y los entornos restantes se completan en la semana 2.

No es necesario que su equipo realice ninguna acción. Recomendamos validar sus flujos de trabajo principales después de la actualización para garantizar que todo siga funcionando según lo previsto.

**¿Qué está cambiando?**

- **Migración del backend:** Apptio Se está planificando el traslado de la base de datos actual a PostgreSQL.
- **Rendimiento mejorado:** los usuarios pueden esperar tiempos de carga más rápidos e interacciones más receptivas, especialmente en planes grandes.
- **Mayor escalabilidad:** la nueva infraestructura admitirá mayores volúmenes de datos y necesidades de planificación cada vez mayores.

Si tiene alguna pregunta o duda, póngase en contacto con su gestor de éxito del cliente.

Nota: Los clientes federales serán actualizados entre agosto y diciembre.

**Vista actualizada de partidas individuales**

La vista actualizada de partidas individuales mejora la visibilidad de los cambios recientes en todas las versiones, lo que facilita a los usuarios revisar, realizar un seguimiento y gestionar las actualizaciones de manera eficiente a lo largo del proceso de planificación. Una nueva opción en la página Gastos permite a los usuarios cambiar entre ver todas las partidas o filtrarlas para mostrar solo las partidas actualizadas desde el último envío o instantánea. La columna Acción indica el tipo de cambio realizado: Nuevo, Actualizado o Eliminado.

Nota:

- Las líneas importadas se marcarán como nuevas, con la marca de tiempo y el nombre de usuario de la persona que importó los datos.
- Los datos financieros generados reflejarán los últimos valores actualizados del elemento de origen (por ejemplo, mano de obra, actividad laboral, contratos o activos) que provocó el cambio.
- Las partidas eliminadas o actualizadas debido a la actualización de datos de referencia y la actualización de datos reales no se incluirán.
- Los planes creados a partir de una línea de base heredarán los valores de Última actualización del plan original.

Esta función permite detectar más rápida y fácilmente qué ha cambiado, quién lo ha cambiado y cuándo, lo que ayuda a los equipos a colaborar y validar las actualizaciones del plan con confianza.

![Actualización de líneas de pedido](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/5.6a.png)

**Flujos de trabajo de aprobación multinivel**

El nuevo flujo de trabajo de aprobación multinivel ofrece un enfoque flexible y asíncrono para gestionar las aprobaciones, diseñado para dar soporte a procesos de planificación y cadenas de revisión más complejos. Esta mejora permite a los departamentos definir rutas de aprobación únicas e introduce nuevos niveles de permiso para mejorar el control y la colaboración durante la planificación.

**Capacidades clave:**

- **Enrutamiento multinivel configurable**
  - Configure cadenas de aprobación personalizadas para cada departamento.
  - Defina hasta 10 niveles de aprobación secuenciales.
  - Cada nivel puede incluir usuarios específicos responsables de la revisión y aprobación.
- **Aprobaciones asincrónicas del departamento**
  - Los departamentos se mueven de forma independiente a través de sus cadenas de aprobación definidas.
  - Permite la planificación y aprobación paralelas entre equipos.
- **Nuevo nivel de permiso «Editar»**
  - Permite a los usuarios realizar cambios en los planes sin poder enviarlos para su aprobación.
  - Útil para colaboradores o contribuyentes que no deben activar cambios en el flujo de trabajo de aprobación.
  - El permiso «Editar» está disponible tanto para los flujos de trabajo de aprobación multinivel como para los de aprobación jerárquica.

![flujo de trabajo multinivel](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/ml-1.png)

![flujo de trabajo multinivel](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/ml-2.png)

**Comparación: flujos de trabajo de aprobación jerárquicos frente a flujos de trabajo de aprobación multinivel**

|  |  |  |
| --- | --- | --- |
|  | **Aprobaciones jerárquicas** | **Aprobaciones multinivel** |
| **Ruta de aprobación** | Sigue la jerarquía del departamento, avanzando nivel por nivel a través de los departamentos principales. | Definido por cada departamento, con aprobaciones secuenciales en orden ( L1 → L2 → L3, etc.). |
| **Niveles de aprobación** | Se pueden asignar varios propietarios por departamento o grupo de departamentos, y solo se requiere una aprobación para avanzar. | Admite hasta 10 niveles de aprobación por departamento. Se pueden asignar varios aprobadores por nivel, siendo necesario solo uno para la aprobación. |
| **Presentación grupal** | Admite envíos de departamentos de grupo, en los que al enviar un grupo se envían y aprueban automáticamente todos los departamentos secundarios. | No aplicable. |
| **Flujo de planificación** | Requiere una planificación y presentación sincronizadas (los departamentos secundarios deben presentar sus propuestas antes de que el grupo principal pueda avanzar). | Admite la planificación y revisión asíncronas. Los departamentos pueden presentar y avanzar de forma independiente a través de la cadena de aprobación. |
| **Comportamiento de rechazo** | Rechazar devuelve el plan un nivel atrás en la jerarquía. El propietario de cada nivel debe seguir rechazando para trasladarlo al departamento inferior. | Rechazar un departamento lo devuelve al inicio del flujo de trabajo, lo que obliga al departamento a volver a enviarlo al nivel 1 |
| **Saltar nodos** | Se admite dejando el propietario sin asignar en un nivel, pasando las aprobaciones al propietario del siguiente nivel superior. | No aplicable. |
| **Permisos de usuario** | Permiso de edición de nivel: • **Propietario:** puede editar, enviar y aprobar o devolver planos. Recibe notificaciones por correo electrónico cuando se aprueban o devuelven los planes.  • **Editar y enviar** : permite editar y enviar planes.  • **Editar** : puede editar planes, pero no enviarlos.  • **Solo lectura** : puede ver los planes, pero no puede editarlos ni enviarlos. | Editar permisos de nivel:  • **Propietario:** puede editar y enviar planos. Recibe notificaciones por correo electrónico cuando se aprueban o devuelven los planes.  • **Editar y enviar** : permite editar y enviar planes.  • **Editar** : puede editar planes, pero no enviarlos.  • **Solo lectura** : puede ver los planes, pero no puede editarlos ni enviarlos.  Permiso de nivel de aprobación:  • **Nivel de aprobación:** establezca un nivel de aprobación (1-10) para definir la posición del usuario en el flujo de trabajo de aprobación. |

Consulte **[la Descripción general de los flujos de trabajo de aprobación](../planning/about-approval-workflows.html "Los flujos de trabajo de aprobación en Apptio Planning controlan cómo los planes presentados pasan por las etapas de revisión y aprobación, lo que garantiza que los planes se envíen a las partes interesadas adecuadas para su aprobación. Estos flujos de trabajo proporcionan flexibilidad para adaptarse a la estructura y al proceso de gobernanza de su organización.")** para obtener más detalles e instrucciones de configuración.

**Corrección de errores**

- Se ha solucionado un problema en la vista Nueva en el que al introducir texto en el campo Descripción de la pestaña Mano de obra se producía un error y el valor no se guardaba.
- Se ha mejorado el modo de pantalla completa en la página Nuevos gastos para aprovechar mejor la altura vertical total del navegador.
- Se ha solucionado un problema por el que la publicación automática desde ADM ( Data Management ) a TBM Studio fallaba debido a una desalineación del período fiscal.
- Se ha resuelto un problema por el que los usuarios no podían añadir valores a los campos marcados como obligatorios para la introducción de datos.

## 5.5 - 28 de julio de 2025

**Configuración de precisión decimal**

Los administradores ahora pueden configurar el número de decimales que se muestran en Apptio Planning, con soporte para hasta 8 decimales. Esta configuración controla cómo aparecen los valores numéricos en la interfaz de usuario para todos los usuarios.

![imagen para decimal](../../../../../03-media/apptio-planning/resources/images/it_planning_images/5.5a.png)

![imagen en resumen](../../../../../03-media/apptio-planning/resources/images/it_planning_images/5.5b.png)

Además, ahora los usuarios pueden especificar la precisión decimal en el momento de la exportación para una mayor flexibilidad. Todos los cálculos y el almacenamiento de datos siguen utilizando la precisión total, independientemente de la configuración de la pantalla.

![formatos de exportación](../../../../../03-media/apptio-planning/resources/images/it_planning_images/5.5c.png)

**Corrección de errores**

- Se ha resuelto un problema por el que la función Exportar todo ignoraba las opciones de exportación seleccionadas por el usuario.

## 5.4 - 14 de julio de 2025

**Versión de mantenimiento**

Esta versión contiene actualizaciones de mantenimiento del sistema y correcciones de errores.

**Corrección de errores**

- Para mejorar la claridad y la facilidad de uso, hemos actualizado la etiqueta del menú «Agrupaciones» en Nueva vista a «Grupos por fecha» Este cambio se basa en los comentarios de los usuarios, que destacan la confusión que existe a la hora de encontrar las agrupaciones por mes, trimestre y año. La etiqueta actualizada refleja mejor el propósito del menú: facilitar la localización y el trabajo con datos basados en el tiempo, incluyendo las agrupaciones Total del plan, Año hasta la fecha y Previsión restante.
- Se ha resuelto un problema por el que la dimensión de partida individual «Real» para el código de proyecto hacía referencia incorrectamente al objeto de coste en lugar del ID/código del proyecto.
- Se ha resuelto un problema en el informe « Apptio BI » (Planificación de la estructura de cuentas) de Planning, en el que al añadir filtros en la jerarquía de cuentas se producía un error 500.
- Se ha resuelto un problema por el que los valores numéricos con más de 15 dígitos se exportaban a Excel como texto debido al formato automático de Excel, lo que daba lugar a totales incorrectos.
- Se ha corregido un problema por el que el filtro de intervalo de fechas no limitaba la agrupación por meses/trimestres al año seleccionado, mostrando en su lugar datos de todos los años.

## 5.3 - 23 de junio de 2025

Nota: Esta versión solo es aplicable a los clientes de la versión beta de Postgres.

**Comportamiento mejorado del menú desplegable del departamento**

El menú desplegable «Departamento» ahora muestra dinámicamente solo los departamentos a los que tiene acceso el usuario, en función de sus permisos de objetos de coste. Esta mejora simplifica la navegación y proporciona una visibilidad más clara de los resúmenes de costes de todos los departamentos que el usuario tiene a su cargo.

- Los usuarios administradores seguirán viendo la jerarquía completa del departamento.
- Los usuarios que no sean administradores solo verán los departamentos para los que tengan permisos de visualización o edición.
- Al seleccionar «Todos los departamentos» o un nivel de departamento agrupado, se mostrarán los datos de gastos de solo lectura de todos los departamentos a los que tiene acceso el usuario.

**Corrección de errores**

- Se ha resuelto un problema por el que un plan de previsión no incluía los importes monetarios de la pestaña «Otros» de Finanzas del presupuesto de referencia.
- Se ha solucionado un problema por el que los usuarios no podían duplicar líneas con códigos externos en la vista Nueva vista.
- Se ha corregido un problema por el que el filtro «Proyecto» mostraba el error «Error al cargar los filtros» en determinados planes.
- Se ha resuelto un problema por el que el campo Centro de costes no se rellenaba automáticamente en la pestaña Actividad laboral al seleccionar un proyecto sin un centro de costes predeterminado. En tales casos, el campo debería mostrar ahora por defecto el centro de costes predeterminado del Departamento.
- Se ha corregido un problema por el que se mostraba un error incorrecto al añadir una partida vinculada a un proyecto con un centro de costes predeterminado enviado. En este escenario no debería producirse ningún error.

## 5.2 - 9 de junio de 2025

**PostgresSQL Migración de bases de datos**

Estamos actualizando la Apptio Planninginfraestructura de la base de datos de PostgreSQL,, una plataforma moderna y escalable diseñada para ofrecer un rendimiento más rápido, una mayor fiabilidad y una experiencia de usuario más sólida.

**¿Qué está cambiando?**

- **Migración del backend:** Apptio Planning se está pasando de la base de datos actual a PostgreSQL.
- **Rendimiento mejorado:** los usuarios pueden esperar tiempos de carga más rápidos e interacciones más receptivas, especialmente en planes grandes.
- **Mayor escalabilidad:** la nueva infraestructura admitirá mayores volúmenes de datos y necesidades de planificación cada vez mayores.
- **Fundación para la IA y la automatización:** esta actualización permite futuras mejoras, como previsiones basadas en IA y flujos de trabajo inteligentes.

**Corrección de errores**

- Se ha solucionado un problema por el que el gráfico de tendencia de gastos de la página Panel de control mostraba los datos reales del plan completo en lugar de filtrar solo los proyectos y departamentos a los que el usuario tiene acceso.
- Se ha resuelto un problema que provocaba que los valores del filtro Descripción se solaparan visualmente, lo que dificultaba su lectura o selección al aplicar filtros.
- Se ha resuelto un problema por el que los usuarios sin permiso para ver datos confidenciales encontraban un error en la página Nuevo gasto cuando la remuneración base se marcaba como confidencial. Con esta corrección, la remuneración base quedará ocultada correctamente para los usuarios no autorizados.

## 3.93 - 3 de junio de 2025

Versión de mantenimiento

Esta versión contiene actualizaciones de mantenimiento del sistema y correcciones de errores.

**Corrección de errores**

- Se ha resuelto un problema por el que la dimensión del proyecto renombrada en la planificación integrada de inversiones volvía a su nombre predeterminado al publicarse en Apptio Costing.

## 3.92 - 12 de mayo de 2025

Atención: Esta será la última versión antes de Apptio Planning 5.0.

Para obtener más información sobre los cambios en el ciclo de lanzamiento y la infraestructura de la plataforma, visite: [Próximos cambios en Apptio Planningel ciclo de lanzamiento y la infraestructura de la plataforma de.](https://community.ibm.com/community/user/discussion/upcoming-changes-to-apptio-plannings-release-cycle-and-platform-infrastructure "(se abre en una pestaña o una ventana nueva)")

**Centro de formación en la aplicación**

El centro de formación integrado en la aplicación es una experiencia de aprendizaje incorporada directamente en Apptio Planning. Proporciona orientación paso a paso y a su propio ritmo dentro de la interfaz del producto, sin necesidad de inicios de sesión separados ni portales de ayuda externos. Diseñada para simplificar la incorporación y apoyar el aprendizaje continuo, la guía ayuda a los usuarios a acceder a la formación adecuada en el momento en que la necesitan, lo que impulsa una adopción más rápida y mejora la productividad.

Las guías actuales incluyen:

- Apptio Planning Descripción general
- Acceso a los planes
- Operaciones básicas con tablas de gastos
- Presentación de planes
- Comprobación del estado del plan
- Comparación de planes
- Informes y análisis

El centro de formación integrado en la aplicación está disponible para **todos Apptio Planning los usuarios**, y seguiremos ampliándolo con nuevos temas en el futuro. Para saber más, vea este [vídeo](https://youtu.be/5B-FxNzE_mo "(se abre en una pestaña o una ventana nueva)").

Seleccione el icono del Centro de formación para acceder a las guías de formación:

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/thimg.png)

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/th-menu.png)

**Ahora en versión beta: Asistente de Apptio para IBM Apptio Planning**

Nos complace presentar el Asistente de Apptio, una herramienta de asistencia basada en inteligencia artificial que ayuda a los usuarios a obtener respuestas a preguntas sobre IBMApptio Planning y tutoriales relacionados. Este asistente está diseñado para mejorar la experiencia del usuario proporcionando ayuda bajo demanda, especialmente para los nuevos usuarios que navegan por la plataforma.

El asistente se puede habilitar para usuarios específicos y es ideal para personas que son nuevas en Apptio Planning.

**Qué esperar como probador beta**

Los participantes deben planificar los siguientes compromisos de tiempo:

- Una llamada inicial de 30 minutos para revisar el programa de pruebas
- ~1 hora para interactuar con el asistente y hacer preguntas relacionadas con el producto o con TBM
- Una sesión de retroalimentación de 1 hora para compartir tu experiencia
- Correos electrónicos ocasionales de seguimiento del equipo de IA de Apptio

**¿Te interesa participar?**

Regístrese aquí: [Formulario de registro para la versión beta](https://forms.monday.com/forms/a4fa2efe897704ff5cbe58649f5d6c1b?r=use1 "(se abre en una pestaña o una ventana nueva)")

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/th-lp.png)

**Corrección de errores**

- Se ha solucionado un problema por el que los campos obligatorios de la pestaña «Trabajo» no se resaltaban automáticamente.

## 3.91 - 28 de abril de 2025

Funcionalidad de exportación mejorada

Esta versión mejora la función de exportación al introducir una opción completa «Exportar todo», que permite a los usuarios exportar todas las dimensiones y atributos del esquema del plan.

Mejoras clave:

- Nueva opción «Exportar todo »: exporta un conjunto de datos completo, incluyendo todas las dimensiones y atributos del esquema del plan.
- Opciones de exportación renombradas:
  - «Exportar solo diseño» ahora se denomina «Exportar diseño» para mayor claridad.
  - La opción «Exportar todo» existente ahora se llama «Exportar para reimportar», lo que indica que solo incluye los campos editables necesarios para la reimportación.
- Información sobre herramientas para mayor claridad : cada opción de exportación incluye información detallada sobre herramientas para explicar su finalidad.

Comportamiento de exportación:

- Exportar todo: exporta el esquema completo del plan, incluidas todas las dimensiones y atributos.
- Exportar diseño : exporta el último diseño guardado, incluidas todas las columnas y filtros visibles.
- Exportar para reimportar : exporta todos los campos editables en un formato adecuado para reimportar datos.

Nota: La publicación de datos del plan a través de CTI o ADM seguirá utilizando el formato «Exportar para reimportar» (anteriormente denominado «Exportar todo»). En una próxima versión, la publicación de planes se actualizará para incluir el esquema completo del plan.

Nuevas columnas «Última actualización» y «Modificado por» para las partidas del plan

Hemos añadido una columna «Última actualización» y «Modificado por» a todas las tablas de elementos de línea del plan, incluyendo mano de obra, actividad de mano de obra, contratos, activos y finanzas. Las columnas «Última actualización» y «Modificado por» muestran la fecha, la hora y el nombre de usuario de la última persona que editó cada elemento de la línea. La marca de tiempo se ajusta automáticamente a la configuración regional para ofrecer una experiencia personalizada.

Nota: Al crear un plan a partir de una línea de base, la fecha de última actualización y la información del usuario que lo modificó se transferirán al nuevo plan.

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.91.png)

Corrección de errores

- Se ha resuelto un problema por el que al actualizar los datos reales en un plan abierto o al crear un plan a partir de una línea de base se generaban incorrectamente partidas de previsión con un coste financiero cero, lo que daba lugar a filas innecesarias. Ahora solo se incluyen las partidas con valores financieros.
- Se ha mejorado el rendimiento de la importación de datos del plan de actividad laboral cuando se utiliza el calendario laboral.

## 3.90 - 14 de abril de 2025

Versión de mantenimiento

Esta versión contiene actualizaciones de mantenimiento del sistema y correcciones de errores.

Corrección de errores

- Se ha corregido un error por el que el filtro Proyecto no funcionaba para los usuarios administradores.
- Se ha resuelto un problema de rendimiento que afectaba a la carga de la página Gastos para los usuarios con permisos de nivel Todos los proyectos en Integrated Investment Planning.
- Se ha solucionado un error por el que al abrir un mes en Gestión de gastos se abrían inadvertidamente varios meses y se revertían a su estado «NUEVO».
- Se ha resuelto un problema por el que el análisis de variaciones mostraba variaciones incorrectas en el plan después de realizar cambios en la jerarquía del departamento.

## 3.89 - 31 de marzo de 2025

Comentario sobre la variación de las exportaciones

Esta versión añade la posibilidad de exportar comentarios sobre variaciones como un archivo.csv directamente desde el informe de análisis de variaciones. Con esta mejora, los clientes pueden acceder de manera eficiente a todos los factores de variación y explicaciones en un formato estructurado. Los datos exportados se pueden integrar perfectamente en TBM Studio u otras herramientas de BI para realizar análisis y generar informes más detallados.

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/pln-3.89.png)

Corrección de errores

- Se ha resuelto un problema en la vista Gastos en el que el icono de revertir no era visible cuando se anulaba Trabajo > Remuneración base.
- Se ha solucionado un problema por el que los datos reales del proyecto no se actualizaban después de modificar los detalles del proyecto desde la lista de proyectos.
- Se ha solucionado un problema de rendimiento que afectaba a la carga de la página Gastos para los usuarios con permisos de nivel Todos los proyectos en Integrated Investment Planning.
- Se ha resuelto un problema en el análisis de variaciones por el que se mostraban datos financieros incorrectos para departamentos inexistentes en una comparación de previsiones.
- Se ha corregido un problema por el que se producía un error en el análisis de variaciones cuando un usuario proporcionaba un factor de variación sin añadir un comentario.
- Se ha resuelto un problema por el que al abrir un mes en Gestión de gastos se abrían inadvertidamente varios meses y se revertían a su estado «NUEVO».

## 3.88 - 17 de marzo de 2025

Dimensiones de acceso restringido

Esta versión introduce la posibilidad de que los administradores designen dimensiones específicas como «Acceso restringido», lo que garantiza que solo los usuarios autorizados puedan modificarlas. Esta mejora ayuda a mantener la integridad de los datos y evita cambios no deseados.

Mejoras clave

- Nueva configuración de «Acceso restringido» : Los administradores pueden marcar dimensiones específicas como de acceso restringido en el cuadro de diálogo Editar atributo del sistema dentro del esquema.
- Permisos granulares : Solo los usuarios con el nuevo permiso « EditRestrictedDimensions » pueden editar estas dimensiones.

  ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.88-1.jpg)
- Visualización de solo lectura : los usuarios que no dispongan de este permiso verán las dimensiones de acceso restringido como de solo lectura en toda la tabla Gastos.
- Nueva herramienta de información sobre herramientas : al pasar el cursor por encima de los campos de acceso restringido, aparecerá una herramienta de información que indicará que la dimensión es de solo lectura.

  ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.88-2.jpg)
- Comportamiento de importación :
  - Los usuarios con permiso de « EditRestrictedDimensions » pueden importar y modificar dimensiones de acceso restringido.
  - Los usuarios sin permiso de « EditRestrictedDimensions » (Acceso restringido) verán cómo las dimensiones de «Restricted Access» (Acceso restringido) se omiten automáticamente durante la importación, conservando los valores existentes.
  - Un mensaje de advertencia notificará a los usuarios cuando se ignoren las dimensiones de acceso restringido durante la importación.
- Historial de cambios : los cambios en las dimensiones de acceso restringido se registran en el historial de cambios.
- Permisos : Se ha introducido un nuevo permiso « EditRestrictedDimensions » (Permiso de gestión de procesos de presupuesto) y se ha asignado a los roles de administrador y propietario del proceso de presupuesto en Frontdoor.

Configuración mejorada del umbral de varianza con operador AND/OR

Esta actualización introduce un tipo de operación «AND/OR» en las configuraciones de varianza, lo que ofrece a los usuarios una mayor flexibilidad a la hora de establecer los umbrales de varianza. Los usuarios ahora pueden elegir entre:

- Y – La variación debe cumplir tanto los umbrales de valor absoluto como los de porcentaje.
- O – La variación debe cumplir los umbrales de valor absoluto o porcentaje.

  ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.88-3.jpg)

Enlaces comunitarios actualizados

Los enlaces a recursos comunitarios se han actualizado a sus nuevas ubicaciones en la plataforma comunitaria IBM.

Corrección de errores

- Los valores periódicos FTE exportados ahora se redondean correctamente y se limitan a dos decimales.

## 3.87 - 3 de marzo de 2025

Solo versión de mantenimiento

Esta versión contiene actualizaciones de mantenimiento del sistema y correcciones de errores.

Corrección de errores

- Se ha optimizado la lógica de cálculo de la delegación para evitar la degradación del rendimiento al añadir elementos de línea.
- Se ha resuelto un problema en Apptio BI por el que un usuario no podía acceder a la fuente de datos «Planificación» en la gestión de fuentes de datos.
- Se ha eliminado la dimensión duplicada del proyecto en la integración de costes de Apptio cuando Integrated Investment Planning está habilitada. (Requiere un estándar de Apptio ).
- Se ha resuelto un problema por el que las dimensiones de fecha se mostraban como « NaN » cuando las partidas se agrupaban en la vista nueva.
- Se ha corregido un problema por el que la configuración de agrupación en la nueva vista no se mantenía como se esperaba.

## 3.86 - 17 de febrero de 2025

Análisis de varianza mejorado

Esta versión amplía las capacidades de análisis de variaciones, permitiendo a los usuarios administradores comparar las previsiones con los planes (presupuestos o previsiones) en estados abiertos y nuevos para cualquier período de tiempo seleccionado, como la variación anual completa.

Mejoras clave

- Ahora los usuarios pueden configurar análisis de varianza entre el pronóstico y el plan (presupuesto o pronóstico) para períodos de tiempo flexibles, lo que permite un seguimiento y una planificación financiera más completos.
- Todos los planes activos en los estados Abierto y Nuevo ahora están disponibles en el menú desplegable Comparar con plan al configurar el análisis de varianza. Sin embargo, tenga en cuenta que los propietarios de centros de coste no tendrán acceso al análisis de variaciones al comparar con un plan en el nuevo estado.
- Se ha añadido la columna «Categoría de cuenta» a la tabla «Análisis de variaciones», lo que permite una mejor categorización y seguimiento de los datos financieros.

  ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.86a.jpg)
- Anteriormente, el análisis de varianza se limitaba a comparar las previsiones con los resultados reales, pero esta mejora ofrece una mayor flexibilidad para analizar el rendimiento financiero en diferentes escenarios.

  Nota: Al comparar con los Periodos de previsión, los usuarios administradores pueden seleccionar « Actualizar análisis de variaciones » para actualizar los cálculos de variaciones, lo que garantiza que los importes de las variaciones reflejen las últimas actualizaciones de las previsiones. Esta opción está disponible en «...» menú de la página Análisis de variaciones.

  ![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.86b.jpg)

Extensiones de contrato variables para contratos externos

Hemos ampliado la función de ajustes de extensión de contratos variables para admitir contratos externos, que se utilizan para importar partidas de contratos como solo lectura.

- Configurar ajustes de prórroga de contratos compuestos para contratos externos.
- Defina porcentajes de ajuste únicos para cada prórroga de contrato.

Al incorporar estos ajustes, se puede lograr un modelo financiero más preciso, que tenga en cuenta factores como la inflación y los cambios en los tipos de interés a lo largo de ciclos de planificación plurianuales. Para obtener más información, consulte [aquí](../planning/vrbl-cntc-ext-adj.html "Apptio La planificación permite ampliar los contratos más allá de su fecha de finalización original, con diferentes capacidades dependiendo de si se utiliza la vista heredada o la nueva vista.").

## 3.85 - 3 de febrero de 2025

Total restante en los planes de previsión

Esta versión introduce una nueva función en la vista Nueva que permite a los usuarios activar o desactivar la columna Previsión restante en los planes de previsión. El pronóstico restante proporciona una suma de todos los períodos de pronóstico del primer año del plan, lo que ofrece una visión rápida y consolidada de los importes pronosticados restantes.

Corrección de errores

- Se ha corregido un problema por el que los ajustes del filtro no se conservaban al cambiar entre pestañas en la página Gastos.
- Se ha corregido un problema en los informes de « Apptio BI » (Actividad laboral por trimestre) en el que los datos de FTE (equivalente a tiempo completo) de la actividad laboral se mostraban incorrectamente cuando se agrupaban por intervalos trimestrales, semestrales o anuales. Esta corrección se aplica a Integrated Investment Planning.
- Se ha resuelto un problema por el que la importación de permisos de objetos de coste no generaba un error para los nombres de usuario inexistentes en Frontdoor.
- Se ha solucionado un problema por el que los datos del plan exportados no se ajustaban a la configuración de formato numérico establecida.
- Se ha resuelto un problema por el que el valor del atributo booleano «Centro de costes» se mostraba incorrectamente como «falso» en las comparaciones de planes.
- Se ha corregido un problema por el que el centro de costes no se rellenaba automáticamente en la pestaña «Mano de obra» después de crear una nueva línea de artículo.
- Se ha corregido un problema por el que la función ADM ( Data Management ) cargaba los datos de previsión en el año fiscal incorrecto para los calendarios fiscales con fechas de inicio distintas a enero.
- Se ha corregido un problema por el que la función de comentarios se desactivaba al utilizar la configuración regional japonesa.
- Se ha resuelto un problema por el que el campo «Tipo de contrato» no se guardaba al añadir una nueva fila en la pestaña Contratos cuando se utilizaban los ajustes del idioma japonés.

## 3.84 - 20 de enero de 2025

Ajustes variables por prórroga del contrato

Esta versión introduce la función «Ajustes variables de la prórroga de contratos», que ofrece una mayor flexibilidad en el modelado de los costes de los contratos. Con esta funcionalidad, usted puede:

- Aplicar el ajuste de la prórroga compuesta en cada renovación del contrato.
- Ampliar el contrato por un periodo inferior a la duración del plan, en lugar del comportamiento predeterminado actual, que consiste en ampliar siempre el contrato por la duración total del plan.
- Establezca diferentes porcentajes de ajuste de la prórroga para cada renovación del contrato.
- Proporcione comentarios para respaldar cada ajuste de renovación

Esta función permite realizar modelos más precisos al tener en cuenta cambios financieros específicos, como la inflación o los ajustes de tipos, en ciclos de planificación plurianuales.

Nota : Esta función solo está disponible cuando la Nueva vista está habilitada.

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.84.jpg)

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/3.84-1.jpg)

Para obtener más información, consulte [Ajuste de la prórroga del contrato variable](../planning/vrbl-cntc-ext-adj.html "Apptio La planificación permite ampliar los contratos más allá de su fecha de finalización original, con diferentes capacidades dependiendo de si se utiliza la vista heredada o la nueva vista.").

Indicadores clave de rendimiento (KPI) de los gastos del proyecto

Esta versión introduce nuevos KPI de gastos de proyecto disponibles cuando Integrated Investment Planning está habilitado, junto con información sobre herramientas añadida a todos los KPI para mejorar la usabilidad:

- Total del proyecto : muestra el total combinado de los gastos operativos ( OpEx ) y de capital ( CapEx ) asociados a un proyecto. Esto se calcula como la suma de las partidas financieras en las que el ID del proyecto no es nulo.
- Total de cargos : muestra el total de créditos aplicados de los gastos de actividad laboral del proyecto, calculado como la suma de las partidas en las que el tipo de coste = cargos.

Estos KPI están disponibles en las páginas Gastos > Resumen, Panel de control y Resumen. Además, el KPI «Total de cargos» se incluye en «Gastos» > «Actividad laboral ». Con la incorporación de las descripciones emergentes, los usuarios ahora pueden ver explicaciones detalladas de cada KPI directamente en la interfaz, lo que mejora la claridad y la facilidad de uso.

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/384-1.jpg)

IBM Planning Analytics Integración

Nos complace anunciar la integración de IBM Planning Analytics con IBM Apptio, lo que permite una conectividad perfecta entre estas plataformas para mejorar la planificación y el análisis financieros. Esta integración bidireccional permite a los usuarios unificar sus procesos de planificación, alinear los datos financieros y tomar decisiones más precisas y basadas en datos en toda su organización.

Características principales :

- Sincronice automáticamente los datos financieros entre IBM Planning Analytics y IBM Apptio para garantizar una visión coherente de los presupuestos, las previsiones y los datos reales.
- Combine las capacidades de gestión financiera de TI de Apptio con las herramientas de planificación y previsión de IBM Planning Analytics para obtener procesos de planificación más completos e integrados.
- Reduzca el esfuerzo manual y los errores con el intercambio automatizado de datos, garantizando que los planes financieros estén siempre actualizados.

Para habilitar los conectores de datos IBM Planning Analytics, consulte la guía de configuración que se incluye a continuación.

[IBM Planning Analytics Guía de configuración de integración](https://www.ibm.com/docs/en/apptio-platform/datalink/saas?topic=connectors-configure-planning-analytics-connection "(se abre en una pestaña o una ventana nueva)")

Nota : Esta integración requiere IBM Planning Analytics Software como servicio (nube).

![img](../../../../../03-media/apptio-planning/resources/images/it_planning_images/3.84-ibm.jpg)

Corrección de errores

- Se ha resuelto un problema por el que los usuarios administradores no podían ver las columnas marcadas como confidenciales después de asignar permisos de objetos de coste con restricciones de visualización.
- Se ha solucionado un problema con la línea base del plan de previsión, por el que al seleccionar un mes de inicio de la previsión en el año 2, el plan de línea base no copiaba las líneas de todos los años.
- Se ha solucionado un problema en Gastos > Contratos, donde los valores predeterminados no se rellenaban al añadir una nueva línea de contrato con las dimensiones «Fecha de inicio» o «Fecha de finalización» ocultas.
- Se ha resuelto un problema con la importación de datos reales en el que, al proporcionar un código de proyecto en lugar de un código de objeto de coste, se producía un error de asignación de objeto de coste y centro de coste no válido.
- Se ha migrado el cuadro de diálogo Crear análisis de varianza a la interfaz de usuario moderna. Nota: Esta actualización es únicamente una mejora visual sin cambios funcionales.
- Se ha resuelto un problema por el que al importar listas con caracteres especiales se añadían comillas dobles no deseadas a los valores de texto.
