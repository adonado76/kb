---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Notas de la versión 2025"
breadcrumb:
  - "TBM Studio"
  - "Notas del release"
source_path: "studio/release_notes/whats-new-2025.html"
images:
  - "resources/images/acm_images/ce-lcm.jpg"
  - "resources/images/acm_images/ce-model-view.jpg"
  - "resources/images/acm_images/ce-vcm.jpg"
  - "resources/images/be/bcm.jpg"
  - "resources/images/be/be-rn-1.jpg"
  - "resources/images/be/be-rn-2.jpg"
  - "resources/images/be/rm-1.jpg"
  - "resources/images/be/sm-2.jpg"
  - "resources/images/ct_images/3-steps.jpg"
  - "resources/images/ct_images/cg-200.jpg"
  - "resources/images/ct_images/cg-300.jpg"
  - "resources/images/ct_images/cg-sum.jpg"
  - "resources/images/ct_images/release_notes/pct-1.jpg"
  - "resources/images/ct_images/release_notes/pct-2.jpg"
  - "resources/images/ct_images/release_notes/pct-3.jpg"
  - "resources/images/studio_images/r-notes/121113-auto.png"
  - "resources/images/studio_images/r-notes/121113-bu.png"
  - "resources/images/studio_images/r-notes/121113-bu1.png"
  - "resources/images/studio_images/r-notes/121113-bu2.png"
  - "resources/images/studio_images/r-notes/121113-usage.png"
  - "resources/images/studio_images/r-notes/121113-usage1.png"
  - "resources/images/studio_images/r-notes/121113-usage2.png"
  - "resources/images/studio_images/r-notes/dupsub.jpg"
  - "resources/images/studio_images/r-notes/ess-1.jpg"
  - "resources/images/studio_images/r-notes/ess-2.jpg"
  - "resources/images/studio_images/r-notes/ess-3.jpg"
  - "resources/images/studio_images/r-notes/et-edit.jpg"
  - "resources/images/studio_images/r-notes/fv.jpg"
  - "resources/images/studio_images/r-notes/sc-pk.jpg"
  - "resources/images/studio_images/r-notes/sc-pk1.jpg"
  - "resources/images/studio_images/r-notes/scroll.jpg"
  - "resources/images/studio_images/r-notes/send-nw.jpg"
  - "resources/images/studio_images/r-notes/send-nw1.jpg"
  - "resources/images/studio_images/r-notes/sh-1.jpg"
  - "resources/images/studio_images/r-notes/sh-2.jpg"
  - "resources/images/studio_images/r-notes/sh-3.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Notas de la versión 2025

## Servidor 12.11.18.1 - 16 de diciembre de 2025

Se ha corregido el error del servidor al crear tablas/informes con caracteres especiales o japoneses en los nombres

## Cliente 2.18, 21 de noviembre de 2025

Todas las nuevas funciones requieren una actualización a la versión del servidor 12.11.18. Consulte las actualizaciones del servidor.

## Servidor 12.11.18 - 21 de noviembre de 2025

- El nuevo IBM Apptio Report Studio se encuentra actualmente en fase de vista previa privada y solo está disponible en entornos de vista previa temporales para un grupo selecto de clientes. A continuación, se iniciará una fase de vista previa pública (beta), que estará abierta a todos los clientes que decidan participar, y luego se pasará a la disponibilidad general (GA).
  - El nuevo estudio de informes ahora cumple con los estándares de accesibilidad de la Sección 508, lo que garantiza una experiencia inclusiva para todos los usuarios.
- Se ha introducido [la función Auto-pause Calc](../admin/build-anomaly-detection.html#build-ano-det__autopause) (vista previa pública/beta) para la detección de anomalías de compilación.
- Norma de cálculo de costes (plantillas v120 )
  - IBM Apptio El TCO del producto es una solución específica diseñada para proporcionar una visión clara y justificable de los costes y la composición del producto. Consulte [la descripción general](/docs/SSI71A/cost-transparency/configuration/product-tco-overview.html) para obtener más información information.To. Para obtener más información, vea [el vídeo](https://youtu.be/7LD-1gRE6nQ?si=0lgkUTplvW1lS9Jy "(se abre en una pestaña o una ventana nueva)").
  - Nuevos informes del panel ejecutivo en IBM Apptio Costing que proporciona información financiera y operativa de alto nivel específica para cada función, adaptada a los directores de informática, directores de tecnología y directores financieros (vista previa pública/beta).
  - Mejora [del TCO del mainframe](/docs/SSI71A/cost-transparency/configuration/mainframe-tco-overview.html#aitco__benchmarking) : se han añadido comparaciones de costes entre pares basadas en referencias del sector.

## Servidor 12.11.17.1 - 7 de noviembre de 2025

- Actualización trimestral de Java.
- Se ha solucionado el problema de creación de versiones durante la carga de descargas.

## Servidor 12.11.17 - 26 de septiembre de 2025

- Presentamos el nuevo IBM Apptio Report Studio (vista previa).
  - El acceso está limitado a los usuarios que se han inscrito en la vista previa. La inscripción está cerrada hasta nuevo aviso.
- La función Recomendaciones del flujo de trabajo le permite desactivar [los informes que no se utilizan (Beta)](../troubleshooting/unused-repors.html).
- En Calc Explorer, se han introducido [métricas secundarias adicionales](../admin/calc-explorer.html#calc-explorer__additional-drills) para los ejercicios: total de filas de la matriz, total de columnas de la matriz, ratio de asignación de filas y tipo de matriz
- Norma de cálculo de costes (plantillas v120 )
  - Mainframe TCO es una solución diseñada específicamente para ofrecer una visión clara y justificable de los costes del mainframe, lo que permite una asignación precisa de los costes, un seguimiento exhaustivo de la utilización y una toma de decisiones basada en datos. Consulte [la Descripción general](/docs/SSI71A/cost-transparency/configuration/mainframe-tco-overview.html) y [la Guía de configuración](/docs/SSI71A/cost-transparency/configuration/mainframe-config-guide.html) para obtener más información. Para obtener más información, vea [el vídeo](https://www.youtube.com/watch?v=XyLAwalou4M "(se abre en una pestaña o una ventana nueva)") y [el blog](https://www.apptio.com/blog/introducing-ibm-apptio-mainframe-tco-complete-visibility-into-mainframe-costs-and-usage/ "(se abre en una pestaña o una ventana nueva)").
  - Cost Take-Out Analytics & Insights son informes consolidados listos para usar que simplifican la optimización de costes al reunir información sobre proveedores, aplicaciones y mano de obra, lo que permite a las organizaciones identificar rápidamente oportunidades de ahorro y tomar decisiones más rápidas basadas en datos. Consulte [la Descripción general](/docs/SSI71A/cost-transparency/configuration/cost-take-out-reports.html) y [la Guía de configuración](/docs/SSI71A/cost-transparency/configuration/cost-takeout-config-guide.html) para obtener más información. Para obtener más información, vea [el vídeo](https://youtu.be/ImnfrjRxEVI "(se abre en una pestaña o una ventana nueva)").
  - Se han añadido archivos de referencia para la taxonomía TBM v5
- Mejora del rendimiento de Maximo Solution (plantilla v200 ).

**Corregido en esta versión**

- Se han corregido vulnerabilidades de seguridad

## Cliente 2.16, 15 de agosto de 2025

- Evitar el error de tabla editable cuando solo se registra el esquema.
- Se ha introducido la función [Calc Management Scheduler](../admin/cacl-mgmt-scheduler.html "Aplicable a: 2.16 y versiones posteriores. Esta función automatizará los cálculos de puesta en escena a nivel de proyecto y de rama.") para automatizar los cálculos de preparación a nivel de proyecto y de rama.

## Servidor 12.11.16 - 15 de agosto de 2025

- La detección [de anomalías en la construcción](../admin/build-anomaly-detection.html "La función de detección de anomalías está diseñada para ayudarle a identificar cambios inusuales en el esfuerzo de cálculo, lo que puede ayudarle a optimizar sus informes y transformaciones. Esta función se basa en los datos recopilados por Calc Explorer, que proporciona información detallada sobre el esfuerzo de cálculo para cada compilación.") ya está disponible.
- [La](../reports/tables/enhanced-excel-parsing.html) función de análisis mejorado de Excel se habilita automáticamente para los nuevos clientes, mientras que los clientes existentes pueden adoptarla mediante un [proceso de migración manual.](../reports/tables/enhanced-excel-parsing.html)
- Norma de cálculo de costes (plantillas v120 )
  - [TCO y uso de la IA](../../cost-transparency/configuration/ai-tco-overview.html "La inteligencia artificial (IA) es una prioridad clave para muchas organizaciones, y los directores de informática (CIO) tienen cada vez más la tarea de liderar las estrategias de IA en toda la organización. A medida que se acelera el gasto en IA, también lo hace la complejidad. Los directores de informática admiten que la gestión de los costes limita su capacidad para aprovechar todo el potencial de la inteligencia artificial. Para que las organizaciones adopten, amplíen y gestionen iniciativas de IA de forma sostenible y aprovechen todo su valor, necesitan una visibilidad clara de los costes, el uso y la adopción de la IA.") : se ha añadido una nueva pestaña de definición.
  - [Impacto del TCO de la TI híbrida](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=collection-hybrid-it-tco-impact-admin "(se abre en una pestaña o una ventana nueva)") : nueva ventana emergente con tendencias detalladas en el informe de análisis y métrica de coste medio por aplicación añadida al informe resumido
  - TCO del mainframe: se ha añadido un informe detallado y un informe de facturación.
  - Se ha añadido la etiqueta «Aplicación» a los informes [de TCO de la nube pública](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=collection-public-cloud-tcoreports "(se abre en una pestaña o una ventana nueva)").
  - Se ha añadido el nuevo campo «Código» en las tablas de datos maestros de integración de planificación.
- Mejoras en los elementos esenciales del cálculo de costes (plantillas v200 )
  - Se han añadido nuevos campos en el informe «[Labor Missing Mapping](https://www.ibm.com/docs/en/apptio-commercial/costing-essentials/saas?topic=workbench-labor-mapping "(se abre en una pestaña o una ventana nueva)") Workbench Report» (Informe de trabajo de mapeo faltante) y en el informe «[Vendor Missing Mapping](https://www.ibm.com/docs/en/apptio-commercial/costing-essentials/saas?topic=workbench-vendor-mapping#VendorMapping__MissingMappings__title__1 "(se abre en una pestaña o una ventana nueva)") Workbench Report» (Informe de proveedor de mapeo faltante).
  - Se han añadido nuevos campos en el informe del entorno de trabajo [de asignación de organizaciones](https://www.ibm.com/docs/en/apptio-commercial/costing-essentials/saas?topic=workbench-organization-mapping "(se abre en una pestaña o una ventana nueva)").
  - Se ha actualizado la fórmula de recuento de filas para TS Infrastructure y TS Platform.
  - Se ha añadido la etiqueta «Aplicación» a los informes [de TCO de la nube pública](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=collection-public-cloud-tcoreports "(se abre en una pestaña o una ventana nueva)").
  - Se ha añadido el nuevo campo «Código» en las tablas de datos maestros de integración de planificación.
  - Se han añadido métricas de depreciación al modelo de servicios tecnológicos.

**Corregido en esta versión**

- Se ha solucionado el problema por el que los KPI no se mostraban en japonés.

## Servidor 12.11.15.1 - 25 de julio de 2025

- Se ha solucionado el problema de rendimiento configurando JVM para utilizar la configuración predeterminada de GC ( G1 ).

## Servidor 12.11.15 - 4 de julio de 2025

- Presentación de IBM Maximo **Maintenance Cost Insights** (MCI), con tecnología de IBM Apptio Costing ( v200 ). Esta solución proporciona a los clientes de Maximo una integración bidireccional lista para usar entre IBM Maximo y IBM Apptio Costing. Proporciona a los responsables de mantenimiento de Maximo visibilidad sobre el coste total de mantenimiento en todas las órdenes de trabajo, activos y ubicaciones. Al identificar los principales factores que influyen en los costes, como la mano de obra, los materiales, las herramientas y los servicios, la solución potencia la responsabilidad financiera y mejora la planificación en todas las operaciones de mantenimiento. Consulte [la descripción general](https://www.ibm.com/docs/en/masv-and-l/maximo-manage/cd?topic=applications-integrating-maximo-maintenance-cost-insights-apptio "(se abre en una pestaña o una ventana nueva)") para obtener más información.
- Norma de cálculo de costes (plantillas v120 )
  - Mejoras en el informe sobre el coste total de propiedad y el uso de la IA; solución añadida a los proyectos de referencia.
  - Mejoras en el coste total de propiedad (TCO) de los mainframes (BETA)
  - Localización al japonés para el impacto del TCO de la TI híbrida y el TCO y el uso de la IA.
- Mejoras en Costing Essentials ( v200 ): se ha eliminado la opción «Global» de [todos los segmentadores](https://www.ibm.com/docs/en/apptio-commercial/costing-essentials/saas?topic=reports-labor-review "(se abre en una pestaña o una ventana nueva)") para aprovechar mejor las vistas guardadas, se han eliminado algunos [informes](https://www.ibm.com/docs/en/apptio-commercial/costing-essentials/saas?topic=started-end-user-devices-reports "(se abre en una pestaña o una ventana nueva)") avanzados sobre dispositivos de usuarios finales y se ha añadido la estrategia de asignación de personal a tiempo completo (FTE).
- Calc Explorer ahora se carga al desplazarse, lo que mejora el tiempo de carga inicial.
- Los paneles de control se han actualizado con los últimos datos de referencia.

**Corregido en esta versión**

- Se ha corregido el error en Calc Explorer al realizar búsquedas en Mostrar compilaciones de desarrollo.
- Se ha solucionado el problema por el que el diagrama de Sankey en Calc Explorer se interrumpía al realizar búsquedas o pasar páginas antes de profundizar.
- Se han corregido vulnerabilidades de seguridad.

## Cliente 2.15, 4 de julio de 2025

- Mejoras en Costing Essentials ( v200 ): se ha eliminado la opción «Global» de [todos los segmentadores](https://www.ibm.com/docs/en/apptio-commercial/costing-essentials/saas?topic=reports-labor-review "(se abre en una pestaña o una ventana nueva)") para aprovechar mejor las vistas guardadas.

## Servidor 12.11.14.1 - 20 de junio de 2025

- Se ha solucionado el problema por el que no se activaban las tareas recurrentes programadas.

## Servidor 12.11.14 - 30 de mayo de 2025

**Nuevas funciones**

- Presentación **de** la solución AI TCO & Usage de IBMApptio, que proporciona a los directores de informática, responsables de negocios y soluciones, y equipos de inteligencia artificial y ciencia de datos una visibilidad integral del coste total de propiedad y el uso de la inteligencia artificial. Al desbloquear información valiosa en modelos y soluciones de IA, impulsa decisiones más inteligentes para las inversiones en IA, permite una ampliación responsable y sienta las bases para conversaciones sobre el valor de la IA. Consulte [la Descripción general](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=tco-ai-overview "(se abre en una pestaña o una ventana nueva)"), [la Guía de configuración](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=tco-ai-configuration-guide "(se abre en una pestaña o una ventana nueva)") y [la Recopilación de informes](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=collection-ai-report "(se abre en una pestaña o una ventana nueva)") para obtener más información.
- *Costing Standard (v120)*
  - Se han introducido [informes generales de modelos](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=collection-model-views-overview "(se abre en una pestaña o una ventana nueva)") para visualizar los flujos de costes, lo que proporciona información detallada y mejora la transparencia.
  - Se han añadido nuevos informes [de Hybrid IT Impact Admin](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=collection-hybrid-it-tco-impact-admin "(se abre en una pestaña o una ventana nueva)") con el botón «Copiar tabla» para simplificar la configuración y eliminar la necesidad de conectores de enlace de datos de Apptio a Apptio.
  - Informe [TCO Public Cloud](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=cloud-public-overview "(se abre en una pestaña o una ventana nueva)") actualizado con pestaña Definición, gráficos de doble eje para tarifas unitarias, tabla de atributos redimensionada y orden de selección de columnas revisado que sigue una jerarquía taxonómica.
- *Proyecto de uso* : se han añadido nuevas fórmulas para el tipo de usuario, la función y la persona en la versión de marzo de 2025.
- *Flujos de trabajo de recomendaciones*
  - Se ha introducido un nuevo flujo de trabajo [de métricas no utilizadas](../troubleshooting/studio-unused-metrics.html "Esta función proporciona recomendaciones automáticas sobre métricas calculadas no utilizadas, lo que ofrece visibilidad de las métricas creadas por los usuarios que no se utilizan en otras métricas o informes. El sistema registrará automáticamente los cambios y marcará los problemas como resueltos.") (Beta) para optimizar el sistema.
  - Se introdujo el flujo de trabajo [de ponderaciones positivas y negativas.](../troubleshooting/positive-and-negative-recom.html "Esta función ayuda a solucionar problemas de peso al detectar y advertir sobre pesos positivos y negativos mixtos, para que puedas corregirlos y obtener resultados precisos.")
- *Detección de anomalías en la compilación (Beta)* : se ha introducido una nueva función para detectar [anomalías en la compilación](../admin/build-anomaly-detection.html "La función de detección de anomalías está diseñada para ayudarle a identificar cambios inusuales en el esfuerzo de cálculo, lo que puede ayudarle a optimizar sus informes y transformaciones. Esta función se basa en los datos recopilados por Calc Explorer, que proporciona información detallada sobre el esfuerzo de cálculo para cada compilación.") con el fin de mejorar los tiempos de cálculo y el rendimiento.

**Mejoras**

- [Public Cloud TCO](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=cloud-public-overview "(se abre en una pestaña o una ventana nueva)") El informe para Costing Essentials se ha mejorado con la pestaña Definición, gráficos de doble eje para las tasas unitarias, una tabla de atributos redimensionada y un orden revisado del selector de columnas que sigue una jerarquía taxonómica.
- Mejoras [en el informe de descripción general del modelo](https://www.ibm.com/docs/en/apptio-commercial/costing-essentials/saas?topic=reports-model-views-overview "(se abre en una pestaña o una ventana nueva)") en Costing Essentials

**Arreglos**

- Se ha solucionado el problema con la función «Año anterior» en «Métricas calculadas» para Costing Essentials
- Correcciones de vulnerabilidades y seguridad

## Cliente 2.14, 30 de mayo de 2025

**Nuevas funciones**

- Se han añadido funciones para mejorar la experiencia del usuario [en la suscripción por correo electrónico](../reports/email-subscription.html), incluyendo la activación/desactivación de suscripciones, la función de búsqueda y el aumento del límite de caracteres en el cuerpo del correo electrónico.
- Ahora se pueden filtrar (buscar) las columnas Conjunto de cambios y Cambios de Calc Explorer para cualquier elemento que aparezca en los cuadros de diálogo que se abren.
- Tablas editables: se ha añadido la posibilidad de descargar, editar [y](../data_studio/create-table-from-et.html) cargar datos de tablas transformadas para un periodo específico con el fin de corregir errores anteriores.

**Arreglos**

- Se ha corregido el error que se producía en los informes de tablas editables tras añadir o eliminar un valor de columna y guardar los cambios.
- Se ha solucionado el problema por el que el script “cellEdit“ ignoraba el error de validación de las celdas existentes.
- Se ha corregido la validación del valor único en el script de carga de archivos/botón

## Servidor 12.11.13.1 - 25 de abril de 2025

- Actualización trimestral de Java.
- Se ha solucionado el problema con el grupo de conexiones de MySQL que provocaba el agotamiento de las sentencias preparadas.

## Servidor 12.11.13 - 11 de abril de 2025

**Costing Standard (v120)**

Esta versión incluye las siguientes mejoras clave para optimizar la experiencia del usuario y la funcionalidad.

- Proyecto de uso: informes basados en roles según el perfil de Frontdoor.
- IBM Apptio La integración de Turbonomic ya está disponible de forma general. Para obtener más información, vea este [vídeo](https://youtu.be/-FY7WfDBK1g?si=20-TTKhVDBaPRo0v "(se abre en una pestaña o una ventana nueva)").
- Soporte en japonés para Public Cloud TCO.
- Public Cloud TCO añadido al proyecto Costing
  Standard de referencia

**Costing Essentials(v200)**

Esta versión incluye dos mejoras clave:

- Soporte en japonés para Public Cloud TCO.
- Public Cloud TCO añadido al proyecto Costing
  Essentials de referencia

**Proyecto de uso: informes basados en roles sobre la personalidad de Frontdoor.**

Esta versión introduce informes basados en roles sobre los perfiles de Frontdoor, lo que proporciona a los administradores una mayor visibilidad sobre la participación y la adopción de los usuarios. El panel de uso de Apptio ahora permite a los administradores supervisar la interacción con los informes, la actividad de los usuarios y el rendimiento de los informes, segmentados por roles de usuario y perfiles definidos en Frontdoor. Esta función permite a los administradores saber quién está interactuando con Apptio e identificar las áreas en las que centrar los esfuerzos de adopción, impulsando una habilitación específica.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/121113-usage.png)

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/121113-usage2.png)

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/121113-usage1.png)

**¡Automático!Configuración ALL\_ROWS habilitada de forma predeterminada**

A partir de esta versión, ¡Automático!ALL\_ROWS está habilitado de forma predeterminada en todos los proyectos, lo que mejora la precisión de los informes. Si surgen problemas, los administradores de Apptio pueden desactivarlo temporalmente a través de la configuración del proyecto, pero se recomienda revisar y conciliar los proyectos para habilitar la función automáticaALL\_ROWS por defecto. ¡Habilitar automático!ALL\_ROWS puede tener un impacto menor en el rendimiento de los cálculos. Esta anulación puede eliminarse en futuras versiones para mejorar la precisión de los informes y reducir los errores, con el fin de ofrecer una mejor experiencia al usuario.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/121113-auto.png)

**Corregido en esta versión**

- Se ha añadido compatibilidad con múltiples dimensiones por filas, columnas y cuadrantes de valores en las consultas de datos de tablas.
- El soporte de datos de tabla en biit-server ahora acepta múltiples valores.
- Se han solucionado problemas de seguridad y vulnerabilidad.

## Cliente 2.13, 11 de abril de 2025

Plantilla de solicitud: 8314

**Carga de la tabla de suscripciones de correo electrónico filtradas**

La distribución de correos electrónicos se ha diseñado para optimizar el proceso de gestión de numerosas vistas filtradas con destinatarios únicos. Esta actualización es especialmente útil para los administradores que necesitan enviar vistas personalizadas y filtradas de informes por correo electrónico a muchos usuarios sin esfuerzo manual.

Para utilizar esta función, seleccione el icono **Exportar** en el modo «Ver» y seleccione **Suscripción por correo electrónico**. Active la opción **«Carga masiva XLS»** para descargar una plantilla. Esta plantilla enumera todos los filtros disponibles para el informe en contexto y proporciona un espacio para añadir destinatarios en cada fila. Añade combinaciones de filtros únicas para cada conjunto de destinatarios, guarda el archivo y vuelve a subirlo. Al cargar un archivo válido, observará dos cambios importantes: el archivo de reglas de suscripción se habilita, lo que indica que ha cargado un archivo que se puede descargar para verlo o editarlo, y se muestra un mensaje de carga correcta. La función de carga de tablas admite un AND lógico de los filtros aplicados a cada fila. El sistema de validación de datos comprueba que las columnas se hayan añadido correctamente, que las columnas de destinatarios de correo electrónico no estén en blanco y que se hayan rellenado otros campos esenciales para garantizar la integridad de los datos. El campo *Destinatarios* es obligatorio, mientras que solo uno de los demás campos es necesario para filtrar el conjunto de datos. La validación de datos se centra principalmente en los metadatos de la tabla (por ejemplo, las columnas correctas) y no necesariamente en los valores dentro de las columnas.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/121113-bu.png)

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/121113-bu1.png)

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/121113-bu2.png)

Para obtener más información, consulte [Suscripciones por correo electrónico](../reports/email-subscription.html).

**Corregido en esta versión**

- Se ha resuelto el problema de formato dinámico que provocaba una actualización/carga no deseada de la tabla en el componente del informe.
- Se ha resuelto el problema en el nuevo visor de informes.
- Se han solucionado problemas de vulnerabilidad.

## Servidor 12.11.12 - 28 de febrero de 2025

Plantilla de solicitud: 8191

**Nuevas funciones de la aplicación**

**Impacto del TCO de la TI híbrida para IBM ApptioCosting Standard ( v120 )**

La solución Hybrid IT TCO Impact está diseñada para ayudar a las organizaciones a medir y comprender el impacto financiero de sus entornos de TI híbridos en constante evolución. Permite a los usuarios finales, como los ejecutivos de alto nivel y los propietarios de aplicaciones, tomar decisiones informadas y garantizar que las migraciones aporten el valor financiero previsto.

Esta solución ofrece varias ventajas clave (como se demuestra en los informes siguientes), entre las que se incluyen la capacidad de comparar la huella actual de la TI híbrida con la objetivo, evaluar los beneficios financieros de la migración y realizar análisis detallados previos y posteriores a la migración. Estas características permiten a los usuarios tomar decisiones informadas sobre la migración de aplicaciones y optimizar sus entornos de TI híbridos.

Informe de nivel 100: Resumen del impacto del TCO de la TI híbrida

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cg-sum.jpg)

Informe de nivel 200: Información sobre el impacto del coste total de propiedad de la TI híbrida

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cg-200.jpg)

Informe de nivel 300: Análisis del impacto del coste total de propiedad (TCO) de la TI híbrida

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/cg-300.jpg)

Para habilitar esta nueva solución, comience de la siguiente manera:

Para obtener más detalles sobre la configuración, vaya [aquí](../../cost-transparency/reports/hybrid-it-tco-config.html).

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/3-steps.jpg)

**Public Cloud TCO para Costing Standard ( v120 ) y Costing Essentials ( v200 )**

La versión Public Cloud TCO para Costing
Standard ( v120 ) y Costing Essentials ( v200 ) ofrece múltiples ventajas para los usuarios principales, principalmente los equipos financieros de TI. Esta versión ofrece una perspectiva financiera sencilla y transparente de los costes mensuales de la nube pública, lo que ayuda a evitar sorpresas desagradables en la factura. También permite a los equipos impulsar la responsabilidad y garantizar una eficiencia óptima de los servicios de nube pública, minimizando el desperdicio.

La nueva versión incluye la instalación de nuevos componentes, como TCOPublic Cloud en v120 y TCOPublic CloudPublic Cloud y TCO Reporting en v200. Los usuarios pueden conectarse a los datos en la nube y utilizar funciones como «Nombre de la cuenta», «Unidad de negocio» y «Tabla de asignación de torres en la nube» para personalizar los informes y obtener información sobre las prácticas de su organización en la nube. Con esta versión, los usuarios pueden evaluar si su organización está aplicando las mejores prácticas en materia de nube, incluyendo la cobertura de RI y las tasas de utilización, para optimizar sus servicios en la nube.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/release_notes/pct-1.jpg)

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/release_notes/pct-2.jpg)

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/release_notes/pct-3.jpg)

Para obtener más información sobre la configuración, consulte [aquí](../../cost-transparency/reports/public-cloud-config.html).

**Costing Essentials (v200)**

Los informes de resumen del modelo son una nueva función diseñada para proporcionar a los usuarios una visión completa de los flujos de costes dentro del modelo. Esta versión incluye informes sobre mano de obra, proveedores, soluciones, consumidores y modelos de costes, y está disponible para todos los usuarios con acceso a los informes. Los informes están diseñados para mejorar la transparencia y la claridad para los usuarios, proporcionando una visión clara y detallada de los flujos de costes dentro del modelo. La vista del modelo laboral se incluye en el componente Informes de costes y mano de obra, mientras que la vista del modelo de costes se encuentra en la colección Vista del modelo. Los informes sobre proveedores, soluciones y consumidores se encuentran en sus respectivas colecciones.

Los usuarios pueden hacer clic en los campos para seleccionarlos y ver cómo fluyen los costes entre los diferentes objetos, lo que proporciona una forma clara e intuitiva de navegar por los informes. Los informes son accesibles para cualquier persona con acceso a los informes, sin necesidad de TBM Studio acceso. Los principales usuarios de los informes de resumen del modelo son los administradores y los usuarios avanzados, que los utilizan para refinar la asignación de costes, tomar decisiones informadas y optimizar sus procesos de gestión de costes.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/acm_images/ce-model-view.jpg)

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/acm_images/ce-lcm.jpg)

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/acm_images/ce-vcm.jpg)

Para ver todos los modelos de costes del informe, consulte [aquí](../../apptio-cost-management/out_of_the_box_reports/model-views-ce.html).

**Billing Essentials (v200)**

Se han realizado las siguientes mejoras en Billing Essentials V200.

- Se ha añadido compatibilidad con el idioma japonés para mejorar la accesibilidad de los usuarios.
- El informe de gestión de tarifas ahora incluye una nueva métrica denominada «Impacto del ajuste de tarifas», que proporciona información adicional sobre los cambios en las tarifas.

  ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/be/rm-1.jpg)

  ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/be/sm-2.jpg)

  Para obtener más información, consulte la configuración [aquí](../../billing-essentials/configure-billing-essentials/configuration.html).
- Se ha añadido un nuevo informe de resumen del modelo para proporcionar un resumen de la información clave sobre facturación.

  ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/be/bcm.jpg)

  Para saber más, consulte [aquí](../../billing-essentials/reports/model-views-be.html).

**Corregido en esta versión**

- Se ha resuelto el problema de análisis numérico de cadenas que contienen «e».
- Las asignaciones no utilizadas ya están disponibles de forma generalizada.
- Se han solucionado problemas de vulnerabilidad.

## Cliente 2.12, 28 de febrero de 2025

**Dependencia**

\*El cliente v2.12 es compatible con el servidor 12.11.12 y 12.11.11.x

**Nuevas funciones para clientes**

**Mejoras en la suscripción por correo electrónico**

Se ha mejorado la funcionalidad de suscripción por correo electrónico para aumentar la facilidad de uso, la personalización y la experiencia general del usuario. Los administradores ahora pueden configurar y personalizar los ajustes del correo electrónico, mientras que los usuarios finales recibirán informes claros e interactivos por correo electrónico. y claridad en la gestión y recepción de informes enviados por correo electrónico.

**Nombres dinámicos de archivos PDF** : los archivos PDF adjuntos a las suscripciones por correo electrónico ahora incluyen el nombre del informe y el período del informe en su nombre de archivo. Este cambio garantiza una identificación y organización más sencillas de los informes para los destinatarios.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/ess-1.jpg)

**Asunto y cuerpo del correo electrónico personalizables** : los administradores ahora pueden personalizar el asunto del correo electrónico utilizando campos dinámicos, como el nombre del informe, el período del informe y los filtros del informe, para crear asuntos más específicos y relevantes. El cuerpo del correo electrónico también se puede personalizar con campos dinámicos, como el nombre del informe, el período del informe y los filtros del informe, para proporcionar contexto o instrucciones adicionales directamente en el correo electrónico.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/ess-2.jpg)

**Botón de llamada a la acción actualizado** : El botón «Ver informe» del correo electrónico se ha actualizado a «Ver informe completo en Apptio » para que los destinatarios comprendan a dónde les llevará el enlace.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/ess-3.jpg)

**Enviar ahora** : esta función ofrece a los administradores una forma cómoda de verificar que la suscripción por correo electrónico funciona según lo previsto, garantizando que los suscriptores reciban el contenido esperado. Al utilizar «Enviar ahora», los usuarios pueden probar con confianza sus suscripciones de correo electrónico, lo que facilita la gestión y el mantenimiento de las mismas.

La función Enviar ahora está disponible en dos lugares: en Administrar suscripciones para cada suscripción de correo electrónico y en la pantalla de edición de una suscripción de correo electrónico individual. Para utilizar la función «Enviar ahora» en la pantalla de edición, los usuarios deben guardar primero cualquier cambio realizado en los detalles de la suscripción. Si se realizan cambios pero no se guardan, la función Enviar ahora se desactivará hasta que se guarden los cambios. Una vez guardado, los usuarios pueden hacer clic en «Enviar ahora» para enviar un correo electrónico de prueba a los suscriptores, lo que proporciona una forma rápida y sencilla de probar y verificar sus suscripciones de correo electrónico.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/send-nw.jpg)

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/send-nw1.jpg)

Para obtener más información, consulte [Suscripciones por correo electrónico](../reports/email-subscription.html).

**Tablas editables**

**editCell  La función ahora solo funciona en una columna específica** : En esta versión, se ha actualizado la función cellEdit para permitir notificaciones por correo electrónico más precisas. Los administradores ahora pueden configurar la función SendMail(, o «Aprobado en el momento de la notificación») para que se active exclusivamente cuando la columna «Estado de envío» cambie de «En curso» a «Enviado», lo que garantiza que los aprobadores solo reciban una notificación cuando se actualice el estado. Anteriormente, las modificaciones realizadas en otras columnas también activaban el envío de correos electrónicos si el estado seguía siendo «Enviado» Esta actualización introduce la sintaxis cellEdit(“column\_name”, «solo si cambia»), que garantiza que las acciones solo se activen cuando se modifique la columna especificada.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/et-edit.jpg)

**Mejoras en la función Mostrar cambios** : La función Mostrar cambios se ha actualizado con las siguientes mejoras:

La clave principal (PK) ahora se muestra en la vista «Mostrar cambios», lo que permite identificar más fácilmente los registros modificados.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/sc-pk.jpg)

En el caso de las tablas editables enriquecidas, la vista «Mostrar cambios» solo muestra los cambios realizados en la tabla de origen subyacente. Esto se indica mediante la presencia de un valor para los campos modificados y la ausencia de un valor para los campos no modificados.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/sc-pk1.jpg)

**Corregido en esta versión**

- Las vistas «Mostrar cambios» ahora se alinean con el paso Canalización de datos > Tabla editable.
- Se han corregido vulnerabilidades de seguridad.

## Servidor 12.11.11.2 - 27 de febrero de 2025

- Se han corregido vulnerabilidades de seguridad.

## Servidor 12.11.11.1 - 5 de febrero de 2025

- Actualización trimestral de Java.
- Se ha solucionado el problema de «entorno no encontrado» en Apptio BI.

## Servidor 12.11.11 - 17 de enero de 2025

Plantilla de solicitud: v120-8191

**Nuevas funciones de la aplicación**

**Billing Essentials GA ( v200 )**

Esta versión ofrece las siguientes mejoras para optimizar la experiencia general del usuario y proporcionar una gestión más eficiente de los procesos de facturación y carga de datos.

- **Informes mejorados** : el informe administrativo del proceso de facturación se ha integrado en la colección de facturación, con permisos de control de acceso basados en roles (RBAC) configurados para restringir el acceso a los propietarios autorizados del proceso de facturación.
- **Exportación y archivo de asientos contables:** La pestaña Archivo de asientos contables de facturación ahora permite a los usuarios exportar asientos contables a un archivo Excel (.xlsx) y crear una tabla simplificada con fines de informes de auditoría, utilizando un script CopyTable para garantizar la integridad de los datos.
- **Archivado de facturas** : La pestaña Archivo de facturas cuenta con un botón Copiar detalles de la factura, que facilita el archivado de las facturas creando una copia duplicada de la factura original, lo que garantiza un registro permanente para fines de auditoría y cumplimiento normativo.

  ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/be/be-rn-1.jpg)

  ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/be/be-rn-2.jpg)

**Corregido en esta versión**

- Se han eliminado datos de forma permanente de una tabla en el canal de datos.
- Se han solucionado problemas de vulnerabilidad.
- Optimizaciones de cálculo de precisión

## Cliente 2.11, 17 de enero de 2025

**Dependencia**

\*El cliente v2.11 es compatible con el servidor 12.11.11 y 12.11.10.x

\*Algunas funciones de Client v2.11 dependen de las nuevas funciones de Server 12.11.11.

**Nuevas funciones para clientes**

**La función de carga de tablas ya está disponible de forma generalizada.**

El componente Table Upload se lanzó hace dos años y la visibilidad en la cinta de Studio se controlaba mediante la función Enable Features. Con su traslado a GA, no se producirá ningún impacto en ningún proyecto existente.

**Mejoras en la distribución de correo electrónico**

- **Suscripciones a vistas filtradas** : esta función permite a los usuarios compartir informes filtrados con destinatarios específicos a través de un sistema de suscripción. Los destinatarios recibirán un hipervínculo para acceder al informe con selecciones de segmentación preaplicadas, lo que les permitirá ver el informe con la configuración de filtro deseada. Además, los destinatarios tienen la opción de recibir un documento PDF adjunto, que se puede configurar para incluir o excluir la vista simple vinculada, manteniendo al mismo tiempo la configuración de filtro seleccionada. Esta función ofrece una forma flexible y segura de compartir informes con otras personas, garantizando que los destinatarios reciban la información que necesitan en un formato fácil de usar.

  ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/fv.jpg)

  Para obtener más información, consulte [Suscripciones por correo electrónico con vista filtrada](../reports/email-subscription.html).
- **Suscripción duplicada** : esta función permite a los usuarios crear una copia de una suscripción de correo electrónico existente y simplifica el proceso de gestión de suscripciones. Para implementar esta función, se ha añadido un nuevo icono «Duplicar suscripción» al cuadro de diálogo Administrar suscripción, que permite a los usuarios crear una copia de una suscripción existente. La suscripción duplicada se nombra automáticamente con el prefijo «Copia de» seguido del nombre de la suscripción original, y los usuarios pueden editar los detalles de la suscripción duplicada, incluyendo el nombre, la frecuencia y la plantilla de correo electrónico adjunta.

  ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/dupsub.jpg)

  Para obtener más información, consulte [Suscripciones duplicadas al correo electrónico](../reports/email-subscription.html).

**Barra de desplazamiento horizontal para pestañas de documentos abiertos en Studio**

Para mejorar la gestión de varias pestañas inferiores abiertas en el estudio, se ha introducido una barra de desplazamiento horizontal. Permite a los usuarios navegar fácilmente por varias pestañas abiertas. Además, la última pestaña abierta se resaltará, lo que proporcionará un indicador visual claro de la pestaña actual en foco.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/scroll.jpg)

Anteriormente, las pestañas desaparecían si no había espacio, por lo que resultaba tedioso volver a abrirlas.

**Tablas editables**

- **La opción «Crear rama» permite marcar automáticamente todas las tablas editables** : Se ha introducido una nueva función para mejorar la gestión de las tablas editables en las ramas. Esta mejora proporciona un flujo de trabajo más optimizado y eficiente para gestionar los cambios en el esquema y los datos de las ramas, y ayuda a evitar cambios no deseados en el tronco.

  Al crear una rama, el usuario ahora puede seleccionar la opción de revisar automáticamente todas las tablas editables, lo que las actualizará en el espacio de trabajo de desarrollo. No es necesario realizar comprobaciones manuales de tablas individuales, lo que reduce el riesgo de inconsistencias y errores en los datos. El proceso de pago ahora está automatizado, lo que garantiza que todas las tablas editables se actualicen correctamente en la sucursal.

  Anteriormente, cuando se actualizaban los datos en una rama, se actualizaban automáticamente en el tronco. No hubo ningún control para validar o confirmar los cambios en una rama. Para obtener más información, consulte [Crear una rama con la opción de pago automático](../admin/bp-branching-projects.html "Aplicable a: TBM Studio 12.1 y posteriores").
- **Exponer el nombre de usuario y la fecha de edición del historial de cambios** : El proceso de configuración de la solución de tabla editable se mejora al exponer dos nuevas columnas de informes: las columnas del sistema.Username y .Edit Date . Los administradores ahora pueden acceder fácilmente a estas columnas en el Explorador de proyectos cuando se abre una tabla editable y arrastrarlas al panel de configuración ad hoc para un componente de informe de tabla editable. Además, estas columnas ahora son visibles en el modo de vista de informe, lo que permite a los usuarios ordenarlas y cambiar su tamaño según sea necesario. Esta actualización elimina la necesidad de crear columnas separadas y utilizar ApptioScript para rellenar la información, lo que agiliza el proceso de configuración y mejora la experiencia general del usuario.

  ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/sh-1.jpg)

  ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/sh-2.jpg)

  ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/sh-3.jpg)

  Anteriormente, estas dos columnas solo estaban disponibles en Mostrar cambios. Para evitar confusiones, los nombres de las columnas de la tabla «Mostrar cambios» se han renombrado como «Nombre de usuario» y « EditDate ».

  Para obtener más información, consulte [Mostrar/ocultar.Nombre de usuario y .EditDate](../reports/tables/component-config-panel.html "Aplicable a: TBM Studio 12.0 y posteriores").
- **Mejora del rendimiento al guardar/actualizar de forma masiva** : Se ha mejorado significativamente el rendimiento de las funciones de guardar y cargar de forma masiva, lo que ha dado como resultado un procesamiento más rápido y eficiente de grandes conjuntos de datos.

  | Número de filas actualizadas | Número de columnas actualizadas | Tiempo transcurrido (en segundos) | Nuevo tiempo (en segundos) |
  | --- | --- | --- | --- |
  | 10.000 | 3 | 179 | 2 |
  | 20 000 | 3 | 578 | 4 |
  | 30 000 | 3 | 1189 | 7 |
  | 1 lakh | 1 | tiempo espera | 47 |
  | 200 000 rupias | 5 | tiempo espera | 110 |

**Corregido en esta versión**

- Se ha solucionado el problema por el que los menús desplegables no respetaban la seguridad a nivel de fila para la tabla estándar.
- Se ha solucionado el problema por el que el ajuste automático del tamaño de la tabla no funcionaba correctamente con la opción Árbol.
- Se ha solucionado el problema de las traducciones pseudo de cadenas que faltaban.
