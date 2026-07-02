---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Publicaciones recientes"
breadcrumb:
  - "TBM Studio"
  - "Notas del release"
source_path: "studio/whats-new.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Publicaciones recientes

## Servidor 12.11.22 - 29 de mayo de 2026

- Esta versión incluye varias mejoras en el Nuevo Report Studio, entre las que se encuentran:
  - [Motor de temas](report-studio/theme-engine.html) para un aspecto de los informes más personalizable y uniforme
  - Compatibilidad con la incorporación de descripciones a las fórmulas personalizadas para mejorar la legibilidad y facilitar el mantenimiento
  - Funcionalidad de exportación a Excel para las visualizaciones de tablas en el Diseñador de informes
  - Tablas editables mejoradas con límites de filas configurables
  - Compatibilidad con la visualización de datos formateados en tablas editables
  - Compatibilidad con «Añadir al filtro» para fórmulas personalizadas en tablas editables
  - Compatibilidad con el filtrado de valores nulos en los gráficos para ofrecer una mayor flexibilidad en el análisis de datos
  - Una nueva opción para desactivar las interacciones de desglose a través de la configuración del Panel de datos
- Se ha añadido la posibilidad de ejecutar programaciones [de publicación periódicas](formulas-and-functions/functions/ApptioScript-function.html "Aplicable a: TBM Studio 12.11.22 y versiones posteriores") para tablas editables mediante ApptioScript.
- **Norma de cálculo de costes (plantillas v120 )**
  - [El TCO de Data Center](/docs/SSI71A/cost-transparency/infra-use-cases/dc-overview.html) ya está disponible para los clientes que dispongan de una licencia de Costing Standard de IBM Apptio. Este paquete de soluciones ayuda a las organizaciones a analizar el coste total de explotación de las instalaciones de los centros de datos, evaluar la capacidad y la utilización en materia de energía, refrigeración, espacio y racks, y comparar las distintas sedes utilizando indicadores económicos unitarios, como el coste por kilovatio, el coste por rack y el coste por metro cuadrado. Además, ayuda a asignar los costes del centro de datos a la infraestructura, las aplicaciones y las soluciones a las que dan soporte, lo que mejora la visibilidad de los factores que influyen en los costes, las limitaciones de capacidad y las decisiones de inversión. [Enlace](https://www.youtube.com/watch?v=RT6brXfajcc "(se abre en una pestaña o una ventana nueva)") al vídeo con los momentos destacados
  - Mejoras [en el coste total de propiedad (TCO) de los mainframes](/docs/SSI71A/cost-transparency/infra-use-cases/mf-overview.html) :
    - Se ha actualizado la pestaña «Grupo de costes» para comprender la composición de los costes, realizar un seguimiento de las tendencias, comparar con los valores de referencia y examinar los detalles interanuales en una única vista coherente.
    - Se ha añadido un nuevo caso de uso de almacenamiento de mainframe para ofrecer visibilidad sobre los costes, el consumo y la asignación del almacenamiento de mainframe, como parte del análisis global del coste total de propiedad (TCO) del mainframe.
  - [Los informes predefinidos](report-studio/ootb-report-pp.html "Este documento describe los pasos necesarios para habilitar los informes OOTB modernizados (Nueva experiencia (NX)) en una instancia de cliente. Estos informes ofrecen una mayor claridad, una mejor comprensión y una experiencia más intuitiva, al tiempo que siguen utilizando los mismos conjuntos de datos que Classic TBM Studio.") basados en el nuevo Report Studio ya están disponibles en su versión general (GA) para los componentes de Finanzas, Proveedores, Aplicaciones, Mano de obra, Costo total de propiedad (TCO) de la nube pública, Costo total de propiedad (TCO) del mainframe, Costo total de propiedad (TCO) de la IA y Servicios.
  - Los informes predeterminados de Costing Standard Legacy ya están disponibles en polaco

**Se ha corregido en esta versión**

- Se han corregido vulnerabilidades de seguridad

## Cliente: 2.22 - 29 de mayo de 2026

- Se ha añadido la posibilidad de ejecutar programaciones [de publicación periódicas](formulas-and-functions/functions/ApptioScript-function.html "Aplicable a: TBM Studio 12.11.22 y versiones posteriores") para tablas editables mediante ApptioScript.
- El resto de funciones requieren actualizar a la versión para servidor 12.11.22. Consulte las actualizaciones del servidor.

## Servidor 12.11.21.1 - 8 de mayo de 2026

- Actualización trimestral de Java.

## Cliente: 2.21.1 - 8 de mayo de 2026

- Actualización trimestral de Java.

## Studio UI 1.21.2 - 8 de mayo de 2026

**La versión « 1.21.2 » ya está disponible para el público general**

Esta versión incluye una serie de pequeñas mejoras en las funciones y en los detalles de acabado, centradas en la usabilidad y la experiencia general del producto del **Nuevo Report Studio.**

- Correcciones en el relleno de la interfaz de usuario para mejorar la coherencia visual
- Mejoras generales en el acabado y la presentación de toda la experiencia de New Report Studio

## Studio UI 1.21.1 - 17 de abril de 2026

En el nuevo Report Studio de IBM Apptio se han introducido las siguientes mejoras:

- Se han corregido las infracciones de accesibilidad para mejorar el cumplimiento normativo.
- Se ha añadido un indicador de «Activo/Inactivo» para los informes. El motor de cálculo ahora excluye los informes inactivos.
- Mejora en la visualización de las descripciones emergentes de varias líneas para facilitar la lectura.
- Se han solucionado los problemas de localización al japonés
- Se ha añadido una separación clara de los informes heredados en el panel de registro.

## Servidor 12.11.21 - 10 de abril de 2026

- El nuevo [Report Studio](report-studio/getting-started/intro.html "El nuevo Report Studio de IBM Apptio, diseñado con Carbon, ofrece una experiencia de generación de informes modernizada, intuitiva y más potente. Está diseñado para ayudar a los administradores de TBM y a los usuarios empresariales a crear informes más rápidamente, con menos complejidad y una curva de aprendizaje más corta. En comparación con el Classic Report Studio, esta versión ofrece:") de IBM Apptio ya está disponible de forma general, y ofrece una experiencia moderna para crear, personalizar y consultar informes, lo que permite una adopción integral en los flujos de trabajo de creación, migración y uso compartido. Con el nuevo estudio de informes, puedes
  - Crear informes desde cero
  - Consulte los informes estándar predefinidos y aprenda de ellos
  - Editar y personalizar informes
  - Consultar y compartir informes
- En esta versión, las nuevas mejoras de IBM Apportion Report Studio incluyen: un componente de botón para acciones, reglas de visibilidad de pestañas, ejes compartidos en gráficos superpuestos, ajuste automático de texto en tablas, vistas guardadas, envío por correo electrónico desde el visor de informes y un [asistente de migración](report-studio/migration-assistant.html) para trasladar informes desde el TBM Studio clásico.
- Se ha incorporado una nueva función de autoservicio en Automated Data Management (ADM) para permitir la integración entre Cloudability y Costing, sustituyendo al conector existente de Cloudability DataLink. Tu gestor de cuentas te proporcionará más detalles e instrucciones sobre la migración.
- IBM Se ha actualizado la documentación de ayuda de TBM Studio, Billing y Benchmarking.
- Norma de cálculo de costes (plantillas v120 )
  - Se ha introducido un nuevo tipo de proyecto independiente para el TCO de mainframe, lo que permite realizar un análisis y una gestión específicos de los costes de mainframe.
  - Ya están disponibles [los informes predefinidos modernizados](report-studio/ootb-report-pp.html "Este documento describe los pasos necesarios para habilitar los informes OOTB modernizados (Nueva experiencia (NX)) en una instancia de cliente. Estos informes ofrecen una mayor claridad, una mejor comprensión y una experiencia más intuitiva, al tiempo que siguen utilizando los mismos conjuntos de datos que Classic TBM Studio.") basados en el nuevo Report Studio (versión preliminar pública).
  - Ya está disponible una nueva solución, Data Center TCO (versión preliminar pública), que ofrece una visión completa de los costes del centro de datos, la utilización de la capacidad y la asignación de costes.
  - Data Advisor se ha actualizado con las últimas mejoras.

**Se ha corregido en esta versión**

- Se han corregido vulnerabilidades de seguridad

## Cliente: 2.21 - 10 de abril de 2026

- Se ha añadido una casilla de selección en el flujo de trabajo de «Informes no utilizados» para permitir consultar los datos de uso de la administración de socios.
- Se ha actualizado la biblioteca de gráficos; es posible que se observen pequeños cambios visuales en los gráficos.
- Para acceder al resto de funciones, es necesario actualizar a la versión de servidor 12.11.21. Consulte las actualizaciones del servidor.

## Servidor 12.11.20 - 27 de febrero de 2026

- El nuevo [IBM Apptio Report Studio](report-studio/recent-releases.html) ya está disponible para su vista previa pública. Si desea participar y aún no se ha registrado, póngase en contacto con su gestor de éxito del cliente (se requiere un servidor 12.11.19/2.19 +). Las nuevas funciones incluyen
  - Vista en árbol para tablas
  - Exportar informes a PDF
  - Exportar tablas a Excel
  - Compatibilidad con múltiples divisas
- deleteAllrows La funcionalidad de la tabla editable solo eliminará el conjunto de filas filtradas actualmente cuando se apliquen los filtros. Si no se aplican filtros, se eliminarán todas las filas de la tabla editable.
- A partir de la versión 2026 de Q2, la compatibilidad con [la agrupación en dimensiones numéricas](troubleshooting/numeric-grouping-tables-reports.html) quedará totalmente desactivada. Se recomienda a los clientes que identifiquen y resuelvan de forma proactiva cualquier configuración relacionada.
- [Las suscripciones por correo electrónico](reports/email-subscription.html) ahora admiten la seguridad a nivel de fila
- Norma de cálculo de costes (plantillas v120 )
  - **Solución TCO del producto:** Se han añadido desgloses de « App ID » (Desglosar por tipo de gasto), métricas de « CapEx » (Desglosar por tipo de gasto) y «Total Spend» (Gasto total) en [el informe detallado del producto](/docs/SSI71A/cost-transparency/solution-uc/product-reports.html), y métricas presupuestarias en [el informe de la lista de productos](/docs/SSI71A/cost-transparency/solution-uc/product-reports.html#prorep__plist).
  - **Solución TCO para mainframe:** Se ha introducido un [informe](/docs/SSI71A/cost-transparency/infra-use-cases/mf-reports.html#mfrep__mainframe-apps) específico sobre aplicaciones mainframe (que anteriormente formaba parte del TCO para mainframe).
- Fundamentos del cálculo de costes (plantillas v200 )
  - Se han actualizado las asignaciones para asignar primero la mano de obra externa a los proveedores, antes de asignarla a la mano de obra.
  - Se han actualizado los selectores de columnas en el [Análisis laboral](/docs/SSU3U2H/apptio-cost-management/out_of_the_box_reports/labor-review.html#LaborReview__lanalysis).

## Cliente 2.20, 27 de febrero de 2026

- El nuevo [IBM Apptio Report Studio](report-studio/recent-releases.html) ya está disponible para su vista previa pública. Si desea participar y aún no se ha registrado, póngase en contacto con su gestor de éxito del cliente (se requiere un servidor 12.11.19/2.19 +).
- Se han solucionado problemas de vulnerabilidad.
- Todas las nuevas funciones requieren una actualización a la versión del servidor 12.11.20. Consulte las actualizaciones del servidor.

## Servidor 12.11.19.1 - 6 de febrero de 2026

- Actualización trimestral de Java.
- Se ha corregido un problema en el nuevo Diseñador de informes por el que el ID de dimensión de la columna Objeto incluía incorrectamente el nombre de la tabla

## Cliente 2.19.1, 6 de febrero de 2026

- Actualización trimestral de Java.

## Servidor 12.11.19 - 16 de enero de 2026

- El nuevo [IBM Apptio Report Studio](report-studio/prev-releases.html) ya está disponible para su vista previa pública. Si desea participar y aún no se ha registrado, póngase en contacto con su gestor de éxito del cliente. El acceso al nuevo IBM Apptio Report Studio estará habilitado en la versión 12.11.19/ 2.19.
- A partir de la versión 2026 de Q2, la compatibilidad con [la agrupación en dimensiones numéricas](troubleshooting/numeric-grouping-tables-reports.html) quedará totalmente desactivada. Se recomienda a los clientes que identifiquen y resuelvan de forma proactiva cualquier configuración relacionada.
- Norma de cálculo de costes (plantillas v120 )
  - Se ha añadido un nuevo informe de simulacro centrado en la jerarquía de productos.
  - Se ha añadido el coste total de propiedad del producto al proyecto de referencia.
  - El TCO del producto está disponible en japonés.
  - Se ha creado un nuevo componente para TBM: Archivos de referencia de v5.
- Fundamentos del cálculo de costes (plantillas v200 )
  - Se ha creado un nuevo componente para TBM: Archivos de referencia de v5.

## Cliente 2.19, 16 de enero de 2026

- Se han solucionado problemas de vulnerabilidad.
- Todas las nuevas funciones requieren una actualización a la versión del servidor 12.11.19. Consulte las actualizaciones del servidor.
