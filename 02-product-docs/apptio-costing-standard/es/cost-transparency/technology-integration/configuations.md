---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Configuraciones"
breadcrumb: []
source_path: "cost-transparency/technology-integration/configuations.html"
images:
  - "resources/images/ct_images/trb-cnfg-1.jpg"
  - "resources/images/ct_images/trb-cnfg-2.jpg"
  - "resources/images/ct_images/trb-cnfg-3.jpg"
  - "resources/images/ct_images/trb-cnfg-4.jpg"
  - "resources/images/ct_images/trb-cnfg-5.jpg"
  - "resources/images/ct_images/trb-cnfg-6.jpg"
  - "resources/images/ct_images/trb-stp-10.jpg"
  - "resources/images/ct_images/trb-stp-3b.jpg"
  - "resources/images/ct_images/trb-stp-4.jpg"
  - "resources/images/ct_images/trb-stp-6rc.jpg"
  - "resources/images/ct_images/trb-stp3a.jpg"
  - "resources/images/ct_images/trb-stp6.jpg"
  - "resources/images/ct_images/trb-stp6filt.jpg"
  - "resources/images/ct_images/trb-stp7-oi.jpg"
  - "resources/images/ct_images/trb-stp7b.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configuraciones

Como se destaca en la sección [Arquitectura](architecture.html), la integración técnica implica 12 pasos distintos. Esta sección describe cada paso en detalle. Todo lo marcado en **rojo** requiere configuración por parte del usuario, mientras que **el naranja** indica un paso automatizado.

![Configuración](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-1.jpg)

**Paso 0** : Configuración de requisitos previos

Asegúrese de que tanto **IBM Apptio Datadrop** como **IBM Apptio Target Type en IBM Turbonomic** están configurados. Estas configuraciones se explican en las secciones anteriores. Una vez instalados, los archivos de datos fluirán diariamente hacia Datadrop. Los archivos son visibles en su Visor Datadrop dentro de Datalink, como se muestra en la siguiente captura de pantalla.

![Visor Datadrop](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-2.jpg)

A continuación, crea un nuevo conector Datalink utilizando el tipo de conector Datadrop.

![Conector Datadrop](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-3.jpg)

![Conexiones](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-4.jpg)

Configure la opción Transformar del siguiente modo:

- OVERWRITE para acciones pendientes
- APPEND para acciones ejecutadas

Asegúrese de que el conector recupera el periodo de tiempo dinámicamente a partir del nombre del archivo seleccionando la opción "Nombre del archivo Mes y Año".

![Acciones pendientes](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-5.jpg)

En la sección Sistema fuente, utilice el patrón de nombre de archivo fijo proporcionado por IBM Turbonomic:

**Turbonomic\_<cloud/onprem>\_<executed/pending>\_actions\_<target name> \_MMDDYYYY.json**

- Dado un nombre de objetivo de "ApptioA"
- Y la fecha actual de "12 Oct 2024"
- Y los datos de acciones pendientes On-prem
- Entonces, el nombre del archivo es:   
  Turbonomic\_onprem\_pending\_actions\_ApptioA\_10122024.json
- Dado un nombre de objetivo "Apptio\_B"
- Y la fecha actual de "1 Nov 2024"
- Y los datos de las acciones ejecutadas en la nube
- Entonces el nombre del archivo es Turbonomic\_cloud\_executed\_actions\_Apptio\_B\_11012024.json

Para el destino, establece los nombres de las tablas en:

- Acciones pendientes Turbo On Prem
- Acciones pendientes de Turbo Cloud
- Acciones Turbo On Prem Ejecutadas
- Acciones ejecutadas de Turbo Cloud

![Acciones pendientes en las instalaciones](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-cnfg-6.jpg)

: Discuta las opciones de archivado con su Gestor de Éxito de Clientes o con el Equipo DAT.

1. Después de configurar los Datalink conectores, los datos se transferirán automáticamente a TBM Studio las tablas: Acciones pendientes de Turbo On Prem, Acciones pendientes de Turbo Cloud, Acciones ejecutadas de Turbo On Prem y Acciones ejecutadas de Turbo Cloud. Estas tablas se crean previamente durante la instalación del componente, y la carga de datos seguirá la misma sintaxis de columnas. En la primera ejecución, realice una comprobación para asegurarse de que el formato y el contenido de los datos son correctos.
2. Los conjuntos de datos se incorporarán automáticamente a la tabla Turbo Actions Feed, combinando las acciones pendientes y ejecutadas para su posterior procesamiento.
3. A medida que los datos se introducen en la tabla Turbo Actions Feed, se vincularán a los modelos de datos Apptio existentes, especialmente para la cuantificación de datos On-Prem. Este paso implica:
   1. Añadir conjuntos de datos maestros de infraestructura (por ejemplo, datos maestros de servidores) a la tabla de alimentación de infraestructura.

      ![Conjuntos de datos maestros de infraestructura](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp3a.jpg)
   2. Creación de nuevos controladores para los modelos de Coste Híbrido y Cargo Híbrido, vinculando el coste y el cargo de los modelos existentes al nuevo objeto del modelo de Infraestructura.

      ![Modelos de coste híbrido y carga híbrida](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-3b.jpg)
4. Una vez añadidos los conjuntos de datos de infraestructura Apptio existentes, valide la búsqueda lista para usar (OOTB) entre la tabla Turbo Actions Feed y la tabla Infrastructure. Esta búsqueda vincula el nombre de la entidad de Turbo con el nombre de Infra de Apptio. Este paso está resaltado en Rojo porque la búsqueda OOTB puede necesitar personalización para maximizar la conexión de datos.

   ![OOTB](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-4.jpg)
5. Los datos *de* la fuente de acciones turbo se añadirán automáticamente al conjunto de datos *maestro de acciones turbo*. La tabla de *alimentación* prefiltra y normaliza los datos, mientras que la tabla *maestra* es donde se realizan los cálculos principales, como el ahorro.
6. El componente *Optimización de TI híbrida* crea un conjunto de tablas editables de Workbench, que se muestran a través de la interfaz de informes. Las tablas clave que hay que configurar son:
   - **Objetivos y ajustes** : Garantizar que los objetivos COIN se fijan de conformidad con los acuerdos internos.

     ![Objetivo y configuración](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp6.jpg)
   - **Filtros** : Excluir cualquier Acción o Tipo de Entidad que no afecte al ahorro potencial o realizado.

     ![Filtros](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp6filt.jpg)
   - Tabla de **tarifas** : La tabla editable más importante es la tabla de tarifas unitarias. Establezca el Porcentaje direccionable (%) y sus desgloses detallados; de lo contrario, el sistema utilizará por defecto las columnas de Coste unitario y Precio basadas en el Coste total de propiedad (TCO).

     ![Rate Card](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-6rc.jpg)
7. Como parte del componente *Optimización de TI híbrida*, se crean automáticamente varias tablas adicionales. Una de estas tablas es la tabla " *Infraestructura no encontrada en la optimización* ", que proporciona información sobre la parte del conjunto completo de infraestructuras cargadas en Apptio a la que se han aplicado optimizaciones Turbo. Estos datos se visualizan en el informe Vista del proveedor en dos áreas::
   - **Impacto de la optimización** : Grado de optimización o impacto de la infraestructura.

     ![Impacto de la optimización](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp7-oi.jpg)
   - **Infra sin Acciones** : Infraestructura sin acciones pendientes o ejecutadas.

     Esto puede ocurrir porque la infraestructura no está dentro del alcance de la optimización del Turbo o porque ya está totalmente optimizada.

     ![Infra sin ninguna acción](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp7b.jpg)
8. El objeto *Optimización de infraestructura detallada* se asigna a *Optimización de infraestructura*. El marco incluye tanto un objeto detallado como un objeto resumido para optimizar las capacidades de información y desglose. Ambos objetos se instalan como parte del componente *Optimización de TI híbrida*.
9. Para permitir la generación de informes desde la perspectiva de la aplicación (consumidor), los datos de infraestructura deben estar relacionados con las aplicaciones. Este paso asigna métricas del modelo al objeto Relaciones de infraestructura.
10. Añadir los datos *de relaciones* de infraestructura Apptio existentes al nuevo objeto Relaciones de infraestructura. Esto se hace por motivos de eficiencia, más que para ampliar el conjunto de datos anterior. ![Relación](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-stp-10.jpg)

    Si la relación con el consumidor de la infraestructura existe dentro del mismo conjunto de datos (por ejemplo, el conjunto de datos maestros del servidor), se añade al modelo en esta fase por motivos de eficacia, en lugar de ampliar el conjunto de datos original de la infraestructura.
11. El componente *Optimización de TI híbrida* incluye líneas de asignación predefinidas que transfieren automáticamente todas las métricas del modelo desde el objeto Modelo de relación de infraestructura al objeto Aplicaciones. Esto permite la generación de informes de vista de consumidor listos para usar (OOTB) desde la perspectiva de las aplicaciones.
12. Este último paso proporciona un marcador de posición para que los clientes amplíen los informes más allá de las aplicaciones, lo que permite asignaciones posteriores a servicios empresariales o unidades de negocio según sea necesario. Esto permite elaborar informes adicionales sobre las oportunidades de optimización y ahorro.
