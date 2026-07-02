---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Configurar el conector Coupa DataLink"
breadcrumb:
  - "Costing Standard"
  - "Integraciones tecnológicas"
  - "Información sobre proveedores Coupa"
  - "Información sobre proveedores Coupa Introducción"
source_path: "cost-transparency/technology-integration/configure_the_datalink_coupa_connector.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configurar el conector Coupa DataLink

◆ Aplicable a: Datalink (Classic)4.8.7 y posteriores

[Descripción general](#overview "(se abre en una pestaña o una ventana nueva)")

[Requisitos previos](#prerequisites "(se abre en una pestaña o una ventana nueva)")

[Instrucciones](#instruction_overview "(se abre en una pestaña o una ventana nueva)")

- [Tarea 1: Configurar el conector](#task_1:_configure_the_connector "(se abre en una pestaña o una ventana nueva)")
- [Tarea 2: Definir la información de la consulta](#task_2:_define_the_query_information "(se abre en una pestaña o una ventana nueva)")
- [Tarea 3: Definir las propiedades](#_task_3:_define_the_properties "(se abre en una pestaña o una ventana nueva)")
- [Tarea 4: Configurar el conector Coupa Apptio Configuración de destino](#task_4:_configure_the_coupa_connector__apptio_destination_settings "(se abre en una pestaña o una ventana nueva)")
- [Tarea 5: Configurar las notificaciones por correo electrónico del conector](#task_5:_configure_connector__email_notifications "(se abre en una pestaña o una ventana nueva)")
- [Tarea 6: Probar el conector](#task_6:_test_the_connector_ "(se abre en una pestaña o una ventana nueva)")
- [Tarea 7: Guardar la configuración del conector](#task_7:_save_the_connector__configuration "(se abre en una pestaña o una ventana nueva)")
- [Tarea 8: Ejecutar o cancelar la ejecución del conector](#task_8:_execute_or_cancel_the_connector__run "(se abre en una pestaña o una ventana nueva)")
- [Tarea 9: Ver el historial de ejecución](#task_9:_view_execution_history "(se abre en una pestaña o una ventana nueva)")
- [Tarea 10: Validar la salida en TBM Studio](#task_10:_validate_output_in_tbm_studio "(se abre en una pestaña o una ventana nueva)")

[Solucionar problemas con el conector](#troubleshoot_issues_with_the_connector_ "(se abre en una pestaña o una ventana nueva)")

[Apéndice](#appendix "(se abre en una pestaña o una ventana nueva)")

- [Mejores prácticas del modo de recuperación](#retrieval_mode_best_practices "(se abre en una pestaña o una ventana nueva)")
- [Recomendación sobre opciones de recuperación](#recommendation_for_retrieval_options "(se abre en una pestaña o una ventana nueva)")
- [Propiedades JSON y objetos Coupa](#json_propteries_and_coupa_objects "(se abre en una pestaña o una ventana nueva)")
- [Advertencia sobre las columnas del segmento de cuenta en las tablas](#warning_about_account_segment_columns_in_tables "(se abre en una pestaña o una ventana nueva)")

**Descripción general**

Utilice el conector Coupa de Datalink (Classic) para exportar datos de Coupa y, a continuación, impórtelos a su instancia de Apptio para generar informes en ApptioVendor Insights .

**Instrucciones**

**Tarea 1: Configurar el conector**

1. Abra el agente Datalink (Classic) y haga clic en Nuevo conector.
2. Haga clic en el conector Coupa.
3. Introduzca un nombre de conector.   
      
    **Ejemplo** : Coupa – Datos iniciales – Línea de pedido
4. Opcionalmente, seleccione Añadir este conector a un grupo de conectores.   
      
    **Nombre de ejemplo** : Coupa – Datos   
     
    iniciales Para obtener información sobre los grupos de conectores, consulte [Agrupar varios conectores](../../datalink-classic/datalink/group-connectors.html "(se abre en una pestaña o una ventana nueva)").

**Tarea 2: Definir la información de la consulta**

Para obtener información sobre cómo definir la consulta y, en concreto, sobre la autenticación, consulte [Definir la información de la consulta](../../datalink-classic/datalink/connectorguides/c-coupa.html).

**Tarea 3: Definir las propiedades**

1. Seleccione un modo de recuperación.   
    Si selecciona Datos iniciales (Datos a partir de), proporcione información adicional sobre el Mes de inicio y el Año de inicio.

   **Ejemplos**

   - Modo de recuperación: Datos iniciales (Datos a partir de)
   - Mes de inicio: enero
   - Año de inicio: 2019

   **Opciones del modo de recuperación**

   Los pasos de configuración varían según el modo de recuperación:
   - **Datos iniciales (Todos los datos)** - Recuperar todos los datos hasta la fecha de ejecución del conector. Esta transformación de destino está configurada para sobrescribir los datos anteriores.
   - **Datos iniciales (datos a partir de)** - Recuperar datos a partir de un mes y año determinados hasta la fecha de ejecución del conector (>= [mes de inicio] / 01 / [año de inicio]). Esta transformación de destino está configurada para sobrescribir los datos anteriores.
   - **Datos Delta (desde el comienzo del mes pasado)** : recupera los datos desde el comienzo del mes anterior hasta la fecha de ejecución del conector (>=[mes del mes pasado] / 01 / [año del mes pasado]). Esta transformación de destino está configurada para añadir los nuevos datos a los datos anteriores.   
        
      Consulte [el Apéndice: Prácticas recomendadas para el modo de recuperación](#retrieval_mode_best_practices "(se abre en una pestaña o una ventana nueva)") para obtener más información.
2. Seleccione un objeto Coupa. Puede acceder e importar los siguientes tipos de datos de la API de Coupa y criterios de filtrado (además del rango de datos del modo de recuperación ) a su instancia de Apptio :

   | Objeto Coupa | Filtro de estado predeterminado |
   | --- | --- |
   | Proveedores | activo, inactivo |
   | Contratos | publicado, inactivo |
   | Órdenes de compra | Todos los estados |
   | Líneas de orden de compra | Todos los estados |
   | Cuentas de líneas de órdenes de compra | Todos los estados |
   | Facturas | aprobado, anulado |
   | Líneas de factura | aprobado, anulado |
   | Cuentas de líneas de factura | aprobado, anulado |

   Nota: Las líneas de factura y las cuentas de línea de factura se filtran según el estado de su factura principal.
3. Seleccionar un filtro de estado

**Tarea 4: Configurar el conector Coupa Apptio Configuración de destino**

Conecta tu conector a tu destino de Apptio. Desde el conector, haga clic en « Apptio **» (Destino)** en el menú de la izquierda para acceder a esta configuración. Si el conector forma parte de un grupo de conectores, los  Apptio  **Destino**   ajustes para  Apptio Instancia  ,  Proyecto  Dominio  , y  Sucursal  se desactivan y, en su lugar, se heredan de los ajustes del grupo.

| Campo | Descripción | Ejemplo |
| --- | --- | --- |
| Apptio **Versión** | Seleccione R12 con puerta delantera. | R12 con puerta principal |
| Apptio **Instancia** | Seleccione de la lista de aplicaciones válidas de Administración de Acceso. | Costing Standard (https://acme.apptio.com) |
| **Dominio** | Introduzca el nombre de dominio de la instancia de destino de Apptio. | acme.com |
| Proyecto | Introduzca el nombre del proyecto de destino. | Costing Standard |
| **Tabla** | Introduzca el nombre de la tabla de destino.   Este es solo el nombre de la tabla. No es la información del « URL » ni de la ruta. Si la tabla no existe, se creará. | Coupa Raw – Inicial – Línea de pedido |
| **Sistema fuente** | Introduzca **Coupa** como nombre del sistema de origen de los datos. | Coupa |
| **Período de tiempo** | Selecciona **Hora específica**. | **Hora específica** |
| **Período específico** | Seleccione el mes específico, el tipo de calendario y el año específico.     Se recomienda utilizar uno de los modos de recuperación **de datos iniciales** de la sección **Definir las propiedades** para rellenar la instancia de Apptio con datos históricos. Estos datos se colocan en el período de tiempo especificado en la configuración de Tiempo específico. | Deseleccionar |
| Validación | Seleccione esta casilla para validar los datos cargados utilizando el conjunto de datos existente. | Seleccionar |

Si las columnas no coinciden, los datos cargados se mantendrán en un área de preparación, pero no se añadirán al conjunto de datos. Se envía un correo electrónico a los usuarios administradores de Datalink (Classic) para notificarles que la carga no ha superado la validación. En este caso, el administrador puede ir a la pestaña TBM Studio Datos y aprobar manualmente la carga. Es una buena práctica validar los datos antes de subirlos.

**Opciones avanzadas**

| Campo | Descripción | Ejemplo |
| --- | --- | --- |
| Codificación de datos | Seleccione la codificación de caracteres que se utilizará con las consultas.     Esta opción solo está disponible cuando la instancia de destino de Apptio es R12. | **Detección automática** |
| Categoría | Introduzca una categoría para la tabla.     Esta opción solo está disponible cuando la instancia de destino de Apptio es R12. | z\_Coupa Raw |
| Sucursal | Si utiliza la función de ramificación en TBM Studio R12, introduzca un nombre de rama para cargar los datos en esa rama.     Para obtener más información, consulte [Proyectos de ramas](../../studio/admin/bp-branching-projects.htm "(se abre en una pestaña o una ventana nueva)").  - Esta función requiere R12.5 o una versión posterior. Si se utiliza una versión anterior de R12, la configuración se ignora y los datos se cargan en el tronco. - Si el nombre de la rama está mal escrito o ya no existe (por ejemplo, la rama está cerrada y se completa una compilación posterior), se informa de un error. |  |
| Transformación | 1. Seleccione un valor adecuado para el modo de recuperación que haya seleccionado:  - Datos iniciales (todos los datos) - Configure la opción Sobrescribir los datos anteriores. - Datos iniciales (datos a partir de) - Configure Sobrescribir los datos anteriores. - Datos Delta (desde principios del mes pasado) - Configure Anexar los nuevos datos a los datos anteriores. | **Sobrescribir** |

  

**Tarea 5: Configurar las notificaciones por correo electrónico del conector**

Después de configurar las notificaciones por correo electrónico para su agente de Datalink (Classic), puede configurar las notificaciones por correo electrónico para cada conector. Si no ha configurado los ajustes SMTP, consulte [Configurar las notificaciones por correo electrónico del agente](../../datalink-classic/datalink/config-datalink-agents.html#agentemail "(se abre en una pestaña o una ventana nueva)"). Puede especificar que se envíe una notificación por correo electrónico cuando un conector tenga éxito o falle.

1. Haga clic en Notificar o Notificar y archivar en el menú de la izquierda para acceder a la configuración del correo electrónico. De lo contrario, desplácese hacia abajo hasta la sección Notificar o Notificar y archivar.
2. Seleccione sus preferencias de correo electrónico.
3. En el cuadro Para, introduzca una o varias direcciones de correo electrónico, separadas por una coma o un punto y coma.
4. Introduzca un asunto en el cuadro Asunto.

**Tarea 6: Probar el conector**

Haga clic en Probar en la esquina superior derecha para probar el conector.

Si hay un error, se marcará y podrás saltar directamente a esa parte de la definición del conector. Al hacer clic en Probar se guardan los cambios realizados en el conector.

**Tarea 7: Guardar la configuración del conector**

Haga clic en Guardar en la esquina superior derecha para guardar el conector.

Si falta información en la configuración, se le indicará.

**Tarea 8: Ejecutar o cancelar la ejecución del conector**

- Para ejecutar el conector, abra el agente de Datalink (Classic), haga clic en Acciones junto al conector y, a continuación, haga clic en Ejecutar ahora.
- Para cancelar un conector que se está ejecutando actualmente, abra el Agente de Datalink (Classic), haga clic en Acciones junto al conector y, a continuación, haga clic en Cancelar ejecución.

**Tarea 9: Ver el historial de ejecución**

Ver un informe de los resultados de la ejecución que incluye las fuentes, el destino, el período objetivo, la hora de inicio y finalización de la ejecución, una explicación de los resultados y el número de bytes cargados para cada ejecución del conector.

1. Abra el Agente de Datalink (Classic), haga clic en Acciones junto al conector y, a continuación, haga clic en Ver historial de ejecución.   
      
    **NOTA** : De forma predeterminada, Historial de ejecución muestra la información de ejecución de los últimos tres meses.
2. (Opcional) Cambie los valores de los campos Desde y Hasta y, a continuación, haga clic en Obtener registros de ejecución para ver hasta 12 meses de historial.

**Tarea 10: Validar la salida en TBM Studio**

Asegúrese de que la tabla con el nombre especificado se haya creado correctamente.

**Solucionar problemas con el conector**

Si el conector falla durante la ejecución, prueba a desmarcar la casilla Validación. Ejecute el conector y, a continuación, vuelva a marcar la casilla de verificación Validación para futuras ejecuciones.

**NOTA** : Para Datalink (Classic) 4.8.8 (compilación new-master-12000 ) y posteriores, el no `execution ID`  está presente en los archivos de registro.

**Apéndice**

**Mejores prácticas del modo de recuperación**

Al configurar por primera vez la integración de Coupa con Apptio, se recomienda utilizar un modo de recuperación de datos iniciales para rellenar Apptio con los datos históricos necesarios. Los datos iniciales se rellenarán en el periodo de tiempo especificado mediante las opciones de Tiempo específico en la configuración Periodo de tiempo del destino Apptio. Para obtener más información, consulte [Configurar los ajustes de destino de Apptio](#task_4:_configure_the_coupa_connector__apptio_destination_settings "(se abre en una pestaña o una ventana nueva)").

La opción Delta Data está diseñada para ser el modo de recuperación para las ejecuciones programadas del conector. Esta opción sirve para recuperar registros que se han actualizado en Coupa y, a continuación, añadirlos a la misma tabla en el mismo periodo de tiempo. En este caso, puede utilizar la TBM Studio función Eliminar duplicados para asegurarse de que solo se utilice la última versión de un registro determinado en Apptio.

**NOTA** : Coupa recomienda utilizar la opción Datos iniciales (establecer fecha de inicio) para las cargas de datos iniciales, con el fin de evitar la transferencia de volúmenes de datos innecesarios. Aunque los datos iniciales (todos los datos) pueden ser adecuados para los proveedores y los contratos.

Valores esperados

La siguiente tabla muestra los valores esperados al extraer datos de Coupa:

| Objeto Coupa | Extracción inicial: filtro de datos | Filtro de estado predeterminado | Periodo inicial de extracción - destino | Tracción inicial:   dónde colocar los datos (transformación) | Delta pull - filtro de datos | Delta pull - período de tiempo de destino | Delta pull: dónde colocar los datos (transformación) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Proveedor | Datos iniciales (todos los datos) | activo, inactivo | Primer período del año en curso | Sobrescribir | Datos delta (desde principios del mes pasado) | Período anterior | Añadir |
| Contrato | Datos iniciales (todos los datos) | publicado, inactivo | Primer período del año en curso | Sobrescribir | Datos delta (desde principios del mes pasado) | Período anterior | Añadir |
| PO, línea PO, cuenta de línea PO | Datos iniciales (todos los datos) | Todos los estados | Primer período del año en curso | Sobrescribir | Datos delta (desde principios del mes pasado) | Período anterior | Añadir |
| Factura, línea de factura, cuenta de línea de factura | Datos iniciales (datos a partir de) | aprobado, anulado | Período anterior | Sobrescribir | Datos delta (desde principios del mes pasado) | Período anterior | Añadir |

**Recomendación sobre opciones de recuperación**

Se recomienda utilizar uno de los modos de recuperación de datos iniciales para rellenar la instancia de Apptio con datos históricos. Estos datos se colocan en el periodo de tiempo especificado en la configuración de Tiempo específico. Para obtener más información, consulte [Definir las propiedades](#_task_3:_define_the_properties "(se abre en una pestaña o una ventana nueva)").

**Ejemplo** : Hora específica

**Ejemplo** : Período específico: Jan:FY2019

**Propiedades JSON y objetos Coupa**

Las propiedades JSON se extraerán en relación con el objeto Coupa que se está consultando. Para los objetos Cuenta de línea de orden de compra y Cuenta de línea de factura, el objeto raíz de cada registro será asignación de cuenta si la cuenta dada es miembro de una asignación de cuenta. De lo contrario, el objeto raíz será la cuenta.

**Ejemplo** : El campo adicional «Some Field Name: some.path » para un objeto «Invoice Line Account» extraería su valor de `invoice.invoice-lines.account-allocations` «para cuentas que son miembros de una asignación de cuentas» y `invoice.invoice-lines.account` «para cuentas que no son miembros de una asignación de cuentas».

**Advertencia sobre las columnas del segmento de cuenta en las tablas**

En Datalink (Classic) 4.8.15 y versiones posteriores, las columnas de segmentos de cuenta en las tablas cargadas por el conector Coupa Datalink (Classic) para cuentas de líneas de órdenes de compra y cuentas de líneas de facturas siguen las siguientes convenciones de nomenclatura nuevas:

- El segmento de cuenta 01-09 permanece igual (un 0 precede a los números 1-9)
- El segmento de cuenta 010 y superiores ya no requieren un 0 antes del número.   
    
   **Ejemplo** : la cuenta 010 ahora es la cuenta 10, y la cuenta 011 ahora es la cuenta 11

Al añadir datos a una tabla que utilizaba la convención de nomenclatura anterior (Cuenta 010 en lugar de Cuenta 10), se añaden a la tabla las nuevas columnas de segmentos de cuenta renombradas. Los registros de tabla que existían antes de Datalink (Classic) 4.8.15 continúan almacenando datos de segmentos de cuenta utilizando la convención de nomenclatura anterior.
