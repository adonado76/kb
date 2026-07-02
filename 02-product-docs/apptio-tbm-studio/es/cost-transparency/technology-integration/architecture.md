---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Conectividad y arquitectura de datos"
breadcrumb: []
source_path: "cost-transparency/technology-integration/architecture.html"
images:
  - "resources/images/ct_images/trb-arch-1.jpg"
  - "resources/images/ct_images/trb-arch-addr.jpg"
  - "resources/images/ct_images/trb-arch-et.jpg"
  - "resources/images/ct_images/trb-framework.jpg"
  - "resources/images/ct_images/trb-model-alloc.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conectividad y arquitectura de datos

El siguiente diagrama ilustra el flujo de datos de IBM Turbonomic a IBM Apptio 's Datalink. A continuación se describen los pasos a seguir:

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/trb-arch-1.jpg)

1. **Configuración y descubrimiento de datos IBM Turbonomic** : IBM Turbonomic realiza su configuración normal y descubre datos para cada objetivo agregado. La lista completa de objetivos compatibles está disponible [aquí](https://www.ibm.com/docs/en/tarm/8.13.0?topic=documentation-target-configuration "(se abre en una pestaña o una ventana nueva)"). Turbonomic descubre recursos, supervisa su utilización y recomienda acciones. El diagrama muestra algunos objetivos de muestra en azul.
2. **IBM Apptio Configuración del tipo de destino** : Configure el tipo de destino IBM Apptio en IBM Turbonomic según los requisitos previos. Esta configuración envía los datos de IBM Turbonomic a IBM Apptio 's Datadrop. Asegúrese de que IBM Apptio 's Datadrop se ha configurado correctamente. Las instrucciones para configurar Datadrop/SFTP Server en el lado Apptio se pueden encontrar en el [ Apptio Help Center](#).
3. **Carga y actualización de archivos** : Los archivos en formato JSON se cargan diariamente en el servidor Datadrop/SFTP basado en la nube de Apptio. La carga útil consta de cuatro conjuntos de datos: Acciones pendientes y ejecutadas para entornos On-Prem y Cloud. Cada día aparecerán cuatro nuevos archivos en el repositorio del visor de Datadrop. Para más detalles sobre el contenido del archivo, consulte la sección Carga útil de datos.
4. **Datalink Configuración de conectores** : Cree conectores Datalink para extraer datos del repositorio Datadrop e introducirlos en TBM Studio:
   - Para Acciones pendientes, establezca el comportamiento de carga en "SOBREESCRITAR" Cada archivo diario de IBM Turbonomic muestra las últimas Acciones Pendientes, por lo que debería sobrescribir el archivo anterior en TBM Studio.
   - Para Acciones ejecutadas, establezca el comportamiento de carga en "APPEND" El archivo contiene las Acciones Ejecutadas de las últimas 24 horas, así que añada los datos para crear una vista de Mes a Fecha.
   - TBMA puede programar ejecuciones de conectores (diarias, semanales o mensuales). Para automatizar el proceso, asigne los nombres de destino de las tablas directamente a los conjuntos de datos creados por IBM Apptio Framework.
5. **Integración de datos en TBM Studio**  : Tras ejecutar los conectores, la carga útil se almacenará en las siguientes tablas de TBM Studio :
   - Acciones pendientes de Turbo Cloud
   - Turbo On-Prem Acciones pendientes
   - Acciones ejecutadas de Turbo Cloud
   - Turbo On-Prem Acciones ejecutadas

## IBM Apptio Marco

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/trb-framework.jpg)

El diagrama del marco proporciona una visión general de la arquitectura de optimización de TI híbrida impulsada por las acciones pendientes y ejecutadas de Turbonomic de IBM. Introduce nuevas tablas y conjuntos de datos maestros desde la perspectiva de IBM Turbonomic (instalado a través del componente IBM Turbonomic - Actions) y desde una perspectiva más amplia de Hybrid IT Optimization (instalado a través del componente Hybrid IT Optimization).

Esta arquitectura relaciona los nuevos puntos de datos con los ya existentes en el modelo IBM Apptio. Hay 12 pasos de configuración, con burbujas rojas que indican las configuraciones requeridas por el usuario y burbujas naranjas para los pasos automatizados/preconfigurados. Estos pasos se detallan en la sección Configuración.

## IBM Apptio Modelo de asignaciones

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/trb-model-alloc.jpg)

El marco IBM Apptio ofrece una visión general de las nuevas tablas y conjuntos de datos, mientras que el diagrama anterior se centra en las nuevas métricas y asignaciones del modelo:

**Coste híbrido/Carga híbrida**

Se trata de nuevas métricas paralelas que aprovechan los modelos de coste/tarifa existentes, centrándose únicamente en el coste total de la capa de infraestructura. Las métricas existentes no se reutilizan para evitar dobles asignaciones y conflictos.

Los usuarios deben crear controladores para estos modelos. Una vez establecidas las asignaciones al nuevo objeto del modelo de infraestructura, el modelo restante seguirá el flujo descrito.

**Recuento de acciones**

Nuevas métricas independientes para los informes del mes hasta la fecha (MTD) y del año hasta la fecha (YTD) sobre recuentos de Acciones Pendientes y Ejecutadas.

**Ahorro potencial/Ahorro realizado**

Estas son métricas clave en el marco de optimización de la TI híbrida.

- El ahorro potencial se basa en las acciones pendientes.
- El ahorro realizado se basa en las acciones ejecutadas. Ambos parámetros se dividen en dos dimensiones: costes y gastos
  - **Coste** : Para la nube, los ahorros en dólares proceden directamente de IBM Turbonomic. Para On-Prem, el ahorro se calcula utilizando el cambio de valor de la acción (por ejemplo, 12 vCPU reducidos a 2 vCPU, lo que supone un ahorro de 10 vCPU ) y el coste unitario de los servicios técnicos. Los ajustes se realizan en función del % direccionable establecido por el usuario.
  - **Cargo** : Sigue un planteamiento similar, utilizando el precio de los servicios técnicos y ajustándose en función del % direccionable fijado por el usuario. Estos ahorros van dirigidos al consumidor de servicios o aplicaciones de cara a la empresa.

**Nivel de direccionamiento**

Los usuarios deben establecer y editar el % Direccionable tanto para el coste unitario como para el precio. La fijación de este porcentaje repercute tanto en el cálculo del ahorro de costes como en el de gastos. El desglose del ahorro se divide en:

- Ahorro directo
- Ahorro diferido
- Evitar costes

Los usuarios tienen plena autonomía para definir la asignación del % direccionable entre estas categorías. Esto puede establecerse a través de la pestaña Workbench del informe Optimización de la infraestructura - Vista del proveedor.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/trb-arch-addr.jpg)

Las columnas en gris claro se añaden a la tabla editable a partir del catálogo de servicios existente, mientras que las columnas en blanco las define el usuario.

![](../../../../../03-media/apptio-tbm-studio/resources/images/ct_images/trb-arch-et.jpg)
