---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Publicaciones recientes"
breadcrumb: []
source_path: "studio/whats-new.html"
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
last_updated: "2026-06-09"
summary: ""
---
# Publicaciones recientes

## Cliente 2.16 - 15 de agosto de 2025

- Evitar el error de Tabla Editable cuando sólo se registra el Esquema.
- Se ha introducido la [función Calc Management Scheduler](admin/cacl-mgmt-scheduler.html "Se aplica a: 2.16 y posteriores. Esta función automatizará los cálculos de puesta a disposición a nivel de proyecto y de rama.") para automatizar los cálculos de puesta en escena a nivel de proyecto y de sucursal.

## Servidor 12.11.16 - 15 de agosto de 2025

- La detección [de anomalías de compilación](admin/build-anomaly-detection.html "La función de detección de anomalías está diseñada para ayudarle a identificar cambios inusuales en el esfuerzo de cálculo, lo que puede ayudarle a optimizar sus informes y transformaciones. Esta función se basa en los datos recogidos por Calc Explorer, que proporciona información detallada sobre el esfuerzo de cálculo de cada construcción.") ahora está disponible de forma general.
- [Análisis sintáctico de Excel mejorado](reports/tables/enhanced-excel-parsing.html)
- Norma de cálculo de costes (plantillas v120 )
  - [TCO y uso de AI](../cost-transparency/configuration/ai-tco-overview.html "La Inteligencia Artificial (IA) es una prioridad clave para muchas organizaciones, y cada vez se encarga más a los CIOs que lideren las estrategias de IA en toda la organización. A medida que se acelera el gasto en IA, también lo hace la complejidad. Los CIO admiten que la gestión de los costes limita su capacidad para liberar el verdadero valor de la IA. Para que las organizaciones adopten, amplíen y gestionen las iniciativas de IA de forma sostenible y aprovechen todo su valor, necesitan una visibilidad clara de los costes, el uso y la adopción de la IA.") : se ha añadido una nueva pestaña de definición.
  - [Impacto del coste total de propiedad de TI híbrida](../cost-transparency/reports/hyb-it-sum.html) : nueva ventana emergente de tendencias detalladas en el informe de análisis y métrica de coste medio por aplicación añadida al informe de resumen
  - Mainframe TCO - Añadido un informe detallado y un informe de facturas.
  - Se ha añadido la etiqueta Aplicación a los informes de [TCO de la nube pública](../cost-transparency/reports/pub-cloud-tco-overview.html).
  - Se ha añadido un nuevo campo "Código" en las tablas de datos maestros de integración de la planificación.
- Mejoras en Costing Essentials (plantillas v200 )
  - Se ha añadido un nuevo campo en el informe del banco de trabajo de [asignación de mano de obra](../apptio-cost-management/workbench/labor-mapping.html) y en el informe del banco de trabajo de [asignación de proveedores](../apptio-cost-management/workbench/vendor-mapping.html).
  - Se han añadido nuevos campos en el informe del banco de trabajo de [asignación de organizaciones](../apptio-cost-management/workbench/organization-mapping.html "Ofrece la posibilidad de completar el enriquecimiento de datos para sus organizaciones de TI (unidades de negocio).").
  - Se ha actualizado la fórmula de recuento de filas para TS Infraestructura y TS Plataforma.
  - Se ha añadido la etiqueta Aplicación a los informes de [TCO de la nube pública](../cost-transparency/reports/pub-cloud-tco-overview.html).
  - Se ha añadido un nuevo campo "Código" en las tablas de datos maestros de integración de la planificación.
  - Se han añadido métricas de depreciación al Modelo de Servicios Tecnológicos.

**Corregido en esta versión**

- Se ha solucionado el problema de los indicadores clave de rendimiento que no se mostraban en japonés.

## Servidor 12.11.15.1 - 25 de julio de 2025

- Se ha solucionado un problema de rendimiento configurando la JVM para que utilice la configuración predeterminada de GC de G1.

## Servidor 12.11.15 - 4 de julio de 2025

- Introdujo IBM Maximo **Maintenance Cost Insights** (MCI), impulsado por IBM Apptio Costing ( v200 ). Esta solución proporciona a los clientes de Maximo una integración bidireccional lista para usar entre IBM Maximo y IBM Apptio Costing. Proporciona a los gestores de mantenimiento de Maximo visibilidad de su coste total de mantenimiento en órdenes de trabajo, activos y ubicaciones. Al identificar los principales factores de coste, como la mano de obra, los materiales, las herramientas y los servicios, la solución facilita la responsabilidad financiera y mejora la planificación de las operaciones de mantenimiento.para más información, consulte el apartado ["Panorama general](https://www.ibm.com/docs/en/masv-and-l/maximo-manage/cd?topic=applications-integrating-maximo-maintenance-cost-insights-apptio "(se abre en una pestaña o una ventana nueva)") "
- Costing Standard (Plantillas v120 )
  - Mejoras en los informes de uso y coste total de propiedad de la IA; solución añadida a los proyectos de referencia
  - Mejoras en el coste total de propiedad (BETA)
  - Localización al japonés de Hybrid IT TCO Impact y AI TCO & Usage
- Mejoras en Costing Essentials ( v200 ): se eliminó la opción "Global" de [todas las segmentaciones](https://www.ibm.com/docs/en/apptio-commercial/costing-essentials/saas?topic=reports-labor-review "(se abre en una pestaña o una ventana nueva)") para aprovechar mejor las vistas guardadas, se eliminaron algunos [informes avanzados de dispositivos de usuario final](https://www.ibm.com/docs/en/apptio-commercial/costing-essentials/saas?topic=started-end-user-devices-reports "(se abre en una pestaña o una ventana nueva)") y se agregó la estrategia de asignación de personal FTE.
- Calc Explorer ahora se carga al desplazarse, mejorando el tiempo de carga inicial.
- Los cuadros de mando se han actualizado con los últimos datos de evaluación comparativa.

**Corregido en esta versión**

- Corregido el error en el Explorador de Calc al buscar en Mostrar Dev Builds.
- Se ha solucionado el problema por el que el diagrama de Sankey en Calc Explorer se interrumpía al buscar o paginar antes de perforar.
- Vulnerabilidades de seguridad corregidas.

## Cliente 2.15 - 4 de julio de 2025

- Mejoras en Costing Essentials ( v200 ) - Se ha eliminado la opción "Global" de [todas las cortadoras](https://www.ibm.com/docs/en/apptio-commercial/costing-essentials/saas?topic=reports-labor-review "(se abre en una pestaña o una ventana nueva)") para aprovechar mejor las vistas guardadas

## Servidor 12.11.14.1 - 20 de junio de 2025

- Se ha solucionado el problema de los trabajos recurrentes programados que no se activaban.

## Servidor 12.11.14 - 30 de mayo de 2025

**Nuevas funciones**

- Presentó IBM Apptio 's **AI TCO & Usage** solution empowering CIOs, Business & Solution Leaders, and AI & Data Science teams with end-to-end visibility into their AI total cost of ownership and usage. Al revelar información sobre los modelos y las soluciones de IA, impulsa decisiones más inteligentes para las inversiones en IA, permite una ampliación responsable y sienta las bases para las conversaciones sobre el valor de la IA. Para más información, consulte [Visión general](../cost-transparency/configuration/ai-tco-overview.html "La Inteligencia Artificial (IA) es una prioridad clave para muchas organizaciones, y cada vez se encarga más a los CIOs que lideren las estrategias de IA en toda la organización. A medida que se acelera el gasto en IA, también lo hace la complejidad. Los CIO admiten que la gestión de los costes limita su capacidad para liberar el verdadero valor de la IA. Para que las organizaciones adopten, amplíen y gestionen las iniciativas de IA de forma sostenible y aprovechen todo su valor, necesitan una visibilidad clara de los costes, el uso y la adopción de la IA."), [Guía Gonfig](../cost-transparency/configuration/ai-tco-configguide.html) y [Recopilación de informes](../cost-transparency/reports/ai-tco-report-collection.html).
- *Costing Standard (v120)*
  - Se han introducido informes de [visión general de los modelos](../cost-transparency/reports/pub-cloud-model-views-cs.html) para visualizar los flujos de costes, proporcionando información detallada y mejorando la transparencia.
  - Se han añadido nuevos informes de [Hybrid IT Impact Admin](../cost-transparency/reports/hyb-tco-imp-admin.html "Se trata de un sustituto del conector mensual Apptio Datalink utilizado para \"congelar\" cualquier aplicación migrada con su TCO, volumen y coste unitario. Las instrucciones están disponibles en el informe de administración.") con el botón Copiar tabla para simplificar la configuración y eliminar la necesidad de conectores de enlace de datos de Apptio a Apptio.
  - Informe [Public Cloud TCO](../cost-transparency/reports/pub-cloud-tco-overview.html) actualizado con la pestaña Definición, gráficos de doble eje para las tarifas unitarias, una tabla de Atributos redimensionada y un orden de selección de columnas revisado que sigue una jerarquía taxonómica.
- *Proyecto de uso* - Añadidas nuevas fórmulas para Tipo de usuario, Rol y Persona en la versión de marzo de 2025.
- *Flujos de recomendación*
  - Se ha introducido un nuevo flujo de trabajo [de métricas no utilizadas](troubleshooting/studio-unused-metrics.html "Esta función proporciona recomendaciones automáticas sobre las métricas calculadas no utilizadas, ofreciendo visibilidad de las métricas creadas por el usuario que no se utilizan en otras métricas o informes. El sistema comprobará automáticamente los cambios y marcará las incidencias como resueltas.") (Beta) para optimizar el sistema.
  - Introducido el flujo de trabajo de [ponderaciones positivas y negativas](troubleshooting/positive-and-negative-recom.html "Esta función ayuda a solucionar los problemas de peso encontrando y avisando de los pesos positivos y negativos mezclados, para que pueda corregirlos y obtener resultados precisos.")
- *Detección de anomalías de construcción (Beta)* - Se ha introducido una nueva función de detección de [anomalías de construcción](admin/build-anomaly-detection.html "La función de detección de anomalías está diseñada para ayudarle a identificar cambios inusuales en el esfuerzo de cálculo, lo que puede ayudarle a optimizar sus informes y transformaciones. Esta función se basa en los datos recogidos por Calc Explorer, que proporciona información detallada sobre el esfuerzo de cálculo de cada construcción.") para mejorar los tiempos de cálculo y el rendimiento.

**Mejoras**

- [Public
  Cloud TCO](../cost-transparency/reports/pub-cloud-tco-overview.html) para Costing Essentials se ha mejorado con la pestaña Definición, gráficos de doble eje para las tarifas unitarias, una tabla de Atributos redimensionada y un orden de selección de columnas revisado que sigue una jerarquía de taxonomía.
- [Informe general del modelo](../apptio-cost-management/out_of_the_box_reports/model-views-ce.html) Mejoras en Costing Essentials

**Arreglos**

- Se ha solucionado un problema con la función Año anterior en Métricas calculadas paraCosting Essentials
- Corrección de vulnerabilidades y seguridad

## Cliente 2.14 - 30 de mayo de 2025

**Novedades**

- Se han añadido funciones para mejorar la experiencia de usuario de [la suscripción por correo electrónico](reports/email-subscription.html), como la activación y desactivación de suscripciones, la función de búsqueda y el aumento del límite de caracteres del cuerpo del correo electrónico.
- Las columnas Conjunto de cambios y Cambios del Explorador de Calc ahora se pueden filtrar (buscar) por cualquier cosa que aparezca en los cuadros de diálogo que abren.
- Tablas editables - Se ha añadido la posibilidad de descargar, editar y cargar los datos de [las tablas de transformación](data_studio/create-table-from-et.html) correspondientes a un periodo concreto para corregir errores anteriores.

**Arreglos**

- Solucionado el problema de error en el informe de tabla editable después de añadir o eliminar un valor de columna y guardar.
- Se ha solucionado el problema del script “cellEdit“ que ignoraba el error de validación de las celdas existentes.
- Corregida la validación del valor único en la carga de archivos/botón script

## Servidor 12.11.13.1 - 25 de abril de 2025

- Actualización trimestral de Java.
- Se ha solucionado el problema con el grupo de conexiones MySQL que provocaba el agotamiento de las sentencias preparadas.

## Servidor 12.11.13 - 11 de abril de 2025

**Costing Standard (v120)**

Esta versión incluye las siguientes mejoras clave para mejorar la experiencia de usuario y la funcionalidad.

- Proyecto de uso: informes basados en roles según la persona de Frontdoor.
- IBM Apptio Turbonomic Integration ya es GA. Para saber más, vea este [vídeo](https://youtu.be/-FY7WfDBK1g?si=20-TTKhVDBaPRo0v "(se abre en una pestaña o una ventana nueva)").
- Asistencia en japonés para Public Cloud TCO.
- Public Cloud TCO añadido al proyecto de referencia Costing Standard

**Costing Essentials(v200)**

Esta versión incluye dos mejoras clave:

- Asistencia en japonés para Public Cloud TCO.
- Public Cloud TCO añadido al proyecto de referencia Costing Essentials

**Proyecto de uso: informes basados en funciones de Frontdoor persona**

Esta versión introduce informes basados en roles sobre Frontdoor personas, proporcionando a los administradores una mayor visibilidad de la participación de los usuarios y la adopción. El panel de control de uso de Apptio permite ahora a los administradores supervisar la participación en los informes, la actividad de los usuarios y el rendimiento de los informes, segmentados por funciones de usuario y personas definidas en Frontdoor. Esta función permite a los administradores saber quién se conecta a Apptio e identificar las áreas en las que hay que centrar los esfuerzos de adopción, impulsando la capacitación específica.

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/121113-usage.png)

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/121113-usage2.png)

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/121113-usage1.png)

**¡Automático!Configuración ALL\_ROWS activada por defecto**

¡A partir de esta versión, Automatic!ALL\_ROWS está activado por defecto en todos los proyectos, lo que mejora la precisión de los informes. Si se producen problemas, los administradores de Apptio pueden desactivarlo temporalmente a través de la configuración del proyecto, pero se les recomienda que revisen y concilien los proyectos para activar el modo automáticoALL\_ROWS por defecto. ¡Activación automática!ALL\_ROWS puede tener un impacto menor en el rendimiento de la calc. Es posible que esta anulación se elimine en futuras versiones para mejorar la precisión de los informes y reducir los errores para mejorar la experiencia del usuario.

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/121113-auto.png)

**Corregido en esta versión**

- Se ha añadido soporte para múltiples dimensiones por filas, columnas y cuadrante de valores en las consultas de datos de tablas.
- El soporte de datos de tabla en biit-server acepta ahora valores múltiples.
- Se han solucionado problemas de seguridad y vulnerabilidad.

## Cliente 2.13 - 11 de abril de 2025

Modelo de solicitud: 8314

**Tabla de carga de suscripciones de correo electrónico filtradas**

La distribución por correo electrónico se ha diseñado para agilizar el proceso de gestión de numerosas vistas filtradas con destinatarios únicos. Esta actualización es especialmente beneficiosa para los administradores que necesitan enviar vistas personalizadas y filtradas de informes por correo electrónico a muchos usuarios sin esfuerzo manual.

Para utilizar esta función, seleccione el icono **Exportar** en el modo "Ver" y seleccione **Suscripción por correo electrónico**. Habilite el conmutador **Carga masiva XLS** para descargar una plantilla. Esta plantilla enumera todos los filtros disponibles para el informe en contexto y proporciona un espacio para añadir destinatarios contra cada fila. Añada combinaciones de filtros únicas para cada grupo de destinatarios, guarde el archivo y vuelva a cargarlo. Al cargar un archivo válido, observará dos cambios clave: se activa el Archivo de reglas de suscripción, lo que indica que ha cargado un archivo que puede descargarse para verlo o editarlo, y se muestra un mensaje de carga correcta. La función de carga de tablas admite un AND lógico de los filtros aplicados a cada fila. El sistema de validación de datos comprueba que las adiciones de columnas sean correctas, que las columnas de destinatarios de correo electrónico no estén en blanco y otros campos esenciales para garantizar la integridad de los datos. El campo *Destinatarios* es obligatorio, mientras que sólo uno de los otros campos es necesario para filtrar el conjunto de datos. La validación de datos se centra principalmente en los metadatos de la tabla (por ejemplo, columnas correctas) y no necesariamente en los valores de las columnas.

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/121113-bu.png)

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/121113-bu1.png)

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/121113-bu2.png)

Para saber más, consulte [Suscripciones por correo electrónico](reports/email-subscription.html).

**Corregido en esta versión**

- Resuelto el problema de formato dinámico que provocaba la actualización/carga no deseada de la tabla en el componente de informe.
- Resuelto el problema en el nuevo visor de informes.
- Se han solucionado problemas de vulnerabilidad.

## Servidor 12.11.12 - 28 de febrero de 2025

Modelo de solicitud: 8191

**Nuevas funciones de la aplicación**

**Impacto del coste total de propiedad de la TI híbrida para IBM Apptio Costing Standard ( v120 )**

La solución Hybrid IT TCO Impact está diseñada para ayudar a las organizaciones a medir y comprender el impacto financiero de sus entornos de TI híbrida en evolución. Permite a los usuarios finales, como los ejecutivos de la C-Suite y los propietarios de aplicaciones, tomar decisiones con conocimiento de causa y garantizar que las migraciones aporten el valor financiero previsto.

Esta solución proporciona varias ventajas clave (como demuestran los informes siguientes), incluida la capacidad de comparar la huella de TI híbrida actual frente a la deseada, evaluar el beneficio financiero de la migración y realizar análisis detallados previos y posteriores a la migración. Estas funciones permiten a los usuarios tomar decisiones informadas sobre la migración de aplicaciones y optimizar sus entornos de TI híbridos.

Informe Level 100: Resumen del impacto de la TI híbrida en el coste total de propiedad

![imagen](../../../../03-media/apptio-costing-standard/resources/images/ct_images/cg-sum.jpg)

Informe Level 200: Hybrid IT TCO Impact Insights

![imagen](../../../../03-media/apptio-costing-standard/resources/images/ct_images/cg-200.jpg)

Informe Level 300: Análisis del impacto del coste total de propiedad de la TI híbrida

![imagen](../../../../03-media/apptio-costing-standard/resources/images/ct_images/cg-300.jpg)

Para habilitar esta nueva solución, empieza como sigue:

Para más detalles sobre la configuración, vaya [aquí](../cost-transparency/configuration/hybrid-it-tco.html).

![imagen](../../../../03-media/apptio-costing-standard/resources/images/ct_images/3-steps.jpg)

**Public Cloud TCO para Costing Standard ( v120 ) y Costing Essentials ( v200 )**

La versión Public Cloud TCO para Costing Standard ( v120 ) y Costing Essentials ( v200 ) ofrece múltiples ventajas para los usuarios primarios, principalmente los equipos financieros de TI. Esta versión proporciona una visión financiera sencilla y transparente de los costes mensuales de la nube pública, lo que ayuda a evitar facturas inesperadas. También permite a los equipos impulsar la responsabilidad y garantizar una eficiencia óptima de los servicios de nube pública, minimizando el despilfarro.

La nueva versión incluye la instalación de nuevos componentes, comoPublic
Cloud TCO en v120 yPublic Cloud TCO yPublic
Cloud TCO Reporting en v200. Los usuarios pueden conectarse a los datos de la nube y utilizar funciones como el nombre de la cuenta, la unidad de negocio y la tabla de asignación de torres en la nube para adaptar los informes y obtener información sobre las prácticas en la nube de su organización. Con esta versión, los usuarios pueden evaluar si su organización está aplicando las prácticas de nube "Best in Class", incluidas las tasas de cobertura y utilización de RI, para optimizar sus servicios en la nube.

![imagen](../../../../03-media/apptio-costing-standard/resources/images/ct_images/release_notes/pct-1.jpg)

![imagen](../../../../03-media/apptio-costing-standard/resources/images/ct_images/release_notes/pct-2.jpg)

![imagen](../../../../03-media/apptio-costing-standard/resources/images/ct_images/release_notes/pct-3.jpg)

Para más información sobre la configuración, consulte [aquí](../cost-transparency/reports/public-cloud-config.html).

**Costing Essentials (v200)**

Los informes generales del modelo son una nueva función diseñada para ofrecer a los usuarios una visión completa de los flujos de costes dentro del modelo. Esta versión incluye informes sobre mano de obra, proveedores, soluciones, consumidores y modelo de costes, y está disponible para todos los usuarios con acceso a informes. Los informes están diseñados para aumentar la transparencia y claridad para los usuarios, proporcionando una visión clara y detallada de los flujos de costes dentro del modelo. La Vista Modelo Mano de Obra se incluye en el componente Informes Coste-Labor, mientras que la Vista Modelo Coste se encuentra en la colección Vista Modelo. Los informes sobre proveedores, soluciones y consumidores se encuentran en sus respectivas colecciones.

Los usuarios pueden hacer clic en los campos para seleccionar y ver cómo fluyen los costes entre los distintos objetos, lo que proporciona una forma clara e intuitiva de navegar por los informes. Los informes son accesibles para cualquier persona con acceso a informes, sin necesidad de acceder a TBM Studio . Los principales usuarios de los informes de resumen de modelos son los administradores y los usuarios avanzados, para perfeccionar las imputaciones de costes, tomar decisiones con conocimiento de causa y optimizar sus procesos de gestión de costes.

![imagen](../../../../03-media/apptio-costing-standard/resources/images/acm_images/ce-model-view.jpg)

![imagen](../../../../03-media/apptio-costing-standard/resources/images/acm_images/ce-lcm.jpg)

![imagen](../../../../03-media/apptio-costing-standard/resources/images/acm_images/ce-vcm.jpg)

Para ver todos los modelos de costes del informe, consulte [aquí](../apptio-cost-management/out_of_the_box_reports/model-views-ce.html).

**Billing Essentials (v200)**

Se han introducido las siguientes mejoras en Billing Essentials V200.

- Se ha añadido compatibilidad con el idioma japonés para mejorar la accesibilidad de los usuarios.
- El informe de gestión de tarifas incluye ahora una nueva métrica de impacto del ajuste de tarifas, que proporciona información adicional sobre los cambios de tarifas.

  ![imagen](../../../../03-media/apptio-costing-standard/resources/images/be/rm-1.jpg)

  ![imagen](../../../../03-media/apptio-costing-standard/resources/images/be/sm-2.jpg)

  Para saber más, consulte la configuración [aquí](../billing-essentials/configure-billing-essentials/configuration.html).
- Se ha añadido un nuevo Informe general del modelo para ofrecer un resumen de la información clave sobre facturación.

  ![imagen](../../../../03-media/apptio-costing-standard/resources/images/be/bcm.jpg)

  Para saber más, consulte [aquí](../billing-essentials/reports/model-views-be.html).

**Corregido en esta versión**

- Resuelto el problema de análisis numérico de cadenas que contienen 'e'.
- Asignaciones no utilizadas es ahora GA.
- Se han solucionado problemas de vulnerabilidad.

## Cliente 2.12 - 28 de febrero de 2025

**Dependencia**

\*Cliente v2.12 es compatible con Servidor 12.11.12 y 12.11.11.x

**Nuevas funciones para clientes**

**Mejoras en la suscripción por correo electrónico**

Se ha mejorado la funcionalidad de suscripción por correo electrónico para mejorar la facilidad de uso, la personalización y la experiencia general del usuario. Los administradores pueden ahora configurar y personalizar los ajustes del correo electrónico, mientras que los usuarios finales obtendrán informes interactivos claros por correo electrónico. y claridad en la gestión y recepción de informes enviados por correo electrónico.

**Nombres dinámicos de archivos PDF** : El archivo PDF adjunto a las suscripciones por correo electrónico ahora incluye el nombre del informe y el periodo del informe en su nombre de archivo. Este cambio facilita a los destinatarios la identificación y organización de los informes.

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/ess-1.jpg)

**Asunto y cuerpo del correo personalizables** : Los administradores ahora pueden personalizar la línea de asunto del correo electrónico utilizando campos dinámicos, como Nombre del informe, Período del informe y Filtros del informe para obtener asuntos de correo electrónico más relevantes y específicos del contexto. El cuerpo del correo electrónico también puede personalizarse con campos dinámicos, como Nombre del informe, Período del informe y Filtros del informe para proporcionar contexto o instrucciones adicionales directamente en el correo electrónico.

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/ess-2.jpg)

**Botón de llamada a la acción actualizado** : El botón "Ver informe" del correo electrónico se ha actualizado a "Ver informe completo en Apptio " para que los destinatarios entiendan a dónde les llevará el enlace.

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/ess-3.jpg)

**Enviar ahora** : Esta función proporciona a los administradores una forma cómoda de verificar que la suscripción por correo electrónico funciona según lo previsto, garantizando que los suscriptores reciben el contenido esperado. Al utilizar Send Now, los usuarios pueden probar con confianza sus suscripciones de correo electrónico, lo que facilita la gestión y el mantenimiento de las mismas.

Se puede acceder a la función Enviar ahora desde dos lugares: en Gestionar suscripciones para cada suscripción de correo electrónico y en la pantalla de edición de una suscripción de correo electrónico individual. Para utilizar Enviar ahora en la pantalla de edición, los usuarios deben guardar primero los cambios realizados en los detalles de la suscripción. Si se realizan cambios pero no se guardan, la función Enviar ahora se desactivará hasta que se guarden los cambios. Una vez guardado, los usuarios pueden hacer clic en Enviar ahora para enviar un correo electrónico de prueba a los suscriptores, proporcionando una manera rápida y fácil de probar y verificar sus suscripciones de correo electrónico...

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/send-nw.jpg)

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/send-nw1.jpg)

Para saber más, consulte [Suscripciones por correo electrónico](reports/email-subscription.html).

**Tablas editables**

**editCell ahora sólo funciona en una columna específica** : En esta versión, la función cellEdit se ha actualizado para permitir notificaciones por correo electrónico más precisas. Ahora los administradores pueden configurar la función SendMail( ) para que se active exclusivamente cuando la columna "Estado de envío" cambie de "En curso" a "Enviado", garantizando así que los aprobadores reciban una notificación sólo cuando se actualice el estado. Anteriormente, las ediciones de otras columnas también activaban correos electrónicos si el estado seguía siendo "Enviado" Esta actualización introduce la sintaxis cellEdit(“column\_name” ), que garantiza que las acciones sólo se activen cuando se modifique la columna especificada.

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/et-edit.jpg)

**Mejoras en la función Mostrar cambios** : La función Mostrar cambios se ha actualizado con las siguientes mejoras:

La clave primaria (PK) se muestra ahora en la vista Mostrar cambios, lo que permite identificar más fácilmente los registros modificados.

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/sc-pk.jpg)

En el caso de las tablas editables enriquecidas, la vista Mostrar cambios sólo muestra los cambios realizados en la tabla de origen subyacente. Esto se indica mediante la presencia de un valor para los campos modificados y la ausencia de un valor para los campos no modificados.

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/sc-pk1.jpg)

**Corregido en esta versión**

- las vistas "Mostrar cambios" ahora se alinean con el paso Canalización de datos > Tabla editable.
- Vulnerabilidades de seguridad corregidas.

## Servidor 12.11.11.2 - 27 de febrero de 2025

- Vulnerabilidades de seguridad corregidas.

## Servidor 12.11.11.1 - 5 de febrero de 2025

- Actualización trimestral de Java.
- Se ha solucionado el problema de entorno "no encontrado" en Apptio BI.

## Servidor 12.11.11 - 17 de enero de 2025

Modelo de solicitud: v120-8191

**Nuevas funciones de la aplicación**

**Billing Essentials GA ( v200 )**

Esta versión proporciona las siguientes mejoras para mejorar la experiencia general del usuario y ofrecer una gestión más eficaz de los procesos de facturación y carga de datos.

- **Informes mejorados** : El informe de administración del proceso de facturación se ha integrado en la colección de facturación, con permisos de control de acceso basados en funciones (RBAC) configurados para restringir el acceso a los propietarios autorizados del proceso de facturación.
- **Exportación y archivo de asientos:** La pestaña Archivo de Diario de Facturación permite ahora a los usuarios exportar asientos a un archivo Excel (.xlsx) y crear una tabla aplanada con fines de informes de auditoría, utilizando un script CopyTable para garantizar la integridad de los datos.
- **Archivo de facturas** : La pestaña Archivo de facturas de facturas presenta un script de botón Copiar detalles de factura, que facilita el archivo de facturas de facturas mediante la creación de una copia duplicada de la factura original, lo que garantiza un registro permanente con fines de auditoría y cumplimiento.

  ![imagen](../../../../03-media/apptio-costing-standard/resources/images/be/be-rn-1.jpg)

  ![imagen](../../../../03-media/apptio-costing-standard/resources/images/be/be-rn-2.jpg)

**Corregido en esta versión**

- Borrado permanente de datos de una tabla en el canal de datos.
- Se han solucionado problemas de vulnerabilidad.
- Optimización de los cálculos de precisión

## Cliente 2.11 - 17 de enero de 2025

**Dependencia**

\*Cliente v2.11 es compatible con Servidor 12.11.11 y 12.11.10.x

\*Algunas funciones de Client v2.11 dependen de las nuevas funciones de Server 12.11.11.

**Nuevas funciones para clientes**

**La función de carga de tablas es ahora GA**

El componente de carga de tablas se lanzó hace dos años y la visibilidad en la cinta de Studio se controlaba mediante la función Activar funciones. Su traslado a GA no afectará a ningún proyecto existente.

**Mejoras en la distribución de correo electrónico**

- **Suscripciones a vistas filtradas** : Esta función permite a los usuarios compartir informes filtrados con destinatarios específicos a través de un sistema de suscripción. Los destinatarios recibirán un hiperenlace para acceder al informe con selecciones de corte preaplicadas, lo que les permitirá ver el informe con la configuración de filtro deseada. Además, los destinatarios tienen la opción de recibir un documento PDF adjunto, que puede configurarse para incluir o excluir la vista simple vinculada manteniendo la configuración de filtro seleccionada. Esta función ofrece una forma flexible y segura de compartir informes con otras personas, garantizando que los destinatarios reciban la información que necesitan en un formato fácil de consumir.

  ![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/fv.jpg)

  Para obtener más información, consulte [Suscripciones de correo electrónico con vista filtrada](reports/email-subscription.html).
- **Suscripción duplicada** : Esta función permite a los usuarios crear una copia de una suscripción de correo electrónico existente y simplifica el proceso de gestión de suscripciones. Para implementar esta función, se ha añadido un nuevo icono "Duplicar suscripción" al cuadro de diálogo Gestionar suscripción, que permite a los usuarios crear una copia de una suscripción existente. La suscripción duplicada se denomina automáticamente con el prefijo "Copia de" seguido del nombre de la suscripción original, y los usuarios pueden editar los detalles de la suscripción duplicada, incluidos el nombre, la frecuencia y la plantilla de correo electrónico adjunta.

  ![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/dupsub.jpg)

  Para obtener más información, consulte [Suscripciones de correo electrónico duplicadas](reports/email-subscription.html).

**Barra de desplazamiento horizontal para las pestañas abiertas de documentos de Studio**

Para mejorar la gestión de las múltiples pestañas inferiores abiertas en el estudio, se ha introducido una barra de desplazamiento horizontal. Permite a los usuarios navegar fácilmente por varias pestañas abiertas. Además, la última pestaña abierta se resaltará, proporcionando un claro indicador visual de la pestaña actual en foco.

![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/scroll.jpg)

Antes, las pestañas desaparecían si no había espacio, por lo que resultaba tedioso volver a abrirlas.

**Tablas editables**

- **Crear sucursal tiene la opción de autocomprobar todas las tablas editables** : Se ha introducido una nueva función para mejorar la gestión de las tablas editables en las sucursales. Esta mejora proporciona un flujo de trabajo más ágil y eficaz para gestionar los cambios de esquema y datos en las ramas y ayuda a evitar cambios involuntarios en el tronco.

  Al crear una rama, el usuario puede ahora seleccionar la opción de comprobar automáticamente todas las tablas editables, lo que las actualizará en el espacio de trabajo de desarrollo. No es necesario comprobar manualmente las tablas individuales, lo que reduce el riesgo de incoherencias y errores en los datos. El proceso de salida está ahora automatizado, lo que garantiza que todas las tablas editables se actualizan correctamente en la sucursal.

  Antes, cuando los datos se actualizaban en una rama, se actualizaban automáticamente en el tronco. No había ningún control para validar o confirmar los cambios en una rama. Para obtener más información, consulte [Crear sucursal con la opción de pago automático](admin/bp-branching-projects.html "Se aplica a: TBM Studio 12.1 y posteriores").
- **Exponer nombre de usuario y fecha de edición del historial de cambios** : El proceso de configuración de la solución de tabla editable se mejora al exponer dos nuevas columnas de informes: columnas de sistema.Nombre de usuario y.Fecha de edición. Ahora los administradores pueden acceder fácilmente a estas columnas en el Explorador de proyectos cuando se abre una tabla editable y arrastrarlas al panel de configuración ad hoc para un componente de informe de tabla editable. Además, estas columnas son ahora visibles en el modo de vista del informe, lo que permite a los usuarios ordenarlas y redimensionarlas según sea necesario. Esta actualización elimina la necesidad de crear columnas independientes y utilizar ApptioScript para rellenar la información, lo que agiliza el proceso de configuración y mejora la experiencia general del usuario.

  ![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/sh-1.jpg)

  ![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/sh-2.jpg)

  ![imagen](../../../../03-media/apptio-costing-standard/resources/images/studio_images/r-notes/sh-3.jpg)

  Anteriormente, estas dos columnas sólo estaban disponibles en Mostrar cambios. Para evitar confusiones, los nombres de las columnas de la tabla Mostrar cambios se han renombrado a Nombre de usuario y EditDate.

  Para saber más, consulte [Mostrar/ocultar.Username y .EditDate](reports/tables/component-config-panel.html "Se aplica a: TBM Studio 12.0 y posteriores").
- **Mejora del rendimiento de guardado/actualización masiva** : se ha realizado una mejora significativa del rendimiento en la funcionalidad de guardado y carga masiva, lo que da como resultado un procesamiento más rápido y eficiente de grandes conjuntos de datos.

  | Número de filas actualizadas | Número de columnas actualizadas | Tiempo antiguo (en segundos) | Nuevo tiempo (en segundos) |
  | --- | --- | --- | --- |
  | 10.000 | 3 | 179 | 2 |
  | 20,000 | 3 | 578 | 4 |
  | 30 000 | 3 | 1189 | 7 |
  | 1 lakh | 1 | tiempo espera | 47 |
  | 2 lakhs | 5 | tiempo espera | 110 |

**Corregido en esta versión**

- Se ha solucionado el problema de los menús desplegables que no respetaban la seguridad de nivel de fila para la tabla estándar.
- Se ha solucionado el problema del tamaño automático de la tabla que no funcionaba correctamente con la opción Árbol.
- Se ha solucionado el problema de las pseudotraducciones de cadenas que faltaban.
