---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "es"
doc_type: "apptio-cost-management"
title: "Configuración de dispositivos de usuario final"
breadcrumb:
  - "Costing Essentials"
  - "Soluciones adicionales"
  - "Dispositivos de usuario final"
source_path: "apptio-cost-management/getting_started/ce-eud.html"
images:
  - "resources/images/acm_images/17-1.jpg"
  - "resources/images/acm_images/17-2.jpg"
  - "resources/images/acm_images/8-a.jpg"
  - "resources/images/acm_images/8-b.jpg"
  - "resources/images/acm_images/8-c.jpg"
  - "resources/images/acm_images/apdx-1.jpg"
  - "resources/images/acm_images/apdx-2.jpg"
  - "resources/images/acm_images/apdx-3.jpg"
  - "resources/images/acm_images/eud-mc.jpg"
  - "resources/images/acm_images/s-10.jpg"
  - "resources/images/acm_images/s-11.jpg"
  - "resources/images/acm_images/s-12.jpg"
  - "resources/images/acm_images/s-13.jpg"
  - "resources/images/acm_images/s-14.jpg"
  - "resources/images/acm_images/s-15.jpg"
  - "resources/images/acm_images/s-16.jpg"
  - "resources/images/acm_images/s-3.jpg"
  - "resources/images/acm_images/s-4.jpg"
  - "resources/images/acm_images/s-5.jpg"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Configuración de dispositivos de usuario final

Siga estos pasos para empezar a utilizar los dispositivos de usuario final

**Instale el componente Dispositivos de usuario final**

(TBM Studio): Crear un proyecto.

1. (TBM Studio): Los Dispositivos de Usuario Final soportan Multidivisa. Haga clic [aquí](#multi-cu "(se abre en una pestaña o una ventana nueva)") para ver los detalles de la configuración.
2. (TBM Studio): Configure los ajustes de tiempo y compruebe los cambios.
3. (TBM Studio): Instalar en el proyecto el componente **Coste- Dispositivos de Usuario Final**.

![componente](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-4.jpg)

¿Qué contiene el componente?

![eud](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-3.jpg)

1. (TBM Studio): Cree tres tablas de entrada para garantizar que se cargan los detalles pertinentes.

Active Directory

Dispositivos de usuario final

Datos laborales

Muestra para referencia - El nombre de las tablas puede ser específico del cliente.

![](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-5.jpg)

1. (TBM Studio): Guarde y registre los cambios.
2. (TBM Studio): Consulte la sección [Apéndice](#appendix "(se abre en una pestaña o una ventana nueva)") para ver las fórmulas de transformación utilizadas en el proyecto de referencia.
3. (TBM Studio): Asigne las siguientes tablas a las tablas Master y Feed correspondientes:

EUD Active Directory Maestro (tabla Active directory)

![apéndice](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/8-a.jpg)

EUD Labor Master (Datos laborales)

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/8-b.jpg)

EUD Feed (Dispositivos de usuario final)

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/8-c.jpg)

1. (TBM Studio): Guarde y registre los cambios.

Si se produce algún cambio, cargue el cuadro de entrada ad hoc/mensualmente para garantizar la exactitud de los informes.

Utilice el formato de fecha "MM/dd/aaaa" para todas las cargas y transformaciones de datos a fin de evitar cambios de fórmula en las tablas maestras.

**Banco de trabajo EUD**

1. (Vista de informe): Vaya a Workbench > EUD Workbench > Exenciones

Utilice esta tabla para editar, añadir y eliminar usuarios para la exención del dispositivo de informes y cuadros de mando.

Haga clic en Guardar y luego pulse Publicar para propagar a todos los informes y modelos, "EUD Exemptions ET Transform"

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-10.jpg)

1. (Vista de informe): Vaya a Workbench > EUD Workbench > Device Estimate Refresh Cost

Utilice esta tabla para editar, añadir y eliminar los detalles del Coste estimado de actualización del dispositivo para los modelos de dispositivos de su inventario ![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-11.jpg)

Haga clic en Guardar y luego pulse Publicar para propagar a todos los informes y modelos, 'Device Estimate Refresh Cost ET Transform'.

1. (Vista de informe): Vaya a Workbench > EUD Workbench > Modelos de dispositivos con información de costes de actualización faltante

Verifique la lista de Modelos de Dispositivos de su Inventario, a los que les falta el Costo Anual de Actualización del Dispositivo Est.

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-12.jpg)

1. (Vista de informe): Navegue hasta Workbench > EUD Workbench > Device EOL EOW Term

Utilice esta tabla para editar, añadir y eliminar los plazos de Fin de vida útil y Fin de garantía en años para los modelos de dispositivos de su inventario.

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-13.jpg)

Haga clic en Guardar y luego pulse Publicar para propagar a todos los informes y modelos, 'Device EOL and EOW Term ET Transform'.

1. (Vista de informe): Vaya a Workbench > EUD Workbench > Modelos de dispositivos con falta de términos EOL y EOW

Esto proporciona la lista de modelos de dispositivos de su inventario, a los que les falta información sobre el final de la vida útil y el final del plazo de garantía, y añade la información en la pestaña 'Device EOL EOW Term'.

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-14.jpg)

1. (Vista de informe): Vaya a Workbench > EUD Workbench > In Stock Definition

Utilice esta tabla para editar, añadir y eliminar los diferentes estados de los dispositivos de usuario final que deben considerarse como "En Stock". La lista de estados disponibles en esta tabla se transforma en "En stock" en todos los informes de End User Insight

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-15.jpg)

Haga clic en Guardar y luego pulse Publicar para propagar a todos los informes y modelos, 'EUD In Stock Status Definition ET Transform'.

1. (Vista de informe): Vaya a Workbench > EUD Workbench > Última versión del sistema operativo

Utilice esta tabla para editar, añadir y eliminar Sistemas Operativos y sus correspondientes detalles de última versión, para marcar los dispositivos con SO no conformes.

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-16.jpg)

Haga clic en Guardar y luego pulse Publicar para propagar a todos los informes y modelos, 'EUD OS Version ET Transform'.

1. (TBM Studio): Abrir el modelo de dispositivos de usuario final y verificar las asignaciones de costes

**Coste adquirido**

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/17-1.jpg)

**Coste estimado de actualización**

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/17-2.jpg)

Ambas capturas de pantalla son orientativas y las imputaciones de costes pueden variar en función de los datos

**Anexo**

Fórmulas aplicadas para transformar los datos de entrada de referencia a fin de cumplir los requisitos del EUD Master y del EUD Feed.

Las fórmulas que figuran a continuación sirven únicamente como datos de referencia. Los clientes pueden actualizar estas fórmulas para adaptarlas a sus datos específicos y a las normas del sector.

Instantánea adjunta de las fórmulas aplicadas al

**ACME Active Directory Entrada**

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/apdx-1.jpg)

**Entrada de dispositivos de usuario final ACME**

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/apdx-2.jpg)

**Entrada de datos laborales ACME**

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/apdx-3.jpg)

**Multidivisa**

Si el cliente utiliza Multidivisa este sería un buen momento para configurarlo. La multidivisa es la misma en Costing Essentials que en los proyectos CT. Puede consultar la [configuración Multidivisa](../../multi-currency/home.html) en el Centro de Ayuda.

Sin embargo, si su cliente utiliza un calendario no gregoriano, la nueva versión de MCC no lo admite. Si su cliente requiere un calendario no gregoriano, siga la configuración Legacy Multi-currency [aquí](../../studio/admin/configure-multi-currency.html).

Seleccione la **moneda base** preferida.

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/eud-mc.jpg)
