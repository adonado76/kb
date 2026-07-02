---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Conéctese a Apptio Costing"
breadcrumb:
  - "Planning"
  - "Integraciones"
source_path: "it-planning/planning/adm/adm_capabilities.html"
images:
  - "resources/images/it_planning_images/int-comp.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Conéctese a Apptio Costing

Apptio La planificación se integra con Apptio el cálculo de costes mediante el sistema automatizado Data Management (ADM). ADM es un servicio de plataforma compartida diseñado para proporcionar una experiencia de intercambio de datos unificada, segura y escalable entre Apptio aplicaciones.

Esta integración permite a los clientes Apptio de Planning importar datos desde Apptio Costing y publicar planes de nuevo en Costing para la elaboración de informes y análisis.

## ¿Qué es la gestión automatizada Data Management (ADM)?

Automatizado Data Management (ADM) es Apptio el marco de integración de datos estandarizado de que:

- Admite intercambios de datos automatizados y repetibles entre Apptio productos
- Gestiona conjuntos de datos, entidades y programas de integración de forma centralizada
- Garantiza la coherencia de los identificadores y las asignaciones entre la planificación y el cálculo de costes
- Reduce el esfuerzo manual y mejora la fiabilidad de los datos

Más información: [Automatizado Data Management](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=automated-data-management "(se abre en una pestaña o una ventana nueva)").

## Integraciones de cálculo de costes Apptio compatibles

Mediante ADM, Apptio Planificación admite las siguientes integraciones con Apptio Cálculo del coste:

**Importar desde Apptio Cálculo de costes a Apptio Planificación**

- **Datos de referencia**

  Importe las dimensiones de los datos de referencia desde Apptio Costing para garantizar la coherencia de los maestros en todas las aplicaciones.

  Más información: [*Importar datos de referencia desde Apptio Costing*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-import-reference-data-from-apptio "(se abre en una pestaña o una ventana nueva)")
- **Datos reales**

  Importar datos de gastos reales desde Apptio Costing para respaldar las previsiones y el análisis de variaciones.

  Más información: [*Importar datos reales desde el cálculo de costes de Apptio*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-import-actuals-from-apptio "(se abre en una pestaña o una ventana nueva)")
- **Planes de referencia**

  Cree planes basados en datos Apptio de costes para acelerar la configuración del plan y garantizar la alineación con las finanzas actuales.

  Más información: [*Importar planes de referencia desde Apptio Costing*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-import-baseline-plans-from-apptio "(se abre en una pestaña o una ventana nueva)")
- **Datos del listado de proyectos**

  Importar la lista de proyectos a nivel de plan desde el cálculo de costes de Apptio.

  Más información: [*Importar lista de proyectos desde Apptio Costing*](../import-pl-acost.dita "(se abre en una pestaña o una ventana nueva)")

**Publicar desde Apptio Planificación a Apptio Cálculo de costes**

- **Publicar datos del plan**

  Transfiera los datos del presupuesto o del plan de previsión desde Apptio Planificación a Apptio Cálculo de costes.

  Más información: [*Publicar datos del plan en el cálculo de costes de Apptio*](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-publish-plan-data-apptio "(se abre en una pestaña o una ventana nueva)")
- **Calendario Plan Publica**

  Automatice la publicación periódica de planes según un calendario definido para mantener Apptio los costes continuamente alineados con las actualizaciones de planificación.

  Más información: [*El plan de programación se publica en Apptio Costing.*](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-schedule-plan-publishes "(se abre en una pestaña o una ventana nueva)")
- **Datos del listado de proyectos**

  Transfiera la lista de proyectos a nivel de plan desde la planificación de Apptio a la determinación de costes de Apptio.

  Más información: [*Publicar proyectos Lista de costes de Apptio*](../pub-pl-ac.dita "(se abre en una pestaña o una ventana nueva)")

## Entidades automatizadas de « Data Management »

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre de entidad** | **Producción de aplicaciones** | **Consumo de aplicaciones** | **Descripción** |
| Publicar presupuesto financiero | Apptio Planificación | Apptio Cálculo de costes | Publica partidas financieras para planes de tipo presupuestario |
| Publicar previsión financiera | Apptio Planificación | Apptio Cálculo de costes | Publica partidas financieras para planes de tipo previsional |
| **Publicar presupuesto de activos** | Apptio Planificación | Apptio Cálculo de costes | Publica partidas de activos para planes de tipo presupuestario |
| Publicar previsión de activos | Apptio Planificación | Apptio Cálculo de costes | Publica partidas de activos para planes de tipo previsión |
| Publicar presupuesto del contrato | Apptio Planificación | Apptio Cálculo de costes | Publica partidas contractuales para planes de tipo presupuestario |
| Publicar previsión de contrato | Apptio Planificación | Apptio Cálculo de costes | Publica partidas de contrato para planes de tipo previsión |
| Publicar presupuesto laboral | Apptio Planificación | Apptio Cálculo de costes | Publica partidas de mano de obra para planes de tipo presupuestario |
| Publicar previsión laboral | Apptio Planificación | Apptio Cálculo de costes | Publica partidas de mano de obra para planes de tipo previsión |
| Publicar presupuesto de actividades laborales | Apptio Planificación | Apptio Cálculo de costes | Publica partidas de actividad laboral para planes de tipo presupuestario |
| Publicar previsión de actividad laboral | Apptio Planificación | Apptio Cálculo de costes | Publica partidas de actividad laboral para planes de tipo previsión |
| Publicar lista de proyectos | Apptio Planificación | Apptio Cálculo de costes | Publica la lista de proyectos a nivel de plan |
| Datos reales | Apptio Cálculo de costes | Apptio Planificación | Importa datos financieros reales desde el cálculo de costes a la gestión de gastos de planificación |
| Plan de importación financiera | Apptio Cálculo de costes | Apptio Planificación | Importa partidas financieras |
| Importar plan de activos | Apptio Cálculo de costes | Apptio Planificación | Importa partidas de activos |
| Contrato de plan de importación | Apptio Cálculo de costes | Apptio Planificación | Líneas de contrato de importaciones |
| Importar plan de mano de obra | Apptio Cálculo de costes | Apptio Planificación | Importa partidas de mano de obra |
| Importar plan de actividades laborales | Apptio Cálculo de costes | Apptio Planificación | Importa partidas de actividad laboral |
| Importar lista de proyectos del plan | Apptio Cálculo de costes | Apptio Planificación | Plan de importaciones Lista de proyectos |
| Cuenta | Apptio Cálculo de costes | Apptio Planificación | Datos de referencia de la cuenta de importaciones |
| Categoría de cuenta | Apptio Cálculo de costes | Apptio Planificación | Datos de referencia de la categoría de cuenta de importaciones |
| Departamento | Apptio Cálculo de costes | Apptio Planificación | Datos de referencia del departamento de importaciones |
| Centro de costes | Apptio Cálculo de costes | Apptio Planificación | Datos de referencia del centro de costes de importaciones |
| Proveedor | Apptio Cálculo de costes | Apptio Planificación | Importaciones Datos de referencia del proveedor |
| Ubicación | Apptio Cálculo de costes | Apptio Planificación | Importa datos de referencia de ubicación |
| Rol | Apptio Cálculo de costes | Apptio Planificación | Importa datos de referencia de roles |
| Tarifas laborales | Apptio Cálculo de costes | Apptio Planificación | Importa datos de referencia sobre tarifas laborales |
| Reglas de asignación de mano de obra | Apptio Cálculo de costes | Apptio Planificación | Importa datos de referencia de las reglas de asignación de mano de obra |
| Valores predeterminados de clase de activos | Apptio Cálculo de costes | Apptio Planificación | Importa datos de referencia de clases de activos |
| Valores predeterminados del tipo de contrato | Apptio Cálculo de costes | Apptio Planificación | Datos de referencia del tipo de contrato de importaciones |
| Controlador de varianza | Apptio Cálculo de costes | Apptio Planificación | Datos de referencia del controlador de variación de importaciones |
| Grupo de proyecto | Apptio Cálculo de costes | Apptio Planificación | Importa datos de referencia del grupo de proyectos |
| Proyecto | Apptio Cálculo de costes | Apptio Planificación | Importa datos de referencia del proyecto |
| Función laboral del proyecto | Apptio Cálculo de costes | Apptio Planificación | Importa datos de referencia sobre funciones laborales del proyecto |
| Tipo de actividad laboral | Apptio Cálculo de costes | Apptio Planificación | Importa datos de referencia del tipo de actividad laboral |

## Descripción general de la configuración

Antes de utilizar las integraciones, es necesario configurar ADM para su entorno. La configuración suele incluir:

1. **Habilitar automatización Data Management**
   1. Confirme que Automated Data Management (ADM) está aprovisionado para su entorno. Puede verificarlo comprobando que ADM aparece como una aplicación en Frontdoor.
   2. En Apptio Planificación, ve a **Configuración (icono de engranaje) → Perfil de la empresa** y selecciona **Habilitar integración Data Management automatizada**.
2. **Configurar los ajustes de exportación**

   Configure **los ajustes de exportación** para definir el comportamiento predeterminado de exportación para todos los conjuntos de datos del plan.

   1. En la planificación de « Apptio », vaya a **«Configuración» (icono de engranaje) → « Apptio » → «Integración de costes» → «Configuración de exportación».**
   2. Configure los ajustes y guarde las configuraciones.
      - **Diseño de exportación:** elija entre publicar el esquema completo (Exportar todo) o un formato reimportable.
      - **Filtros de datos confidenciales:** habilita o deshabilita el filtrado de datos confidenciales laborales y financieros durante la publicación.
      - **Formato de exportación:** La opción de publicar los meses como filas o columnas se ha trasladado de la sección Configurar a esta nueva configuración de Ajustes de exportación.
      - **Configuración de moneda:** publicar utilizando la moneda predeterminada de la organización o en la moneda original.
      - **Precisión decimal:** La precisión decimal se establece de forma predeterminada según la configuración de la organización definida en el perfil de la empresa. Puede seleccionar una precisión decimal y un icono decimal (punto o coma) diferentes para exportar datos a un Apptio Costing.
      - **Formato de fecha:** Configure el formato de fecha utilizado al publicar en Costing.
3. **Configurar conjuntos de datos de integración en Apptio Cálculo de costes**
   1. Instale los componentes de Apptio integración de costes en función de las capacidades de planificación que desee habilitar.
   2. Componentes de integración disponibles:
      1. **Integración de la planificación**

         Instala los conjuntos de datos de referencia básicos, datos reales, presupuesto y previsiones necesarios para Apptio la planificación.
      2. **Planificación de la integración del proyecto**

         Instala conjuntos de datos adicionales necesarios para la planificación de proyectos y actividades laborales en Apptio Planificación.

   ![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/int-comp.png)

## Conjuntos de datos instalados por el componente de integración de planificación

|  |  |  |  |
| --- | --- | --- | --- |
| **Categoría** | **Conjunto de datos** | **Grupo de mesas** | **Descripción** |
| Cuenta y estructura financiera | Cuenta maestra de planificación | Datos de referencia de planificación de Z\_Apptio | Lista maestra de cuentas financieras utilizadas para la planificación, incluidos los atributos de cuenta requeridos por Apptio Planning. |
| Planificación de la categoría de cuenta maestra | Datos de referencia de planificación de Z\_Apptio | Define categorías financieras de alto nivel utilizadas para agrupar y analizar cuentas en Planning. |
| Planificación de la jerarquía de cuentas | Datos de referencia de planificación de Z\_Apptio | Estructura jerárquica que organiza las cuentas en relaciones padre/hijo para la consolidación y la generación de informes. |
| Nivel de planificación de cuentas 1-5 | Datos de referencia de planificación de Z\_Apptio | Vistas planas de la jerarquía de cuentas en cada nivel para facilitar las integraciones y la generación de informes. |
| Centros de coste y departamentos | Planificación del centro de costes maestro | Datos de referencia de planificación de Z\_Apptio | Lista autorizada de centros de coste disponibles para la elaboración de presupuestos y previsiones. |
| Planificación de la jerarquía de centros de coste | Datos de referencia de planificación de Z\_Apptio | Estructura jerárquica que organiza los centros de coste en relaciones padre/hijo para la consolidación y la elaboración de informes. |
| Planificación del centro de costes Nivel 1-5 | Datos de referencia de planificación de Z\_Apptio | Vistas planas de la jerarquía de centros de coste en cada nivel para facilitar las integraciones y la generación de informes. |
| Departamento de Planificación Maestro | Datos de referencia de planificación de Z\_Apptio | Conjunto de datos maestro que define los departamentos utilizados en Apptio la planificación. |
| Jerarquía del Departamento de Planificación | Datos de referencia de planificación de Z\_Apptio | Estructura jerárquica que organiza los departamentos en relaciones padre/hijo para la consolidación y la presentación de informes. |
| Departamento de Planificación Nivel 1-5 | Datos de referencia de planificación de Z\_Apptio | Vistas planas de la jerarquía del departamento en cada nivel para facilitar las integraciones y la generación de informes. |
| Datos reales | Planificación Real Maestro | Datos de planificación de Z\_Apptio | Conjunto de datos maestros de las finanzas reales utilizadas por Apptio Planificación. El conjunto de datos «Planificación real» se asigna a esta tabla para el consumo de planificación. |
| Planificación Real | Datos de planificación de Z\_Apptio | Conjunto de datos transformados derivados de los datos maestros de fuentes de costes, filtrados para incluir solo datos reales para su importación a Apptio Planning. |
| Planes financieros | Presupuesto de planificación | Datos de planificación de Z\_Apptio | Partidas financieras presupuestadas publicadas desde Apptio Planificación. |
| Previsión de planificación | Datos de planificación de Z\_Apptio | Partidas financieras previstas publicadas desde Apptio Planificación. |
| Planes de activos | Presupuesto de planificación de activos | Datos de planificación de Z\_Apptio | Partidas financieras de activos publicadas desde Planes Apptio presupuestarios de planificación. |
| Previsión de activos de planificación | Datos de planificación de Z\_Apptio | Partidas financieras de activos publicadas a partir de los planes Apptio de previsión de planificación. |
| Planificación de la clase de activos maestra | Datos de referencia de planificación de Z\_Apptio | Datos de referencia que definen las clases de activos y el comportamiento de capitalización utilizados en la planificación. |
| Planes contractuales | Presupuesto del contrato de planificación | Datos de planificación de Z\_Apptio | Partidas presupuestadas del contrato publicadas desde Apptio Planificación. |
| Previsión del contrato de planificación | Datos de planificación de Z\_Apptio | Partidas de contrato previstas publicadas desde Apptio Planificación. |
| Planificación del tipo de contrato maestro | Datos de referencia de planificación de Z\_Apptio | Datos de referencia que definen los tipos de contrato utilizados en la planificación. |
| Planes laborales | Planificación del presupuesto laboral | Datos de planificación de Z\_Apptio | Partidas presupuestarias de mano de obra publicadas desde Apptio Planificación. |
| Planificación de la previsión de mano de obra | Datos de planificación de Z\_Apptio | Partidas de mano de obra previstas publicadas desde Apptio Planificación. |
| Planificación de las tarifas laborales | Datos de referencia de planificación de Z\_Apptio |  |
| Planificación del rol laboral maestro | Datos de referencia de planificación de Z\_Apptio | Definiciones de tarifas de mano de obra por función, ubicación o proveedor utilizadas para calcular los costes de mano de obra en Apptio Planificación. |
| Datos de referencia | Planificación Ubicación Maestro | Datos de referencia de planificación de Z\_Apptio | Datos de referencia de ubicación utilizados para las tarifas de mano de obra, la elaboración de informes y el análisis en Apptio Planificación. |
| Planificación de tipos impositivos del IVA | Datos de referencia de planificación de Z\_Apptio | Conjunto de datos de referencia que define los tipos del IVA utilizados para calcular las partidas de contrato con impuestos incluidos en Apptio Planificación. |
| Factores que influyen en la variación de la planificación | Datos de referencia de planificación de Z\_Apptio | Conjunto de datos de referencia que define las categorías de varianza utilizadas en el análisis de varianza y comentarios en Apptio Planificación. |
| Planificación del maestro de proveedores | Datos de referencia de planificación de Z\_Apptio | Lista maestra de proveedores utilizados en Apptio Planificación. |

## Conjuntos de datos instalados por el componente de integración de proyectos de planificación

|  |  |  |  |
| --- | --- | --- | --- |
| **Categoría** | **Conjunto de datos** | **Grupo de mesas** | **Descripción** |
| Proyectos | Planificación del proyecto maestro | Datos de referencia de planificación de Z\_Apptio | Lista maestra de proyectos disponibles para la planificación de proyectos e inversiones en Apptio Planificación. |
| Grupo de planificación del proyecto Master | Datos de referencia de planificación de Z\_Apptio | Agrupación jerárquica de proyectos utilizada para la gestión de carteras y la elaboración de informes. |
| Actividad laboral | Planificación del proyecto: Maestro de funciones laborales | Datos de referencia de planificación de Z\_Apptio | Funciones laborales específicas del proyecto y tarifas asociadas utilizadas para la actividad laboral del proyecto en Apptio Planificación. |
| Planificación del tipo de actividad laboral maestro | Datos de referencia de planificación de Z\_Apptio | Define los tipos de actividad laboral y las asignaciones para la contabilidad de cargos y cargos cruzados en Apptio Planificación. |
| Planes del proyecto | Planificación del presupuesto para actividades laborales | Datos de planificación de Z\_Apptio | Partidas de actividad laboral presupuestadas publicadas desde Apptio Planificación. |
| Planificación de la previsión de la actividad laboral | Datos de planificación de Z\_Apptio | Elementos de actividad laboral previstos publicados desde Apptio Planificación. |
| Integración de Targetprocess | Actividad laboral de Targetprocess: datos reales | Datos de planificación de Z\_Apptio | Actividad laboral real del proyecto importada desde Targetprocess. |
| Plan de actividades laborales de Targetprocess | Datos de planificación de Z\_Apptio | Actividad laboral planificada del proyecto obtenida de Targetprocess para compararla y alinearla con la planificación. |

## Mejores prácticas para Data Management

El enfoque recomendado es importar y publicar conjuntos de datos maestros desde Apptio Costing, en lugar de sobrescribir o integrar directamente los archivos de datos fuente sin procesar.

Las fuentes de datos sin procesar deben transformarse, normalizarse y asignarse primero en Apptio Costing a conjuntos de datos maestros estandarizados. Estos conjuntos de datos maestros representan datos financieros depurados, categorizados y alineados con el negocio, y están diseñados para ser reutilizados de forma coherente en todas Apptio las aplicaciones, incluida Apptio Planning.

Aunque puede crear sus propias tablas de integración personalizadas en lugar de utilizar los conjuntos de datos listos para usar (OOTB), tenga en cuenta que mantiene Apptio y mejora continuamente los esquemas OOTB. Cuando se publiquen actualizaciones del modelo de datos o del esquema, Apptio actualizará los conjuntos de datos y los componentes de integración OOTB, y usted podrá actualizar esos componentes para aprovechar automáticamente las últimas mejoras y correcciones. Las tablas personalizadas, por el contrario, deben mantenerse y actualizarse manualmente.

- **[Importar datos de referencia desde](../../../it-planning/planning/adm/adm_import_reference_data.html)** Datos de   
   referencia Apptio de costes en Apptio Planificación define las dimensiones principales utilizadas para la planificación, la previsión y la elaboración de informes, tales como cuentas, centros de costes, departamentos, proveedores, proyectos y funciones laborales. Con la gestión automatizada de datos Data Management (ADM), puede importar datos de referencia fiables y controlados directamente desde Apptio Costing para garantizar la coherencia en todos los flujos de trabajo financieros.
- **[Importar datos reales desde Apptio Costing](../../../it-planning/planning/adm/adm_import_actuals.html)**  
   La importación de datos reales transfiere los datos históricos de gastos desde Apptio Costing a Apptio Planning, donde se pueden utilizar para realizar previsiones, análisis de variaciones y comparaciones de planes.
- **[Importar planes de referencia desde Apptio Costing](../../../it-planning/planning/adm/adm-import-baseline-data.html)**  
   Esta función le permite importar datos de planes de referencia desde Apptio Costing a Apptio Planning. Esto resulta útil cuando se desea utilizar un conjunto de datos existente de Apptio Costing como punto de partida para la elaboración de presupuestos o previsiones.
- **[Importar lista de proyectos desde Apptio Costing](../../../it-planning/planning/import-pl-acost.html)**
- **[Publicar datos del plan en Apptio Cálculo de costes](../../../it-planning/planning/adm/adm_publish_import_plan_data.html)**  
   La publicación de datos del plan desde Apptio Planificación a Apptio Cálculo de costes le permite compartir datos definitivos del presupuesto y las previsiones con su entorno de asignación y transparencia de costes. Gracias a las funciones integradas de integración y programación de Automated Data Management (ADM), puede exportar partidas financieras (finanzas, mano de obra, actividad laboral, contratos, activos) desde Planning e introducirlas directamente en Apptio Costing.
- **[Publicar la lista de proyectos en Apptio Costing](../../../it-planning/planning/pub-pl-ac.html)**
- **[Estado de la integración](../../../it-planning/planning/adm/adm-status.html)**  
   La página Estado de la integración proporciona visibilidad sobre el progreso de los intercambios de datos entre Apptio Planificación y Apptio Cálculo de costes mediante Data Management (ADM). Esta vista ayuda a los administradores a supervisar las importaciones, las publicaciones y a resolver problemas de integración.
- **[Integración de Transparencia de Costes (Legacy)](../../../it-planning/planning/integrate-ct.html)**  
   Si su organización ejecuta tanto Apptio Costing Standard como una aplicación Apptio Planning , puede integrarlas para compartir datos.
- **[Conéctate a Cloudability Financial Planning](../../../it-planning/planning/connect-cfp.html)**
- **[Gestionar gastos en la nube (sin integración CFP)](../../../it-planning/planning/manage-cfp-wo-int.html)**  
   La pestaña **Nube** de la vista **Gastos** se puede utilizar de forma independiente sin la integración CFP para gestionar y realizar un seguimiento del gasto en la nube dentro de los presupuestos y las previsiones.
- **[Configurar y gestionar la integración de Cloud Financial Planning](../../../it-planning/planning/cfp-integration.html)** La configuración  
   de la integración de Cloud Financial Planning (CFP) se configura **por plan** dentro de la configuración del plan. Estos ajustes establecen la conexión entre la planificación de Apptio y el **plan CFP** específico y **la vista de propiedad de costes**, y definen cómo las dimensiones de planificación (departamento, centro de costes, cuenta, etc.) Mapa de las estructuras de propiedad de costes de CFP.
