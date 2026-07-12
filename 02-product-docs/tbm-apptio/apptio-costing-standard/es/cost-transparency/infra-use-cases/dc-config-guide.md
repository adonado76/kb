---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Coste total de propiedad de los centros de datos: guía de configuración"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestructura"
  - "Centros de datos"
source_path: "cost-transparency/infra-use-cases/dc-config-guide.html"
images:
  - "resources/images/ct_images/alternate-allocation-strategy.png"
  - "resources/images/ct_images/assumed-percentage-split.png"
  - "resources/images/ct_images/capacity-nx.png"
  - "resources/images/ct_images/capacity-reports.png"
  - "resources/images/ct_images/capacity-threshold-nx.png"
  - "resources/images/ct_images/capacity-threshold.png"
  - "resources/images/ct_images/cost-model-datacenter-config-guide.png"
  - "resources/images/ct_images/create-new-table.png"
  - "resources/images/ct_images/ct-apps-datacenter.png"
  - "resources/images/ct_images/data-center-enrichment-report.png"
  - "resources/images/ct_images/data-center-tco-components.png"
  - "resources/images/ct_images/datacenter-admin.png"
  - "resources/images/ct_images/datacenter-allocation-method.png"
  - "resources/images/ct_images/datacenter-analysys-nx.png"
  - "resources/images/ct_images/datacenter-enrichment-report-nx.png"
  - "resources/images/ct_images/datacenter-estimate-allocation.png"
  - "resources/images/ct_images/datacenter-feed.png"
  - "resources/images/ct_images/datacenter-review-nx.png"
  - "resources/images/ct_images/datacenter-review-report.png"
  - "resources/images/ct_images/datacenters-analysys-report.png"
  - "resources/images/ct_images/itresource=tower-datacenter.png"
  - "resources/images/ct_images/legacy-allocation-strategy.png"
  - "resources/images/ct_images/lineage-flow-diagram.png"
  - "resources/images/ct_images/mainframe-object.png"
  - "resources/images/ct_images/map-field-datacenter.png"
  - "resources/images/ct_images/project-settings-ribbon-dc-cg.png"
  - "resources/images/ct_images/server-object.png"
  - "resources/images/ct_images/steps-raw-intake-table.png"
  - "resources/images/ct_images/storage-object.png"
  - "resources/images/ct_images/table-upload-method.png"
  - "resources/images/icons/datacenters.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Coste total de propiedad de los centros de datos: guía de configuración

## Resumen

**¿Qué problema estamos resolviendo?**

La solución aborda la creciente complejidad y las presiones de costes asociadas a los centros de datos modernos, entre las que se incluyen el aumento de las cargas de trabajo de IA, la mayor demanda energética y las limitaciones de capacidad. A menudo, las organizaciones carecen de una visión global de los costes, el consumo y las limitaciones de la infraestructura, lo que dificulta la planificación de estrategias de expansión, consolidación o migración. El coste total de propiedad (TCO) del centro de datos ofrece una visión coherente de los costes, la capacidad y las limitaciones del centro de datos, lo que permite tomar decisiones de inversión a largo plazo con conocimiento de causa.

**¿Para quién estamos resolviendo el problema?**

Entre los principales destinatarios se encuentran los responsables de TI, el departamento financiero de TI, los propietarios de centros de datos, los propietarios de infraestructuras, los responsables de aplicaciones, los responsables de productos y los responsables de servicios que necesitan información sobre los costes y la capacidad.

**¿Cómo lo estamos resolviendo?**

IBM Apptio El TCO del centro de datos es un conjunto de contenidos predefinidos diseñado para el estándar de cálculo de costes « IBM » ( Apptio ), que incluye informes, tablas y elementos de modelos de datos para ayudar a las organizaciones a comprender el coste total, la capacidad y las limitaciones operativas de su infraestructura de centros de datos. Ofrece una visión global y coherente de la rentabilidad por unidad y de los recursos de infraestructura —como la energía, la refrigeración, el espacio y la densidad de los racks— para facilitar la toma de decisiones operativas y de inversión más acertadas.

## Casos de uso

1. **Comprenda la estructura de costes de su centro de datos**
   - **Costes totales y economía por unidad:** Obtenga una visión global del gasto por centro y región, con costes unitarios como el de « $/kW, », el de $/rack y el de $/pie cuadrado, para identificar ineficiencias.
   - **Transparencia en los factores que influyen en los costes:** comprueba cómo se desglosan los costes entre los contratos de suministro eléctrico, mano de obra y proveedores para justificar el coste total de propiedad (TCO) y tomar decisiones más acertadas en materia de precios y adquisiciones
2. **Identificar y optimizar la utilización de la capacidad y las limitaciones**
   - **Visibilidad de la utilización de la capacidad y las limitaciones por centro:** Identifique la utilización, las limitaciones y el margen de capacidad por centro para detectar a tiempo el exceso de capacidad y los cuellos de botella, y planificar con antelación.
   - **Visibilidad de los costes de proveedores y contratos:** Comprender cómo los contratos de instalaciones y proveedores influyen en los costes a nivel de centro para permitir una optimización proactiva de los precios, las compras y los contratos.
3. **Mejorar la transparencia del consumo de los centros de datos**

   - **Asignación de costes de computación y almacenamiento:** Asignar los costes del centro de datos a los servidores y al almacenamiento para establecer unos costes unitarios justificados y facilitar los procesos de showback y chargeback.
   - **Visibilidad de los costes de infraestructura, aplicaciones, productos y servicios:** Identifique qué elementos de infraestructura, aplicaciones, productos y servicios están generando gastos en el centro de datos para mejorar la rendición de cuentas en todas las unidades de negocio.

## Requisitos previos

Para la solución de TCO para centros de datos se requieren los siguientes requisitos previos:

- IBM Apptio Norma de cálculo de costes
- Versión del servidor: Versión preliminar pública - 12.11.21, versión general -12.11.22 o posterior
- Versión de los componentes v120

## Instalación de componentes

Nota: Antes de continuar, comprueba que la versión de los componentes de tu proyecto esté configurada en «Versión 120».

Consulte esta guía para obtener más información: [«Instalación de las nuevas soluciones de cálculo de costes de IBM Apptio en proyectos basados en plantillas antiguas».](../configuration/config-instnew.html)

- En la cinta de opciones «Proyecto», haz clic en el botón «**Configuración del proyecto** ».
- Comprueba o configura la versión de los componentes en «Versión 120».

  ![Configuración del proyecto](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/project-settings-ribbon-dc-cg.png)
- Haz clic en el botón «**Guardar** ».

**La solución** de coste total de propiedad (TCO) para centros de datos se implementa a través de dos componentes.

- **Coste total de propiedad (TCO) de los centros de datos:** Este componente instala los conjuntos de datos, las tablas editables, las métricas, la lógica de asignación y las estructuras de datos básicas necesarias para analizar las operaciones de los centros de datos y establecer una economía unitaria fundamentada en todas las ubicaciones e instalaciones. Es necesario instalar este componente antes de instalar cualquiera de los componentes de generación de informes que se indican a continuación.
- **Informes sobre el coste total de propiedad (TCO) de los centros de datos** : instala los informes clásicos para la elaboración de informes y el análisis del coste total de propiedad (TCO) de los centros de datos.
- **Informes de TCO de centros de datos en NX** : instala los informes de NX para la elaboración de informes y el análisis del TCO de los centros de datos.

Los clientes pueden instalar el componente de generación de informes Classic o NX, según sus preferencias en cuanto a la experiencia de generación de informes. No obstante, el componente básico del coste total de propiedad (TCO) de los centros de datos debe instalarse primero en todos los casos.

![Componentes del coste total de propiedad (TCO) de los centros de datos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/data-center-tco-components.png)

## Requisitos de datos

La solución de TCO para centros de datos requiere tres categorías clave de datos para ofrecer información sobre costes, capacidad y asignación:

1. **Datos financieros (a través de IT Resource Towers)**

   Los datos financieros, como los costes de proveedores y de mano de obra, se importan a través de integraciones estándar de Costing y se asignan a las torres de recursos de TI. Los costes deben clasificarse en una subtorre incluida dentro de las Torres de Recursos de TI = Torre del Centro de Datos para que se registren a nivel del centro de datos.
2. **Datos de uso (tabla de datos de centros de datos)**

   Los datos operativos y de capacidad deben introducirse en la tabla «Data Centers Feed» para permitir la elaboración de informes y el análisis de la rentabilidad por unidad. Revisa los datos necesarios.

   [![](../../../../../03-media/apptio-costing-standard/resources/images/icons/datacenters.png)](../../resources/data-center-tco-data-advisor.xlsx "(se abre en una pestaña o una ventana nueva)")

   Esto incluye indicadores obligatorios como:
   - Uso y capacidad del rack (RU)
   - Consumo y capacidad ( kW )

   Entre las métricas opcionales, pero recomendadas, se incluyen:
   - Aprovechamiento y capacidad del espacio (metros cuadrados)
   - Consumo y capacidad de refrigeración

   Estos datos suelen proceder de sistemas de gestión de instalaciones (DCIM), de gestión de edificios (BMS), de gestión de energía ( LogicMonitor, ) o de otros sistemas de instalaciones, y son fundamentales para calcular la utilización, identificar ineficiencias y permitir asignaciones basadas en factores determinantes.

   Utiliza las tablas editables disponibles para ampliar los datos de uso.
3. **Metadatos (para la asignación y el enriquecimiento)**

   Los metadatos enriquecen los informes y respaldan la lógica de asignación. Entre los ámbitos clave se incluyen:

   - Identificadores principales: ID del centro de datos, nombre, región, nivel (obligatorios para la asignación y la presentación de informes)
   - Atributos adicionales: Ubicación, Tipo de instalación (propia, alquilada, coubicación), Centro de costes, Nombre del servicio (también se utiliza como nombre del producto)
   - Contexto operativo: responsable, finalidad, nivel de certificación, estado de la comisión

   Estos datos suelen proceder de la CMDB (por ejemplo, ServiceNow ) y de los sistemas de gestión de instalaciones.

   Utiliza las tablas editables disponibles para completar los metadatos.

## Lógica de asignación

**Torre de recursos de TI → Centro de datos:** los costes asignados a la torre del centro de datos se distribuyen entre los distintos centros de datos mediante una lógica de ponderación predefinida. De forma predeterminada, esto utiliza una combinación de:

- Superficie ocupada del centro de datos
- Porcentaje de asignación de infraestructura

**Centro de datos → Asignación de infraestructura** Los costes del centro de datos se asignan a su vez a componentes de infraestructura como servidores, almacenamiento y mainframe.

Esta asignación suele depender de:

- Alineación de la ubicación
- Factores de consumo basados en el uso, como las horas de servidor, el almacenamiento (GB/TB) o el consumo de mainframe (MIPS/MSU)

Estos métodos de asignación son configurables y pueden adaptarse para reflejar el modelo de consumo más preciso o las normas específicas de su empresa.

**RECORDATORIO:** El coste total de propiedad (TCO) de un centro de datos se centra en los costes de las instalaciones y los costes operativos, entre los que se incluyen:

- Energía y electricidad
- Refrigeración
- Espacio (alquiler, coubicación o instalaciones propias)
- Mantenimiento y operaciones
- Seguridad
- Gastos de personal y otros gastos relacionados con las instalaciones

- **No** incluye los costes de hardware de infraestructura, como servidores, sistemas de almacenamiento y dispositivos de red. Estos activos de infraestructura se incluyen en las secciones posteriores del modelo de costes, tal y como se ilustra en la sección «Arquitectura» del presente documento.

## Arquitectura

Modelo de costes

![Modelo de costes](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/cost-model-datacenter-config-guide.png)

Opciones para la asignación de redes (caso de uso avanzado)

- **Opción 1: Estrategia de asignación tradicional**

  ![Estrategia de asignación de activos heredados](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/legacy-allocation-strategy.png)

  **Aspectos clave a tener en cuenta:**
  - Es más preciso cuando se dispone de datos detallados sobre los dispositivos de red ubicados en cada centro de datos y sobre su consumo de energía, espacio y refrigeración.
  - Mayores requisitos en materia de datos y configuración, ya que se necesitan datos detallados sobre la infraestructura para imputar los costes compartidos del centro de datos a la red.
  - Ideal para entornos consolidados que cuentan con datos detallados sobre activos y su utilización.
- **Opción 2: Estrategia de asignación alternativa**

  ![Estrategia de asignación alternativa](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/alternate-allocation-strategy.png)

  **Aspectos clave a tener en cuenta:**
  - Es más sencillo de implementar, ya que los costes de red se pueden asignar a los centros de datos utilizando un criterio general, como la ubicación.
  - Requisitos de datos reducidos, lo que facilita la configuración cuando no se dispone de datos detallados a nivel de dispositivo.
  - Ofrece una aproximación práctica sin dejar de permitir tratar a Network como una torre independiente.Ideal para entornos consolidados que cuentan con datos detallados sobre activos y su utilización.

Nota:

Para dirigir los flujos de asignación desde la red hacia los centros de datos o desde los centros de datos hacia la red, asegúrese de disponer de los datos necesarios y personalice la asignación.

**Diagrama de flujo de linaje**

![Flujo de linaje](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/lineage-flow-diagram.png)

## Configuración

**Conjuntos de datos** Sigue estos pasos para rellenar la tabla principal «Data Centers Feed»:

1. Accede a **TBM Studio**.
2. Carga los datos sin procesar del centro de datos en una tabla de entrada personalizada. A continuación se muestra el nombre que sugerimos para tu tabla de entrada personalizada (donde los corchetes y el texto entre corchetes se sustituyen por los valores que elijas): Centros de datos de [Nombre del sistema de origen] Sin procesar
3. No recomendamos añadir pasos a las tablas de entrada sin procesar. Lo ideal es que el flujo de trabajo de Steps de cada tabla sin procesar tenga el mismo aspecto que en la captura de pantalla que se muestra a continuación.

   ![Pasos: Tabla de ingesta de alimentos crudos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/steps-raw-intake-table.png)
4. Después de crear una tabla de entrada sin procesar, transforma la tabla haciendo clic con el botón derecho del ratón en el paso «Tabla» y seleccionando **«Crear nueva tabla a partir de este paso».**

   ![Crear una nueva tabla](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/create-new-table.png)
5. Asigna a la nueva tabla el mismo nombre que la tabla de datos sin procesar, pero sin el sufijo «Raw».
6. Abre la tabla transformada y añade un paso «Map Columns» (Asignar columnas), colocándolo justo antes del paso «Table» (Tabla).
7. En el menú desplegable «**Seleccionar destino** », selecciona «**Feed de centros de datos** ».

   ![Noticias sobre centros de datos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-feed.png)
8. Asigna los campos de tu tabla de transformación a los de la tabla «**Data Centers Feed** ».

   ![Campo de mapa](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/map-field-datacenter.png)
9. **Guarda** y confirma los cambios.

**Tablas editables:** esta  
 sección de tablas editables se utiliza para el enriquecimiento opcional de datos. La solución de coste total de propiedad (TCO) del centro de datos funcionará correctamente sin este paso. No obstante, permite incorporar valores adicionales o corregidos cuando sea necesario. La lógica aplicada garantiza que los valores de la tabla editable solo se utilicen cuando los campos correspondientes del conjunto de datos principal estén en blanco, sean incorrectos o estén incompletos, lo que significa que los datos existentes no se sobrescriben.

**Informe de enriquecimiento de centros de datos** Utilice el informe de enriquecimiento de centros de datos (incluido en la colección de informes de Workbench) para mejorar o enriquecer los datos de su centro de datos.

![Informe sobre el desarrollo de los centros de datos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/data-center-enrichment-report.png)

**Informe de administración de centros de datos:** utilice este informe para gestionar los métodos de asignación y las ponderaciones de asignación de los centros de datos en cuestión.

En la pestaña «**Método de asignación** »: seleccione un método cambiando su selección a **«Sí»** entre los dos métodos disponibles para asignar los costes de los centros de datos a los recursos de computación y almacenamiento:

- **Porcentaje de distribución predeterminado** : Selecciona esta opción para aplicar un porcentaje fijo de distribución entre «Compute» y «Storage» en todos los centros de datos. Utiliza esta opción cuando no se disponga de datos de asignación detallados.
- **Método de carga de tablas** : Seleccione esta opción para asignar los costes basándose en datos detallados (por ejemplo, el consumo eléctrico). Esto permite la asignación a nivel de cada centro de datos.

Haz clic en **«Guardar»** y, a continuación**, en «Publicar»** para aplicar la selección.

![Administrador de centros de datos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-admin.png)

Si la opción **«Distribución porcentual predeterminada»** está marcada como **«Sí»**, vaya a la pestaña **«Asignación estimada»** y siga las instrucciones que aparecen en pantalla para aplicar los cambios.

![Porcentaje de reparto estimado](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/assumed-percentage-split.png)

Si **la opción «Carga de tabla»** está **activ** ada, ve a la pestaña **«Carga de tabla de asignación»** y sigue las instrucciones que aparecen en pantalla para aplicar las actualizaciones.

![Método de carga de tablas](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/table-upload-method.png)

Pestaña «**Umbrales de capacidad** »: utilice esta pestaña para definir los valores del umbral de baja utilización (%) y del umbral de alta utilización (%) para los distintos tipos de capacidad.

- **El umbral de baja utilización (%)** identifica los recursos infrautilizados que pueden indicar un exceso de capacidad u oportunidades de optimización.
- **El umbral de alta utilización (%)** identifica los recursos que se acercan a sus límites de capacidad y los posibles riesgos operativos.

Cada tipo de capacidad puede tener un umbral diferente en función de consideraciones operativas.   
Por ejemplo:

- **Superficie (pies cuadrados):** Ayuda a identificar las limitaciones de espacio o las oportunidades de consolidación.
- **Unidades de rack:** Los umbrales se pueden configurar en función de la capacidad instalada del rack y de las necesidades de expansión.
- **Potencia ( kW ):** Los umbrales altos indican que la infraestructura eléctrica se está acercando a sus límites, mientras que los umbrales bajos pueden indicar un exceso de capacidad sin utilizar.
- **Refrigeración ( kW ):** Los umbrales altos ayudan a identificar los riesgos de saturación del sistema de refrigeración, mientras que los umbrales bajos pueden indicar un exceso de capacidad de refrigeración

Estos umbrales facilitan la planificación proactiva de la capacidad y la supervisión de la utilización en todo el centro de datos.

Los valores límite actuales se ofrecen a modo de orientaciones generales y pueden actualizarse en función de los requisitos de la organización y las necesidades operativas.

Siga las instrucciones que aparecen en pantalla para actualizar los valores de umbral.

![Umbral de capacidad](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/capacity-threshold.png)

**Asignaciones** Siga estos pasos para completar la configuración de las asignaciones:

1. Abre TBM Studio.
2. Ve al objeto **«Centros de datos»** y échale un vistazo.
3. Si se ha instalado el componente «CT Apps - Centros de datos», añada el campo **«Infraestructura»** al identificador del objeto «**Centros de datos** ». Si el componente **TCO de Data Centers** se ha instalado por primera vez, continúe con los siguientes pasos.

   ![Centros de datos de CT Apps](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-apps-datacenter.png)
4. Ve al objeto **«Torre de recursos informáticos»** y échale un vistazo.
5. Establece la métrica en «**Coste** ».
6. Abre la estrategia de asignación relacionada con el objeto «Centros de datos».
7. En la sección «Distribución», configura las siguientes opciones:
   - Activar «Ponderar por»
   - Selecciona la opción «Columna de la tabla» y establece la columna en la columna «Ponderación» de la tabla «**Datos maestros de centros de datos** ».

   ![De la torre de recursos informáticos al centro de datos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itresource=tower-datacenter.png)
8. Abre la página «Centros de datos» object.\
9. Abre la estrategia de asignación asociada al objeto **«Servidores»** y configura las siguientes opciones tal y como se muestra en la siguiente captura de pantalla:
   - En la sección «De», configura el filtro de modo que el campo **«Data Centers Master» Data.Infrastructure** sea igual a «Compute».
   - En la sección «Distribución», configura las siguientes opciones:
     - Activar «Ponderar por»
     - Selecciona la opción «Columna de la tabla» y establece la columna en «Horario del servidor» de la tabla **maestra de servidores**.
     - Active la opción «Relación de datos» y establezca la correspondencia según lo siguiente:
     - Ubicación = UbicaciónCierra la estrategia de asignación vinculada al objeto «Servidores».

   ![Objeto servidor](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/server-object.png)
10. Con el objeto **«Centros de datos»** aún abierto, pasa al siguiente paso.
11. Abre la estrategia de asignación del objeto **de almacenamiento** y configura las siguientes opciones tal y como se muestra en la siguiente captura de pantalla:
    - En la sección «De», configura el filtro de modo que el campo **«Data Centers Master» Data.Infrastructure** sea igual a «Storage».
    - En la sección «Distribución», configura las siguientes opciones:
      - Activar «Ponderar por»
      - Selecciona la opción «Columna de la tabla» y establece la columna en «Espacio utilizado» de la tabla «**Datos maestros de almacenamiento** ».
      - Active la opción «Relación de datos» y establezca la correspondencia según lo siguiente:
      - Ubicación = Ubicación

    ![Objeto de almacenamiento](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/storage-object.png)
12. Abre la estrategia de asignación correspondiente al objeto «Mainframes» y configura las siguientes opciones tal y como se muestra en la siguiente captura de pantalla:
    - En la sección «De», configura el filtro de modo que el campo **«Data Centers Master» Data.Infrastructure** sea igual a «Mainframe».
    - En la sección «Distribución», configura las siguientes opciones:
      - Active la opción «Relación de datos» y establezca la correspondencia según lo siguiente:
      - Ubicación = Ubicación

    ![Objeto de mainframe](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/mainframe-object.png)
13. **Guarda** y confirma los cambios.
14. Selecciona la métrica « **CapEx** » y configura las asignaciones del mismo modo que las de la métrica «Cost».

## Informes

Además del informe de administración de centros de datos, la solución de TCO para centros de datos incluye tres informes principales:

1. **Informe de revisión de centros de datos**

   **Dirigido a:** propietarios de centros de datos e instalaciones, directivos y responsables de finanzas de TI

   **Ventajas más importantes:**

   - Identifica los principales centros de datos según su coste y su superficie física, y compáralos por región, gestor, tipo de instalación (colocación / alquilada) y nivel
   - Comprender los factores que influyen en el coste total de propiedad (TCO), como el consumo eléctrico, la refrigeración, la mano de obra y los gastos con proveedores
   - Consulte los costes unitarios para comparar ubicaciones de centros de datos, incluyendo el coste por rack y el coste por metro cuadrado ( $/kW, )

   Compara ubicaciones de centros de datos, identifica ineficiencias y orienta las decisiones sobre inversión, consolidación y planificación de la capacidad.

   ![Informe de revisión de centros de datos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-review-report.png)
2. **Informe de análisis de centros de datos**

   **Dirigido a:** Analistas de finanzas y de infraestructura de TI

   **Ventajas principales:**

   - Consulte los costes y el consumo del centro de datos en un formato de tabla flexible utilizando filtros y dimensiones, métricas y periodos de tiempo opcionales.
   - Ver el consumo de energía, la superficie, las unidades de rack y la refrigeración, y compararlos con la capacidad
   - Analizar las tendencias en distintos periodos de tiempo: mensuales, trimestrales o según sea necesario para la elaboración de informes.

   ![Informe de análisis de centros de datos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenters-analysys-report.png)
3. **Informe de capacidad**

   **Dirigido a:** Propietarios de centros de datos e instalaciones

   **Ventajas más importantes:**

   - Conocer la capacidad total de las instalaciones de los centros de datos en cuanto a suministro eléctrico, refrigeración y espacio
   - Supervisar la utilización de la capacidad para identificar los puntos de congestión
   - Mejorar el aprovechamiento de las instalaciones e identificar la capacidad disponible antes de invertir en la ampliación

   Identifique la capacidad potencial y las limitaciones de sus centros de datos para optimizar de forma proactiva y planificar ampliaciones con total confianza

   Nota:

   Los datos más destacados del informe indican la utilización de la capacidad total en función del porcentaje de umbral.

   - Si la utilización es superior al umbral de alta utilización (%): rosa
   - Utilización < Umbral de baja utilización %: Amarillo
   - La utilización se encuentra entre el % del umbral de utilización alta y el % del umbral de utilización baja: Blanco

   ![Informe de capacidad](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/capacity-reports.png)

**Informes sobre la modernización de la interfaz de usuario:**

1. **Informe sobre la mejora de los centros de datos**

   ![Informe sobre la mejora de los centros de datos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-enrichment-report-nx.png)
2. **Informe de administración del centro de datos**
   - **Método de asignación:**

     ![Método de asignación](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-allocation-method.png)
   - **Asignación de presupuestos:**

     ![Asignación de presupuestos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-estimate-allocation.png)
   - **• Umbral de capacidad:**

     ![Umbral de capacidad](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/capacity-threshold-nx.png)
3. **Informe de revisión de centros de datos**

   ![Informe de revisión de centros de datos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-review-nx.png)
4. **Informe de análisis de centros de datos**

   ![Informe de análisis de centros de datos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/datacenter-analysys-nx.png)
5. **Informe de capacidad**

   ![Informe de capacidad](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/capacity-nx.png)
