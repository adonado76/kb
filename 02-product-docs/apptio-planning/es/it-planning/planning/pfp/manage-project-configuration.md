---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Datos de referencia de la configuración del proyecto"
breadcrumb: []
source_path: "it-planning/planning/pfp/manage-project-configuration.html"
images:
  - "resources/images/icons/icon-options_23x20.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Datos de referencia de la configuración del proyecto

◆ Se aplica a: Apptio Planning aplicaciones con [Project Financial Planning](gs-project-financial.html "◆ Se aplica a: Planificación con proyecto Planificación financiera."). Las tareas que se describen a continuación requieren una licencia de Project Financial Planning. Para activar las funciones de Project Financial Planning , consulte [Editar el perfil de la empresa](../edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.").

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

|  |  |
| --- | --- |
| icono de cámara | Vea este vídeo de Apptio Education Services: [Configuración de datos de referencia: Project Financial Planning Dimensiones](https://community.ibm.com/community/user/viewdocument/configuring-reference-data-project?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(se abre en una pestaña o una ventana nueva)"). |

## Gestionar los datos de referencia del proyecto

Las dimensiones son las categorías de datos esenciales en las partidas presupuestarias. Muchas dimensiones integradas dependen de otras dimensiones (para más información, véase [-](../manage-reference-data.html) ). Puede importar datos de referencia de dimensiones desde un archivo.csv o desde Costing Standard y exportar plantillas de datos de referencia de dimensiones y datos de tablas (véase [Gestionar dimensiones](../manage-reference-data.html "(se abre en una pestaña o una ventana nueva)") ).

Consejo: Los usuarios asignados al rol Admin disponen de un acceso directo para publicar los datos de referencia del Proyecto. En la pestaña Lista de la vista Resumen de todos los proyectos, utilice el botón Acciones, comando Publicar en Datos de Referencia. Tenga en cuenta que una vez que los datos del proyecto se publiquen de esta forma, no podrá volver a los datos de referencia del proyecto anterior. Si desea archivar esos datos, expórtelos a formato.csv antes de publicarlos de esta forma.

Los proyectos son un tipo de objeto de coste. La siguiente información describe los campos de las dimensiones del proyecto.

1. En el menú de navegación, seleccione Configuración > Datos de referencia.
2. Seleccione la pestaña Proyecto en la página Datos de referencia.
3. En la tabla Proyecto, seleccione Proyecto.
4. Seleccione ![más opciones](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Exportar.
5. En la ventana Exportar archivo, en Opciones de formato, puede cambiar el formato de los datos exportados.
6. Seleccione Exportar. Los datos de referencia se exportan como archivo.csv.
7. Abra el archivo.csv descargado. No modifique los títulos de las columnas ni la estructura de datos del fichero. Actualice los valores de la tabla de datos según sea necesario:
   - Código - Identificador único de un proyecto.
   - Nombre - Nombre del proyecto.
   - Código padre - Representa la jerarquía de su proyecto. El valor de un código padre es el valor del código de su cuenta inmediatamente superior o padre (si existe).
   - Permitir Cualquier Centro de Coste - Un valor de TRUE le permite asignar el proyecto a cualquier Centro de Coste. Un valor de FALSE toma por defecto el Centro de Coste actual.
   - Importe del beneficio - Valor monetario previsto del proyecto finalizado. Este valor y el Periodo de Beneficio se utilizan para calcular el rendimiento de la inversión.
   - Periodo de Beneficio - El número de meses hasta que el proyecto devuelva un beneficio monetario. Este periodo y el valor del Importe de la Prestación se utilizan para calcular el rendimiento de la inversión.
   - Código de moneda - Moneda común del proyecto. Este valor es necesario cuando el soporte para múltiples monedas está habilitado en el Perfil de la empresa (consulte [Soporte para múltiples monedas](../support-multiple-currencies.html) ). El valor monetario común debe ser el código ISO de tres letras de la moneda. Si no se introduce ningún código de moneda, se utilizará la moneda común por defecto.
   - Descripción - Resumen del proyecto.
   - Duración - La duración prevista del proyecto en número de meses.
   - Tiempo de CapEx (no mano de obra) - El valor estimado de los gastos de capital ( CapEx ) para el proyecto. Se utiliza para evaluar la demanda frente a la capacidad.
   - Tiempo de Mano de obra externa - La mano de obra externa estimada (por ejemplo, proveedores) para el proyecto. Se utiliza para evaluar la demanda frente a la capacidad.
   - Tasa de mano de obra externa - La tasa de pago estimada para la mano de obra externa para los proyectos. Se utiliza para evaluar la demanda frente a la capacidad.
   - Tiempo de Mano de obra interna - La plantilla de mano de obra interna estimada para el proyecto. Se utiliza para evaluar la demanda frente a la capacidad.
   - Tiempo de Tasa de mano de obra interna - La tasa de pago estimada para la mano de obra interna del proyecto. Se utiliza para evaluar la demanda frente a la capacidad.
   - Tiempo de Capitalización de la mano de obra - La tasa estimada de capitalización de la mano de obra interna y externa para el proyecto. Se utiliza para evaluar la demanda frente a la capacidad.
   - Tiempo de OpEx (no laboral) - El valor estimado de los gastos de funcionamiento ( OpEx ) para el proyecto. Se utiliza para evaluar la demanda frente a la capacidad.
   - Clasificación del grupo - Valor numérico que indica la clasificación relativa del proyecto entre todos los grupos de proyectos.
   - Grupo de precios - Determina el grupo de precios del proyecto para los modelos de precios por regiones o por niveles.
   - Jefe de proyecto - El jefe de proyecto asignado. Elija entre las cuentas de usuario definidas a través de Enhanced Access Administration.
   - Estado del proyecto - Valor del estado del proyecto.
   - Clasificación - Valor numérico que indica la clasificación relativa del proyecto entre todos los proyectos.
   - Puntuación - Valor numérico que indica la puntuación global relativa del proyecto entre todos los grupos de proyectos.
   - Puntuación anulada - Esta dimensión se utiliza en la exportación e importación de datos de referencia del proyecto. Al exportar datos, esta dimensión indica si el valor de Puntuación se ha calculado automáticamente (valor Falso), o se ha anulado manualmente (Verdadero). Al importar datos, Verdadero significa que el valor de Puntuación anulará cualquier valor calculado automáticamente. Falso significa ignorar el valor de Puntuación cargado, y calcular automáticamente uno en su lugar.
   - Fecha de inicio - Fecha prevista de inicio del proyecto.
   - Código de Centro de Coste - El identificador de los Centros de Coste correspondientes. Al importar los reales, se asignan por Centro de Coste y luego se asignan a Objeto de Coste. Un proyecto puede estar asociado a múltiples Centros de Coste y puede incluir partidas (volúmenes, mano de obra o gastos) registradas para más de un Centro de Coste. Añada múltiples Centros de Coste a la celda de la tabla utilizando una coma para separarlos.
8. Guarde el archivo en formato.csv. Ahora, seleccione **Configuración > Datos de referencia > Proyecto**.
9. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Importar. Arrastre y suelte el archivo con los datos en la zona resaltada de la ventana Importar archivo **> Importar**.
10. Para publicar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Publicar > Publicar.
11. Para cancelar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Revertir > Revertir.

Los datos de referencia de Permisos de Objetos de Coste determinan quién puede editar cada Proyecto y quién puede aprobar presentaciones de planes presupuestarios.

## Gestionar los datos de referencia de los grupos de proyectos

Los datos de referencia del grupo de proyectos representan la estructura jerárquica de proyectos de su organización. Los Grupos de Proyectos son visibles en el menú de la Subsección del Plan y en la página de Proyectos, Resumen.

1. En el menú de navegación, seleccione Configuración > Datos de referencia.
2. Seleccione la pestaña Proyecto en la página Datos de referencia
3. En la tabla Proyecto, seleccione Grupo de proyectos.
4. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Exportar.
5. En la ventana Exportar archivo, en Opciones de formato, puede cambiar el formato de los datos exportados.
6. Seleccione Exportar. Los datos de referencia se exportan como archivo.csv.
7. Abra el archivo.csv descargado. No modifique los títulos de las columnas ni la estructura de datos del fichero. Actualice los valores de la tabla de datos según sea necesario:
   - Código - Identificador único del grupo de proyectos.
   - Nombre - El nombre del Grupo de Proyecto.
   - Código Padre - Representa su jerarquía de Grupos de Proyectos. El valor de un código padre es el valor del código de su cuenta inmediatamente superior o padre (si existe).
   - Código de moneda - La moneda común para el Grupo de Proyectos. Este valor es necesario cuando se habilita el soporte para múltiples monedas en el Perfil de la Empresa. El valor de la moneda común debe ser el código ISO de tres letras de la moneda. Si no se introduce ningún código de moneda, se utilizará la moneda común por defecto.
   - Grupo de precios - Determina el grupo de precios del proyecto para los modelos de precios por regiones o por niveles.
   - Código de Centro de Coste - El identificador de los Centros de Coste correspondientes. Al importar los reales, se asignan por Centro de Coste y luego se asignan a un Objeto de Coste. Un proyecto puede estar asociado a múltiples Centros de Coste y puede incluir partidas (volúmenes, mano de obra o gastos) registradas para más de un Centro de Coste. Añada múltiples Centros de Coste a la celda de la tabla utilizando una coma para separarlos.
8. Guarde el archivo en formato.csv. Ahora, seleccione **Configuración > Datos de referencia > Grupo de proyectos**.
9. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Importar. Arrastre y suelte el archivo con los datos en la zona resaltada de la ventana Importar archivo **> Importar**.
10. Para publicar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Publicar > Publicar.
11. Para cancelar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Revertir > Revertir.

## Gestionar los datos de referencia de las clases de actividad

La dimensión Tipos de actividad es utilizada por Labor Activity Planning. Véase [la función Acceso anticipado: Planificación de la actividad laboral](../labor-activity-planning.html "La versión del 20 de marzo de 2019 de las aplicaciones de planificación 2.45 de Apptio introdujo un modo alternativo para la planificación de la mano de obra del proyecto denominado Planificación de la actividad laboral. El Administrador o el Propietario del Proceso Presupuestario pueden hacer visibles en la interfaz las funciones de Planificación de la Actividad Laboral."). Esta dimensión se utiliza para asociar partidas de Asignación y Demanda con una Clase de Actividad.

1. En el menú de navegación, seleccione Configuración > Datos de referencia.
2. Seleccione la pestaña Dimensiones estándar en la página Datos de referencia.
3. Seleccione > Tipos de actividad.
4. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Exportar.
5. En la ventana Exportar archivo, en Opciones de formato, puede cambiar el formato de los datos exportados.
6. Seleccione Exportar. Los datos de referencia se exportan como archivo.csv.
7. Abra el archivo.csv descargado. No modifique los títulos de las columnas ni la estructura de datos del fichero. Actualice los valores de la tabla de datos según sea necesario:
   - Nombre - Describe la naturaleza del trabajo para la actividad.
   - Es capitalizable - Identifica la actividad como capitalizable.
   - Cuenta de transferencia - El código de cuenta del libro mayor del proyecto desde el que se carga el coste de la actividad.
   - Cuenta de transferencia - El código de cuenta del libro mayor del Departamento al que se abona el coste de la actividad.
8. Guarde el archivo en formato.csv. Ahora, seleccione **Configuración > Datos de referencia > Grupo de proyectos**.
9. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Importar. Arrastre y suelte el archivo con los datos en la zona resaltada de la ventana Importar archivo **> Importar**.
10. Para publicar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Publicar > Publicar.

## Gestionar los datos de referencia de las tasas de actividad laboral de los departamentos

La dimensión Tasas de Actividad Laboral de los Departamentos es utilizada por Labor Activity
Planning. Véase [la función Acceso anticipado: Planificación de la actividad laboral](../labor-activity-planning.html "La versión del 20 de marzo de 2019 de las aplicaciones de planificación 2.45 de Apptio introdujo un modo alternativo para la planificación de la mano de obra del proyecto denominado Planificación de la actividad laboral. El Administrador o el Propietario del Proceso Presupuestario pueden hacer visibles en la interfaz las funciones de Planificación de la Actividad Laboral."). Esta dimensión se utiliza para establecer una tarifa laboral para roles específicos.

1. En el menú de navegación, seleccione Configuración > Datos de referencia.
2. Seleccione la pestaña Dimensiones estándar en la página Datos de referencia.
3. Seleccione las tasas de actividad laboral del departamento.
4. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Exportar.
5. En la ventana Exportar archivo, en Opciones de formato, puede cambiar el formato de los datos exportados.
6. Seleccione Exportar. Los datos de referencia se exportan como archivo.csv.
7. Abra el archivo.csv descargado. No modifique los títulos de las columnas ni la estructura de datos del fichero. Actualice los valores de la tabla de datos según sea necesario:
   - Departamento - El identificador único del Departamento.
   - Centro de Coste - El identificador de los Centros de Coste correspondientes.
   - Tipo de empleado - Recurso laboral interno o externo (como proveedores o contratistas).
   - Rol - Las opciones disponibles para esta dimensión vienen dadas por los datos de referencia de Roles.
   - Moneda - La moneda común para la imputación de la actividad laboral. Obligatorio cuando está habilitada la compatibilidad con múltiples monedas (consulte [Compatibilidad con múltiples monedas](../support-multiple-currencies.dita "(se abre en una pestaña o una ventana nueva)") ). El valor de la moneda común del Departamento debe ser el código ISO de tres letras de la moneda. Si no se introduce ningún código de moneda, se utilizará la moneda común por defecto.
   - Tasa de mano de obra - La tasa de compensación por hora por defecto.
8. Guarde el archivo en formato.csv. Ahora, seleccione **Configuración > Datos de referencia > Tasas de actividad laboral por departamento**.
9. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Importar. Arrastre y suelte el archivo con los datos en la zona resaltada de la ventana Importar archivo **> Importar**.
10. Para publicar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Publicar > Publicar

## Gestionar los datos de referencia de las tasas de actividad laboral del proyecto

La dimensión Tasas de actividad laboral del proyecto se utiliza en Labor Activity
Planning. Véase [la función Acceso anticipado: Planificación de la actividad laboral](../labor-activity-planning.html "La versión del 20 de marzo de 2019 de las aplicaciones de planificación 2.45 de Apptio introdujo un modo alternativo para la planificación de la mano de obra del proyecto denominado Planificación de la actividad laboral. El Administrador o el Propietario del Proceso Presupuestario pueden hacer visibles en la interfaz las funciones de Planificación de la Actividad Laboral."). Esta dimensión se utiliza para fijar una tarifa laboral para actividades laborales específicas.

1. En el menú de navegación, seleccione Configuración > Datos de referencia.
2. Seleccione la pestaña Dimensiones estándar en la página Datos de referencia
3. Seleccione Tasas de actividad laboral del proyecto.
4. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Exportar.
5. En la ventana Exportar archivo, en Opciones de formato, puede cambiar el formato de los datos exportados.
6. Seleccione Exportar. Los datos de referencia se exportan como archivo.csv.
7. Abra el archivo.csv descargado. No modifique los títulos de las columnas ni la estructura de datos del fichero. Actualice los valores de la tabla de datos según sea necesario:
   - Rol - Las opciones disponibles para esta dimensión vienen dadas por los datos de referencia de Roles.
   - Proveedor - Las opciones disponibles para esta dimensión vienen dadas por los datos de referencia del proveedor.
   - Moneda - La moneda común para la imputación de la actividad laboral. Obligatorio cuando está habilitada la compatibilidad con múltiples monedas (consulte [Compatibilidad con múltiples monedas)](../support-multiple-currencies.dita "(se abre en una pestaña o una ventana nueva)"). El valor de la moneda común del Departamento debe ser el código ISO de tres letras de la moneda. Si no se introduce ningún código de moneda, se utilizará la moneda común por defecto.
   - Tasa de mano de obra - La tasa de compensación por hora por defecto.

     NOTA : Las tasas de actividad laboral de los proyectos son diferentes de la remuneración salarial de los recursos. La tasa de actividad fijada se aplica a la asignación de un recurso a una actividad de un proyecto (no a la remuneración base de ese recurso específico). Ambos valores pueden ser (y probablemente serán) diferentes.
8. Guarde el archivo en formato.csv. Ahora, seleccione **Configuración > Datos de referencia > Tasas de actividad laboral del proyecto**.
9. Seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Importar. Arrastre y suelte el archivo con los datos en la zona resaltada de la ventana Importar archivo **> Importar**.
10. Para publicar los cambios, seleccione ![más icono](../../../../../../03-media/apptio-planning/resources/images/icons/icon-options_23x20.png) > Publicar > Publicar

Consulte [Gestionar la configuración de la](score-manage.html) puntuación para obtener más información sobre la gestión de la puntuación aplicable a los proyectos.
