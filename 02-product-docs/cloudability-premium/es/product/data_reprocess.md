---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Reprocesamiento de datos"
breadcrumb:
  - "Cloudability Premium"
  - "Configuración"
source_path: "product/data_reprocess.html"
images:
  - "images/data_reprocess_1.jpg"
  - "images/data_reprocess_2.jpg"
  - "images/data_reprocess_4.jpg"
  - "images/dp10.jpg"
  - "images/dp11.jpg"
  - "images/dp2.jpg"
  - "images/dp3.jpg"
  - "images/dp4.jpg"
  - "images/dp5.jpg"
  - "images/dp6.jpg"
  - "images/dp7.jpg"
  - "images/dp8.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Reprocesamiento de datos

[Reelaboración de datos para los usuarios de « Cloudability »](data_reprocess.html#data_reprocess__Data)

[Reprocesamiento de datos para usuarios de « Cloudability : Costing & Planning»](data_reprocess.html#data_reprocess__Data2)

Reelaboración de datos para los usuarios de « Cloudability »

Por lo general, cuando se modifica la estrategia empresarial, es necesario ajustar las asignaciones de negocio, los grupos de cuentas y las etiquetas y marcas en Cloudability, lo que implica una actualización retrospectiva de los datos históricos. Aquí es donde entra en juego el reprocesamiento de datos. Si eres cliente de « Cloudability », es posible que solo necesites volver a realizar el proceso en Cloudability. Puedes realizar un reprocesamiento de datos de autoservicio para volver a procesar los datos sin necesidad de recurrir a los equipos de asistencia técnica o de éxito del cliente.

Esta función solo está disponible para los usuarios con permiso de «Admin» en Cloudability. Ve a Organizar > Reprocesar datos.

Nota:

Esta función no está activada de forma predeterminada, ya que se trata de una función opcional. Ponte en contacto con el equipo de asistencia o con tu gestor de éxito del cliente para que te activen esta función.

Sigue los pasos que se indican a continuación para iniciar el reprocesamiento

1. Ve a Organizar > Reprocesamiento de datos; por defecto, se muestra la pestaña «Estado de los trabajos ». En esta pestaña aparecerá una lista de tus solicitudes anteriores.
2. Ve a la pestaña «Nueva solicitud», introduce el nombre del trabajo (para tu identificación), la fecha de inicio, la fecha de finalización y el motivo. Selecciona el botón «Iniciar reprocesamiento» para enviar la solicitud.

   ![Captura de pantalla del reprocesamiento de datos](../../../../03-media/cloudability-premium/images/data_reprocess_1.jpg)

   Nota:
   - Se te asignan 12 unidades mensuales para las que puedes solicitar un nuevo procesamiento cada mes. Unidades mensuales : Cada mes de reprocesamiento de datos se considera una unidad mensual. Por ejemplo, si envías una solicitud de reprocesamiento correspondiente a un periodo de 12 meses, consumirás 12 unidades mensuales. Si envías dos solicitudes de reprocesamiento de tres meses cada una, consumirás seis unidades de mes.
   - En la parte superior se muestran el total de unidades mensuales y las unidades mensuales restantes.
   - El plazo máximo de revisión es de 12 meses, durante los cuales se puede solicitar un nuevo procesamiento.
   - Las unidades mensuales que utiliza tu selección actual se muestran debajo de la fecha de finalización.
   - Si la selección supera el número de unidades de mes restantes, aparecerá un mensaje de error en la parte inferior derecha.
   - Si la tarea falla en un mes concreto, tus unidades mensuales no se contabilizan para ese mes, y puedes volver a enviar la tarea para ese mes concreto.

     ![Nueva captura de pantalla del procesamiento de datos](../../../../03-media/cloudability-premium/images/data_reprocess_2.jpg)
3. Al enviar la solicitud «Iniciar reprocesamiento », aparecerá un mensaje de confirmación en la esquina inferior derecha y se le redirigirá a la pestaña «Estado del trabajo ».

   ![Captura de pantalla del estado de la solicitud de empleo](../../../../03-media/cloudability-premium/images/dp10.jpg)
4. La pestaña «Estado de los trabajos» muestra el estado de tus trabajos actuales y anteriores. También puedes desplegar el ID del trabajo y consultar los estados de cada mes. Selecciona «Actualizar» para actualizar la página de estado.

   ![Captura de pantalla que muestra el estado de un trabajo](../../../../03-media/cloudability-premium/images/data_reprocess_4.jpg)

   Nota:
   - Una vez enviada la solicitud de reprocesamiento, no se puede cancelar.
   - No pueden estar en ejecución dos solicitudes de reprocesamiento al mismo tiempo durante el mismo periodo o mes. No obstante, puedes presentar dos solicitudes de reelaboración al mismo tiempo si no hay solapamiento en el periodo o en los meses seleccionados.
   - Si solo necesitas volver a procesar los datos del mes en curso, no es necesario que envíes una solicitud. Cloudability Ya se están procesando los datos del mes en curso a diario, por lo que deberían estar disponibles en 24 horas.

Cuándo ponerse en contacto con TAM/CSM/Soporte técnico

Puedes ponerte en contacto directamente con tu TAM/CSM o con el equipo de asistencia si:

- La tarea falla más de una vez.
- Has agotado tu límite mensual de unidades mensuales y existe una necesidad empresarial urgente de volver a procesar los datos.
- ¿Tienes algún comentario o cualquier otra cuestión?

Reprocesamiento de datos para usuarios de « Cloudability : Costing & Planning»

Si utilizas «Costing & Planning», es posible que te interese importar tus datos de la nube a «Costing & Planning» desde « Cloudability » o utilizar «Cloud Data Ingestion» (CDI). Sin embargo, es posible que se produzcan cambios continuos en las estrategias empresariales de tu organización, que se añadan nuevas cuentas y aplicaciones, o que cambie la estrategia de etiquetado. Debido a estos cambios, es posible que desee volver a procesar los datos para que se apliquen de forma retroactiva las nuevas incorporaciones o modificaciones, y que desee transferir estos datos a «Costes y planificación».

Esta función permite a los usuarios con permiso de «Administrador» de Cloudability o a los usuarios de CDI iniciar el reprocesamiento de datos y supervisar el estado del proceso.

Nota:

Esta función está suspendida temporalmente para los clientes que tengan contratado el servicio Apptio Costing & Planning junto con Cloudability o CDI. Estamos trabajando activamente para mejorar la experiencia y esperamos lanzar la función mejorada a principios del año que viene. Cloudability Los clientes de Costing & Planning que ya tenían acceso seguirán conservándolo.

Sigue los pasos que se indican a continuación para iniciar el reprocesamiento

1. Ve a Organizar > Reprocesamiento de datos; por defecto, se muestra la pestaña Estado de la tarea. En esta pestaña aparecerá una lista de tus solicitudes anteriores.
2. Ve a la pestaña «Nueva solicitud» y aparecerá el paso predeterminado «Etiquetas y marcas ». Puedes seleccionar o deseleccionar las etiquetas y los campos específicos que desees exportar o transferir a «Costes y planificación».

   Nota:

   TBM StudioLos cambios realizados en esta selección solo se aplican a los datos que se exportan a «Costing & Planning» o a. Todas las dimensiones empresariales (etiquetas y labels, grupos de cuentas y asignaciones empresariales) se vuelven a procesar para « Cloudability ». No obstante, si solo desea solicitar un nuevo procesamiento sin modificar la exportación de datos a «Costing & Planning» o TBM
   Studio, continúe hasta el último paso para enviar su solicitud.

   ![Captura de pantalla de tbm studio](../../../../03-media/cloudability-premium/images/dp11.jpg)
3. Selecciona «Siguiente» para seleccionar o deseleccionar los «Grupos de cuentas ».

   ![Seleccionar captura de pantalla de grupos de cuentas](../../../../03-media/cloudability-premium/images/dp2.jpg)
4. Selecciona «Siguiente» para elegir «Asignaciones empresariales ».

   ![Captura de pantalla del reprocesamiento de datos de las correspondencias empresariales](../../../../03-media/cloudability-premium/images/dp3.jpg)
5. Selecciona «Siguiente» y revisa la selección que has realizado.

   ![Captura de pantalla de la selección de reseñas](../../../../03-media/cloudability-premium/images/dp4.jpg)
6. Selecciona «Siguiente» y aparecerá la página de envío del trabajo. Introduce el nombre del trabajo (para tu identificación), la fecha de inicio y la fecha de finalización, así como el motivo. Selecciona el botón «Iniciar reprocesamiento» para enviar la solicitud.

   ![Captura de pantalla de la solicitud de reenvío del reprocesamiento de datos](../../../../03-media/cloudability-premium/images/dp5.jpg)

   Nota:
   - Se te asignan 12 unidades mensuales para las que puedes solicitar el reprocesamiento cada mes.
   - Unidades mensuales: Cada mes de reprocesamiento de datos se considera una unidad mensual. Por ejemplo, si envías una solicitud de reprocesamiento para un periodo de 12 meses, consumirás 12 unidades mensuales. Si envías dos solicitudes de reprocesamiento de tres meses cada una, consumirás seis unidades mensuales.
   - En la parte superior se muestran el total de unidades mensuales y las unidades mensuales restantes.
   - El plazo máximo de revisión es de 12 meses, durante los cuales se puede solicitar un nuevo procesamiento.
   - No pueden estar en ejecución dos solicitudes de reprocesamiento al mismo tiempo durante el mismo periodo o mes. No obstante, puedes presentar dos solicitudes de reprocesamiento al mismo tiempo si no hay solapamiento en el periodo o en los meses seleccionados.
   - Las unidades mensuales que utiliza tu selección actual se muestran debajo de la fecha de finalización.
   - Si la selección supera el número de meses restantes, aparece el mensaje en la esquina inferior derecha.
   - Si el trabajo falla (el estado general del trabajo es «FAILED»), tendrás que volver a ejecutar el reprocesamiento para el mismo periodo.

     ![Captura de pantalla del estado del reprocesamiento de datos](../../../../03-media/cloudability-premium/images/dp6.jpg)
7. Al pulsar el botón «Iniciar reprocesamiento », aparecerá un mensaje de confirmación en la esquina inferior derecha y se le redirigirá a la pestaña «Estado del trabajo ».

   ![Captura de pantalla del inicio del reprocesamiento de Daat](../../../../03-media/cloudability-premium/images/dp7.jpg)
8. La pestaña «Estado» muestra el estado de tus trabajos actuales y anteriores. También puedes desplegar el ID del trabajo y consultar los estados de cada mes. Selecciona «Actualizar» para actualizar la página de estado.

   ![Captura de pantalla del estado de la tarea de reprocesamiento de datos](../../../../03-media/cloudability-premium/images/dp8.jpg)

   Nota:
   - Solo se pueden seleccionar etiquetas y marcas, grupos de cuentas y asignaciones empresariales.

     Las estructuras de negocio que incluyan en su definición columnas de «ID de recurso» y/o «Fecha» no serán compatibles con Costing & Planning ni con TBM Studio.
   - Todas las métricas empresariales que se configuren se transferirán automáticamente a «Costes y planificación».
   - Todos los campos predeterminados seguirán transfiriéndose a «Costes y planificación» como hasta ahora.
   - Una vez enviada la solicitud de reprocesamiento, no se puede cancelar.
   - Cuando la solicitud se haya completado (Estado = Finalizada), puedes ejecutar el conector DLC (Data Link) para extraer los datos a Costing & Planning.
   - Si solo necesitas volver a procesar los datos del mes en curso, no es necesario que envíes una solicitud. Cloudability Ya se están procesando los datos del mes en curso a diario, por lo que deberían estar disponibles en 24 horas.

Cuándo ponerse en contacto con TAM/CSM/Soporte técnico

Puedes ponerte en contacto directamente con tu TAM/CSM o con el equipo de asistencia si:

- La tarea falla más de una vez.
- Has agotado tu límite mensual de unidades mensuales y existe una necesidad empresarial urgente de volver a procesar los datos.
- ¿Tienes algún comentario o cualquier otra cuestión?
