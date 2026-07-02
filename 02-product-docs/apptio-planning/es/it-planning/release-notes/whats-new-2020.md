---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Planificación: Novedades para 2020"
breadcrumb: []
source_path: "it-planning/release-notes/whats-new-2020.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Planificación: Novedades para 2020

## 2.86 - 28 de diciembre de 2020

Novedades
:   Mensajes más detallados en la página de estado de CTI
:   Los usuarios reciben ahora mensajes más detallados y útiles al importar y exportar operaciones en CTI. Los mensajes de error incluyen los detalles necesarios para depurar y resolver el problema.

Mejoras menores
:   Ninguna

## 2.85 - Del 7 al 18 de diciembre de 2020

Sólo versión de mantenimiento
:   Esta versión sólo contiene correcciones de errores y servicios para satisfacer las necesidades operativas.

## 2.86 - 28 de diciembre de 2020

Novedades
:   Renombramiento de columnas
:   Ahora los administradores pueden cambiar los nombres de las columnas que los usuarios ven durante la introducción de partidas presupuestarias. Antes de esta versión, sólo era posible cambiar los nombres de las columnas de las Dimensiones o Listas personalizadas; ahora también es posible hacerlo para las Dimensiones del sistema. Para cambiar el nombre de las columnas, simplemente edite la definición de la Tabla de Partidas deseada en Datos de Referencia. El editor de tablas ahora permite renombrar todas las columnas de tipo Lookup y String.

    ![](../../resources/images/it%20planning_images/release-notes/column-renaming.png)

    Figura 1: Edición de las definiciones de columna de la Tabla de Partidas en Datos de Referencia.

    Renombrar columnas no requiere una operación de Actualizar Referencia para que un plan recoja el cambio. Una vez renombrado, los usuarios verán el nuevo nombre en las cabeceras de las columnas de la tabla de partidas.

    ![](../../resources/images/it%20planning_images/release-notes/colrename-after.png)

    Figura 2: Columnas del sistema renombradas en la tabla de partidas.

    Nota: Cambiar el nombre de una columna simplemente cambia el nombre de visualización utilizado en la tabla de partidas, el cuadro de diálogo mostrar/ocultar columnas, el cuadro de diálogo de filtro y los selectores de agrupación en el análisis de la página Resumen. No cambia el "nombre en clave" subyacente utilizado en las operaciones de Importación/Exportación o CTI

Amortización manual de contratos
:   Ahora es posible importar, introducir y editar manualmente los importes de gastos amortizados por periodo de un contrato. Para facilitarlo, hemos añadido un método de amortización Manual y la posibilidad de cambiar (anular) el método de amortización definido por el Tipo de contrato. Al igual que antes, la selección de un Tipo de contrato rellenará automáticamente el campo Amortización del contrato con el método definido en el Tipo de contrato, pero ahora este campo puede modificarse. Si el método de amortización se establece en Manual, los importes de gastos generados se pueden editar.

    ![](../../resources/images/it%20planning_images/release-notes/manual-amort.png)

    Figura 3: Método de amortización por defecto del tipo de contrato de prórroga.

    Aparecerá un icono con forma de remolino cuando se modifique el método de amortización por defecto del Tipo de Contrato; al hacer clic en él se volverá al método definido por el Tipo de Contrato y se forzará un nuevo cálculo de los importes de amortización de gastos basado en el Importe actual del contrato, la Fecha de Inicio/Final y otros campos relevantes (Amortizar, Prorrogar, etc.).

    ![](../../resources/images/it%20planning_images/release-notes/manual-amort-2.png)

    Figura 4: El método de amortización manual permite modificar directamente los importes de los gastos.

    NOTA: mientras se encuentre en el modo de amortización Manual, cualquier edición realizada a los parámetros del contrato (como Importe, Fecha de Inicio/Final, Prorrogar, etc) no tendrá impacto en los importes de gasto por periodo.

    Ahora también es posible importar partidas de contrato con importes de gastos por período en lugar de tener que calcular los importes en Planning . Para ello, hay que importar las partidas con el Método de amortización de contratos fijado en Amortización manual. Si el Tipo de Contrato está utilizando un método de amortización diferente, entonces el campo Método de Amortización del Contrato por Defecto Anulado debe estar establecido en TRUE.

    ![](../../resources/images/it%20planning_images/release-notes/import-template.png)

    Figura 5: El método de amortización manual puede utilizarse para importar directamente los importes de los gastos contractuales (por periodo).

    Por último, ahora es posible importar partidas contractuales como partidas externas. Las partidas externas se tratan como procedentes de un sistema externo y de sólo lectura dentro de Planning. Utilícelo junto con la amortización manual de contratos para introducir importes de gastos de contratos periódicos que hayan sido calculados por otro sistema.

    ![](../../resources/images/it%20planning_images/release-notes/external-line-items.png)

    Figura 6: Importación de partidas de contratos externos.

Agrupación de dimensiones y descripciones en Apptio BI
:   Ahora puede ver la lista de dimensiones agrupadas por el tipo de dimensión al configurar las visualizaciones. Además, puede pasar el ratón por encima del icono de ayuda situado junto al nombre de la dimensión para ver una descripción de la misma.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_1%20(3).png)

    Figura 7: Agrupación de dimensiones en Apptio BI

    VER TAMBIÉN:

    Guía del usuario: [Planning datos en Apptio BI](../planning/it-planning-data-self-servic-reporting.html "Apptio BI permite a los usuarios crear y compartir sus propios informes personalizados utilizando datos de diversas aplicaciones, incluida Planificación.")

Mejoras menores
:   Ninguna

## 2.83 - Del 9 al 20 de noviembre de 2020

Novedades
:   Soporte Apex Shell

    ITP funciona ahora en el nuevo shell Apex. Los usuarios pueden alternar entre el nuevo panel de navegación izquierdo de la shell o la navegación actual tipo barra de menús a través de su menú de perfil de usuario.

    Para más información sobre Apex, consulte [Sistema de diseño Apex: Actualización de la navegación](https://community.apptio.com/docs/DOC-13878 "(se abre en una pestaña o una ventana nueva)").

Mejoras menores
:   Sólo actualizaciones de mantenimiento del sistema

## 2.82 - 2 de noviembre de 2020

Novedades
:   Soporte de estilismo Apex
:   Hemos realizado pequeños cambios en el estilo de nuestra interfaz de usuario para adaptarla mejor al aspecto de Apex. Apex es la nueva UX común a todo Apptio que se introducirá a finales de este año. Básicamente, hemos cambiado las fuentes y los colores para dar a nuestras aplicaciones un aspecto más limpio y moderno. También hemos modificado el estilo de la cabecera del plan (la zona situada justo debajo de los menús de la aplicación y el inicio del contenido de la página) para separarla limpiamente de la navegación por la aplicación y ofrecer un aspecto más nítido, como puede verse en las imágenes siguientes.

    Nuevo aspecto de la aplicación

    ![](../../resources/images/it%20planning_images/release-notes/apex1.png)

    Aquí puede ver con más detalle los cambios en el estilo de la cabecera del plan. No hay cambios funcionales: todo sigue funcionando igual, sólo tiene un aspecto un poco diferente, y mejor.

    Plan anterior Estilo de cabecera

    ![](../../resources/images/it%20planning_images/release-notes/apex2.png)

    Nuevo estilo de la cabecera del plan

    ![](../../resources/images/it%20planning_images/release-notes/apex5.png)

Dimensiones a nivel de departamento en Apptio BI
:   Hemos añadido nuevas dimensiones (Nivel 1 y Nivel 2) a las fuentes de datos Planning Apptio BI. Nivel 1 y Nivel 2 se refieren al roll-up de departamento superior y al siguiente nivel superior asociados al objeto de coste (departamento) de una partida. El nivel 1 es la primera lista de departamentos que aparecen en el desplegable "Todos los departamentos" en Planning; el nivel 2 es la siguiente lista de departamentos que aparecen debajo de los departamentos del nivel 1. Estas dimensiones apoyan la elaboración de informes a nivel ejecutivo al permitir la agregación de los valores de las partidas del plan hasta los niveles de departamento de los ejecutivos y altos directivos.

    ![](../../resources/images/it%20planning_images/release-notes/apex4.png)

    Figura 1: Valores de nivel 1 y nivel 2 en la lista desplegable "Todos los departamentos" de Planning.

    ![](../../resources/images/it%20planning_images/release-notes/apex6.png)

    Figura 2: Las dimensiones de Nivel 1 y Nivel 2 se encuentran en la configuración de visualización Apptio BI, en la lista desplegable "Add Dimensions" (Añadir dimensiones)

Mejoras menores
:   Ninguna

## 2.81 - 28 de septiembre - 9 de octubre de 2020

Novedades
:   Ocultar datos laborales sensibles a los usuarios
:   Ahora puede identificar columnas laborales sensibles y ocultar esos datos laborales sensibles a los usuarios en. En primer lugar, el administrador identificará las columnas de la pestaña Gastos de mano de obra que son sensibles y deben ocultarse a los usuarios. Entonces, a los usuarios que no deberían tener acceso a datos laborales sensibles se les puede revocar el acceso a esos datos laborales sensibles. Por defecto, los usuarios tendrán acceso a los datos laborales sensibles.

    NOTA: Tras actualizar su inquilino de Planning , los usuarios existentes seguirán teniendo acceso a datos laborales confidenciales. Para revocar el acceso de determinados usuarios a los datos laborales sensibles, revoque el acceso del usuario directamente desde Permisos de objetos de coste.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_1%20(2).png)

    Figura 1: Configuración de los datos laborales sensibles

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_3%20(1).png)

    Figura 2: Concesión de acceso a datos laborales sensibles

    VEA TAMBIÉN: Guía del usuario: [Ocultar el acceso a datos laborales sensibles en Planning](https://community.apptio.com/docs/DOC-13724 "(se abre en una pestaña o una ventana nueva)")

Listas de selección dependientes
:   Las listas de selección dependientes permiten filtrar la lista de valores mostrados en una lista de selección en función de otros valores de la partida. Por ejemplo, la lista de Proveedores puede filtrarse por la selección actual de Clase de Activo para mostrar sólo proveedores de Hardware o Software. Las listas de selección dependientes facilitan a los administradores la restricción del número de opciones disponibles para el usuario durante la introducción de datos de partidas individuales, lo que mejora la calidad de los datos a la vez que proporciona una mejor experiencia de introducción a los usuarios.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_1%20(2).png)

    Figura 3: La tabla con la lista de selección dependiente (derecha) se utiliza para filtrar los resultados, lo que facilita la elección

Mejoras menores
:   Ninguna

## 2.80 - 28 de septiembre - 9 de octubre de 2020

Novedades
:   Ninguna

Mejoras menores
:   Sólo actualizaciones de mantenimiento del sistema

## 2.79 - 14 de septiembre - 25 de septiembre de 2020

Novedades
:   Soporte de instancias CT compartidas en CTI
:   Ahora puede conectar varias instancias ITP a una única instancia CT compartida (por ejemplo, un entorno de pruebas y un entorno ITP principal) utilizando Token Auth como método de autenticación.

    Para obtener más información sobre el proceso de configuración, consulte [Integrar con Transparencia de costes](../planning/integrate-ct.html "Si su organización utiliza tanto Apptio Costing Standard como una aplicación de planificación Apptio, puede integrarlas para compartir datos.") y Panel de integración CT.

Mejoras menores
:   Ninguna

## 2.78 - 31 de agosto - 11 de septiembre de 2020

Novedades
:   Integración mejorada Costing Standard (CTI)
:   Hemos mejorado la experiencia de integración de Costing Standard para ofrecer una gestión centralizada y la importación y exportación con un solo clic con Costing Standard. La página de configuración CTI existente se ha sustituido por una página de menú que centraliza todas las tareas CTI en un único lugar, eliminando la complejidad y el tedio del proceso de intercambio de datos con Costing Standard.

    Cuando acceda a CTI, verá un nuevo panel con las siguientes opciones:

    - Configurar : configure y modifique los ajustes de integración.
    - Importar datos reales: importación masiva de conjuntos de datos reales desde CT
    - Importar datos de referencia : importación masiva de conjuntos de datos de referencia de CT
    - Publicar - exportación masiva de datos del plan a CT
    - Estado - ver el estado de las solicitudes de importación y exportación de datos

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_5.png)

    Nota: Aún puede importar y exportar a CT directamente desde datos de referencia individuales y tablas de elementos de línea del plan a través de las acciones Importar desde CT y Exportar a tabla CT. La nueva experiencia CTI simplemente proporciona un lugar central para realizar operaciones de importación y exportación masivas.

    Para obtener más información sobre el proceso de configuración, consulte [Integrar con Transparencia de costes](../planning/integrate-ct.html "Si su organización utiliza tanto Apptio Costing Standard como una aplicación de planificación Apptio, puede integrarlas para compartir datos.") y Panel de integración CT.

Mejoras menores
:   Ninguna

## 2.77 - 14 de agosto de 2020

Novedades
:   Ninguna

Mejoras menores
:   Actualizaciones de mantenimiento del sistema
:   Esta versión sólo incluye el mantenimiento del sistema y la corrección de errores.
:   Corregido en esta versión:

    - Las tarifas de mano de obra externa son ahora editables. Los usuarios ahora pueden editar las tarifas laborales de las líneas de artículo en la tabla Proyecto > Actividad > Externa.
    - Hemos añadido el botón Actualizar datos de referencia a la barra de cabecera de la Gestión de gastos. Anteriormente, esta operación sólo estaba disponible a través del menú Acciones

## 2.76 - 31 de julio de 2020

Novedades
:   Planning datos en Apptio BI
:   Ahora puede crear y compartir informes personalizados en Apptio BI utilizando los datos del plan de Planning. Puede crear y visualizar informes en Apptio BI que utilicen los últimos datos del plan en tiempo real. Sus informes pueden incluir múltiples visualizaciones, incluidas visualizaciones de diferentes fuentes de datos. Por ejemplo, un mismo informe puede contener visualizaciones tanto de Costing Standard como de Planning.

    Los gastos de departamento están disponibles como fuentes de datos Planning Financials, Labor, Contracts, o Assets en Apptio BI. Tras seleccionar una fuente de datos, puede seleccionar cualquier plan activo en el campo Nombre del plan para utilizarlo en una visualización. Las dimensiones disponibles para los informes son las mismas que las disponibles en la pestaña Gastos del departamento en Planning, incluidas las dimensiones personalizadas. Además de los intervalos de fechas existentes en Apptio BI, también puede seleccionar intervalos de fechas para el próximo año, 2 años en el futuro y hasta 6 años en el futuro para utilizarlos en su visualización.

    NOTA: Tras actualizar su tenant Planning , si su entorno ya dispone de Apptio BI, las fuentes de datos ITP estarán disponibles en Apptio BI en el plazo de 1 hora. Consulte aquí el calendario completo de despliegue. Los permisos existentes a nivel de objeto de coste en Planning se aplicarán en Apptio BI.

    NOTA: Esta función no está disponible actualmente para los inquilinos que funcionan en GovCloud o IRAP.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_1.png)

Importar la depreciación de activos existentes
:   Hemos añadido un nuevo método de depreciación manual, lo que significa que ahora puede importar y editar los importes de depreciación de los activos. También hemos añadido compatibilidad con partidas individuales de activos externos para que pueda importar detalles de activos (e importes de depreciación) desde un sistema externo, de forma que los propietarios del presupuesto puedan ver, pero no editar, las partidas individuales importadas.

    ![](../../resources/images/it%20planning_images/release-notes/pastedimage_3.png)

Mejoras menores
:   Ninguna

## 2.75 - 13 de julio de 2020

Novedades
:   Ninguna

Mejoras menores
:   Sólo actualizaciones de mantenimiento del sistema

## ITP Apptio BI L1, L2 Dimensión - 11 de febrero de 2020

◆ Se aplica a: Planning, Planning Foundation, Project Financial Planning, y/o Service Demand Planning según se indica a continuación.

En este comunicado:

- [Departamento Dimensiones de nivel 1 y 2 en Apptio BI](whats-new-2020.html)
- [Manténgase informado sobre las actualizaciones de productos](whats-new-2020.html)

## Departamento Dimensiones de nivel 1 y 2 en Apptio BI

Ahora puede seleccionar 2 nuevas dimensiones (Nivel 1 y Nivel 2) de las fuentes de datos Planning en Apptio BI. El Nivel 1 y el Nivel 2 son el nivel superior y el siguiente nivel superior del roll-up de departamento asociado con el objeto de coste de la partida. El Nivel 1 es la primera lista de departamentos que aparecen en la lista desplegable "Todos los departamentos" en Planning al seleccionar el departamento para ver el plan. El Nivel 2 es la segunda lista de departamentos que aparecerían bajo el Nivel 1 en la lista desplegable "Todos los departamentos". Esto permitirá al usuario crear una visualización que agregue el plan para los niveles de departamento del ejecutivo y del alto directivo con el fin de elaborar informes ejecutivos.

![](../../resources/images/it%20planning_images/itp-ssr-l1-l2-dimension-1_700x355.png)

Figura 1: Valores de nivel 1 y nivel 2 en la lista desplegable "Todos los departamentos" de Planning. 1 indica valor de Nivel 1 mientras que 2 indica valor de Nivel 2.

![](../../resources/images/it%20planning_images/itp-ssr-l1-l2-dimension-2_700x502.png)

Figura 2: Las dimensiones de Nivel 1 y Nivel 2 se encuentran en la configuración de visualización Apptio BI, en la lista desplegable "Add Dimensions".

VER TAMBIÉN:

- [Utilice los datos de Planning en Apptio BI](https://community.apptio.com/docs/DOC-13547 "(se abre en una pestaña o una ventana nueva)")
- [Planning datos expuestos a Apptio BI](https://community.apptio.com/docs/DOC-13513 "(se abre en una pestaña o una ventana nueva)")

## Manténgase informado sobre las actualizaciones de productos

Para recibir una notificación cuando se actualice esta página, haga clic en el menú Acciones (engranaje) situado en la esquina superior derecha de esta pantalla y, a continuación, en Seguir. Aparecerá un enlace al tema actualizado en su [bandeja de entrada de la comunidad Apptio](https://community.apptio.com/inbox "(se abre en una pestaña o una ventana nueva)"). También puede ver todos los detalles históricos de las versiones del producto; consulte Planning y Gestión financiera: [Novedades (acumulativas) y Próximas versiones](https://community.apptio.com/docs/DOC-1302 "(se abre en una pestaña o una ventana nueva)").

MÁS RECURSOS:

- Véase también [Planning Programa de mantenimiento semanal](https://community.ibm.com/community/user/viewdocument/maintenance-schedule-update?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(se abre en una pestaña o una ventana nueva)").
- Compruebe si las aplicaciones de Apptio Planning tienen algún problema conocido en [Apptio Problemas conocidos](https://community.ibm.com/community/user/viewdocument/introducing-known-issues-it-planni?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(se abre en una pestaña o una ventana nueva)").
