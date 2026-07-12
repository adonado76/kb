---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "billing-essentials"
title: "Configuración"
breadcrumb: []
source_path: "billing-essentials/configure-billing-essentials/configuration.html"
images:
  - "resources/images/be/be-flowchrt.jpg"
  - "resources/images/be/be-s9.jpg"
  - "resources/images/be/billing-charge.jpg"
  - "resources/images/be/s7-sl.jpg"
  - "resources/images/studio_images/alloc-chrt.jpg"
  - "resources/images/studio_images/be-tu1.jpg"
  - "resources/images/studio_images/be-tu2.jpg"
  - "resources/images/studio_images/be-tu3.jpg"
  - "resources/images/studio_images/be-tu4.jpg"
  - "resources/images/studio_images/be-tu5.jpg"
  - "resources/images/studio_images/becomp-1.jpg"
  - "resources/images/studio_images/bes11.jpg"
  - "resources/images/studio_images/bes11chrg.jpg"
  - "resources/images/studio_images/bes11pc.jpg"
  - "resources/images/studio_images/bes11pu.jpg"
  - "resources/images/studio_images/bes9.jpg"
  - "resources/images/studio_images/besolution.jpg"
  - "resources/images/studio_images/cons-feed.jpg"
  - "resources/images/studio_images/df-chart.jpg"
  - "resources/images/studio_images/mc-be.jpg"
  - "resources/images/studio_images/s8.jpg"
  - "resources/images/studio_images/samp-ref.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración

1. (TBM Studio): Crear un proyecto.
2. (TBM Studio): Billing Essentials soporta Multidivisa. Consulte [aquí](multi-currency.html) los detalles de configuración.
3. (TBM Studio): Configure los ajustes de tiempo y compruebe los cambios.
4. (TBM Studio): Instale el componente **Facturación - Cargo** en el proyecto. ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/be/billing-charge.jpg) ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/becomp-1.jpg)
5. (TBM Studio): Cree dos tablas de entrada para garantizar que se cargan los detalles relevantes.
   - Nombre de la tabla: Alimentación de consumo
   - Nombre de la tabla de alimentación: Biblioteca de soluciones

     Muestra de referencia:

     El nombre de las tablas puede ser específico para cada cliente

     ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/samp-ref.jpg)
6. (TBM Studio): Guarde y registre los cambios.
7. (TBM Studio): Estas tablas deben asignarse a las tablas Master/Feed como se muestra a continuación

   Consumo de piensos (tabla de consumo de piensos)

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cons-feed.jpg)

   Alimentación de la biblioteca de soluciones (tabla de la biblioteca de soluciones)

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/be/s7-sl.jpg)

   *\*\* Si falta la columna de origen que se va a asignar, asegúrese de que se especifica el tipo de datos correcto para la columna en la sección "Sustitución de tipo" de la transformación "Importar" de la tabla*
8. (TBM Studio): Guarde y registre los cambios.

   Nota:
   - Si se produce algún cambio, cargue la tabla de entradas de forma ad hoc/mensual para garantizar la exactitud de los informes
   - Compruebe que la fórmula "Facturable" resaltada a continuación está presente en el Maestro de soluciones para garantizar que se rellenan datos precisos en los informes

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/s8.jpg)

   Informe de gestión de tarifas (debe instalarse el componente "Facturación - Informes")
9. (Vista de informe): Vaya a Facturación > Gestión de tarifas.

   Elimine el filtro de "Facturable" para mostrar todas las Ofertas. Utilice esta tabla para editar la columna "Facturable" a "Sí" o "No". Además, las actualizaciones de las columnas "Tarifa base" y "Gestión de tarifas" pueden aplicarse para establecer la tarifa facturable si es necesario

   - **Tarifa base** - Tarifa inicial establecida a partir del coste unitario de Costing Essentials
   - Ajuste de **tarifa** : introduzca un número positivo o negativo para calcular y ajustar la tarifa facturable (tarifa facturable = tarifa base + ajuste de tarifa), calculada mediante el script ET
   - **Impacto del ajuste** de tarifas - Se utiliza para identificar claramente el cargo frente a la recuperación de costes como resultado del ajuste de tarifas

   Seleccione **Guardar** y luego **Publicar** para propagar a todos los informes y modelos, "Biblioteca de soluciones ET Transform"

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/be/be-s9.jpg)

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes9.jpg)

   \*\* Una vez publicado, asegúrese de que el filtro "Facturable" está en "Sí" para ver el valor del cargo en el informe.
10. (TBM Studio): Vaya a Tablas > Biblioteca de soluciones ET Transform y revise los datos posteriores a Publicar en el paso 10. Además, se puede establecer una publicación periódica para esta tabla. Para más información, véase [Publicación recurrente de la tabla de transformación](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-recurring-publish-transform-table "(se abre en una pestaña o una ventana nueva)").
11. (TBM Studio): Abrir el modelo de consumo y verificar las asignaciones

    Unidades facturables

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes11.jpg)

    *\*\* Esta captura de pantalla sirve de referencia, ya que las imputaciones de costes variarán en función de los datos.*

    **Carga**

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes11chrg.jpg)

    *\*\* Esta captura de pantalla sirve de referencia, ya que las imputaciones de costes variarán en función de los datos.*

    Cargo del plan

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes11pc.jpg)

    *\*\* Esta captura de pantalla sirve de referencia, ya que las imputaciones de costes variarán en función de los datos.*

    Plan Unidades

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes11pu.jpg)

    *\*\* Esta captura de pantalla sirve de referencia, ya que las imputaciones de costes variarán en función de los datos.*

    Asimismo, verifique las asignaciones en el modelo **Solutions** para las métricas antes mencionadas

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/besolution.jpg)

    *\*\* Esta captura de pantalla sirve de referencia, ya que las imputaciones de costes variarán en función de los datos.*

    Diagrama de flujo de datos

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-chart.jpg)

    Cuadro de asignación

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/alloc-chrt.jpg)

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/be/be-flowchrt.jpg)

**Multidivisa**

Si el cliente utiliza Multidivisa este sería un buen momento para configurarlo. La multidivisa es la misma en Costing Essentials que en los proyectos CT. Puede consultar la configuración Multidivisa en el Centro de ayuda.

Sin embargo, si su cliente utiliza un calendario no gregoriano, la nueva versión de MCC no lo admite. Si su cliente requiere un calendario no gregoriano, siga la configuración Legacy Multi-currency aquí.

Seleccione la **moneda base** preferida.

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/mc-be.jpg)

**Carga de tablas**

El componente **Carga de tablas** permite a los usuarios finales con los permisos adecuados **cargar** directamente datos de hojas de cálculo en tablas sin necesidad de acceder a TBM Studio . El informe de carga de tablas consta de dos pestañas: Carga de tablas y Acceso a carga de tablas.

**Pestaña Carga de tablas**

La pestaña de Carga de Tablas ayudará a los usuarios a cargar directamente los datos en el Libro Mayor/Consumo, Presupuesto y Mano de Obra sin necesidad de acceder a TBM Studio .

Vaya a Workbench > Carga de tablas > Carga de tablas, como se muestra:

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu1.jpg)

El componente de carga de tablas ofrece dos opciones de configuración: [configuración simple](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-table-upload-component#TableUploadcomponent__Simpleconfiguration__title__1 "(se abre en una pestaña o una ventana nueva)") y [configuración avanzada](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-table-upload-component#TableUploadcomponent__Advancedconfiguration__title__1 "(se abre en una pestaña o una ventana nueva)"). En este ejemplo, está equipado con Configuración Avanzada, lo que permite la coincidencia de usuarios en la pestaña Acceso a la carga de tablas.

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu2.jpg)

**Ficha Acceso a la carga de tablas**

La pestaña de Acceso a Carga de Tablas ayudará a los administradores a gestionar el acceso a quién puede cargar datos directamente en el Libro Mayor/Consumo, Presupuesto y Mano de Obra sin necesidad de acceder a TBM Studio .

Vaya a Workbench > Carga de tablas > Carga de tablas > Acceso a carga de tablas, como se muestra:

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu3.jpg)

Conceda acceso a la carga de tablas especificando el nombre de la tabla y los detalles del usuario correspondiente para permitirles cargar datos en la tabla designada, como se muestra a continuación.

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu4.jpg)

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu5.jpg)

*\*\* La visibilidad de la pestaña se puede personalizar en función de los requisitos del cliente para controlar qué roles de usuario tienen acceso a la pestaña "Acceso a carga de tablas" en el informe de carga de tablas.*

Para más información, consulte [la Tabla de carga](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-table-upload-component "(se abre en una pestaña o una ventana nueva)").
