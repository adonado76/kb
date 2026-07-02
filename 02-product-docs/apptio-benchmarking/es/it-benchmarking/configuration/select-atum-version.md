---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Integración de la norma de cálculo de costes"
breadcrumb: []
source_path: "it-benchmarking/configuration/select-atum-version.html"
images:
  - "resources/images/it_benchmarking_images/frontdoor.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_1.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_10.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_11.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_12.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_13.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_14.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_17.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_19.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_2.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_20.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_22.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_4.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_5.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_6.jpg"
  - "resources/images/it_benchmarking_images/pastedimage_9.jpg"
  - "resources/images/it_benchmarking_images/settingsadvanced.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Integración de la norma de cálculo de costes

Este documento proporciona información sobre (1) la selección de una versión de ATUM para la evaluación comparativa interactiva (2) el recorrido por los ajustes para obtener los datos reales de la aplicación Costing Standard . La primera sección del documento se centra en Costing Standard en R12 y la segunda sección explica cómo obtener datos reales de un proyecto de Costing Standard R11. La tercera sección describe el proceso de configuración que se sigue cuando un cliente inicia sesión en Interactive Benchmarking por primera vez.

**IMPORTANTE** En esta versión no se recuperan los reales de las subtorres. La obtención de datos de subtorres se habilitará en una versión posterior.

**Costing Standard en TBM Studio v12**

**Supuestos**

- Su producto Apptio está habilitado para Front Door.
- La aplicación R12 Costing Standard y la evaluación comparativa interactiva se encuentran en el mismo entorno.

Véase en la imagen siguiente un ejemplo de entorno con Costing Standard y Benchmarking interactivo.

NOTA Puede tener más de una Aplicación Costing Standard así como otras Aplicaciones en un entorno.

![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/frontdoor.jpg)

**Uso de Ajustes para la configuración**

En esta sección se explicará la configuración de las versiones de ATUM y la obtención de datos reales mediante las páginas de configuración.

La secuencia recomendada es seleccionar primero la versión de ATUM. Para ello, haga clic en el volante de configuración situado en la esquina superior derecha de la aplicación Benchmarking Interactivo. Verás la página de configuración con una serie de pestañas.

- Haga clic en la pestaña Avanzado. Aquí verá la sección de la versión ATUM (véase la imagen de abajo con V2 seleccionado).

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/settingsadvanced.jpg)
- Puede cambiar la versión de ATUM. Al hacerlo, verá un cartel amarillo de advertencia que proporciona información sobre:
  - Repercusiones del cambio de versión de ATUM :
    - Las torres y subtorres son diferentes en V1 y V2, por lo que la lista de torres y subtorres cambiará
    - Debido a esta diferencia, se descartarán los volúmenes, los datos de costes reales y las selecciones de referencia para torres y subtorres.
  - Siguientes pasos recomendados una vez realizado este cambio:
    - Recupere sus datos de costes reales o introdúzcalos manualmente
    - Actualice sus volúmenes
    - Revise sus selecciones en los niveles de referencia (Industria, TI OpEx e Infraestructura).

  La siguiente imagen muestra un ejemplo de cambio a V1. La pancarta amarilla con el impacto y las recomendaciones está a la derecha.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_11.jpg)
- A continuación, puede continuar con esta selección haciendo clic en Guardar. Esto da lugar a un cuadro de diálogo que enumera los datos con el mismo cartel amarillo de advertencia. **IMPORTANTE:** este paso todavía no permite obtener los datos reales del proyecto Costing Standard . Sólo cambia los datos actuales a la versión modificada ATUM. Es necesario hacer un Fetch explícito desde Actuals como se indica en los siguientes pasos.

  Debe hacer clic en "Continuar con estos datos reales" para cerrar este cuadro de diálogo.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_12.jpg)
- El siguiente paso consiste en configurar las opciones de búsqueda en Costing Standard. Para ello, haz clic en la **pestaña Fuente de APPTIO** en ajustes (ver imagen inferior). Esto proporcionará una lista desplegable de Costing Standard Aplicaciones en su Apptio (Front Door Environment). En esta pantalla, sólo hay una aplicación Costing Standard (con el nombre Costing Standard). A continuación, haga clic en el botón **Validar conexión**.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_17.jpg)
- Una vez validada la conexión, verá una pantalla en la que podrá seleccionar un proyecto Costing Standard y un mes concreto. En la siguiente imagen de ejemplo, puede ver que el proyecto seleccionado es: reference.apptio.com: Costing Standard. IMPORTANTE: Seleccione el proyecto CT específico del que desea obtener datos de costes reales. El cartel amarillo de la derecha es una nota de advertencia. Le indica que debe asegurarse de que el proyecto CT está abierto (ya que al seleccionar un proyecto cerrado se activará un calc en CT).

  Ahora haga clic en "Recuperar datos de costes" para obtener los datos reales del proyecto Costing Standard y del mes/año seleccionados.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_19.jpg)
- Ahora verá los datos obtenidos en un cuadro de diálogo (vea un ejemplo en la imagen siguiente). La columna Nueva fuente contiene los datos obtenidos del proyecto seleccionado.

  Haga clic en **Continuar con estos datos reales**. De este modo, se guardan los datos de costes recuperados del proyecto.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_20.jpg)
- También puede ver los datos de costes recuperados seleccionando la pestaña Datos de costes en Configuración. La imagen siguiente es una captura de pantalla de los Datos de costes. Muestra los costes globales, los costes del grupo de costes y los costes de la torre rellenados. Los costes de las subtorres están en blanco y deben introducirse manualmente.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_22.jpg)
- Por último, al igual que antes, el perfil de la organización se introduce manualmente (ya que no forma parte del proyecto Costing Standard ) porque es específico de la evaluación comparativa. Puede acceder al Perfil de la Organización seleccionando la pestaña Perfil de la Organización.

  Para los Costes y Volúmenes Anuales de las Subtorres, puede introducirlos mediante:

  - En la sección de ajustes; Costes anuales de la subtorre en la pestaña Datos de costes y Volúmenes en la pestaña Volúmenes, o bien
  - En las páginas individuales de las subtorres, en Métricas de infraestructura.

Ya está listo para realizar sus comparaciones de referencia con los datos reales.

**Costing Standard en TBM Studio v11**

Para los proyectos Costing Standard en v11, no hay integración Frontdoor. Esto significa que tendrá que crear/utilizar un usuario administrador (en v11 ) e introducir el nombre de usuario/contraseña en la Comparación Interactiva. En la pestaña Apptio Fuente (véase la imagen siguiente), tiene la opción de introducir manualmente las credenciales URL (el hipervínculo es: introducir manualmente las credenciales URL y AdminDB ). Haga clic en ese hipervínculo.

![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_1.jpg)

En el siguiente paso, verá los cuadros de texto de entrada donde debe proporcionar la instancia URL, AdminDB Nombre de usuario y AdminDB Contraseña. Este [vídeo](https://community.apptio.com/videos/1516 "(se abre en una pestaña o una ventana nueva)") ofrece información adicional sobre su uso.

![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_2.jpg)

Los demás pasos para seleccionar las versiones de ATUM y configurar los volúmenes, etc., son los mismos que para R12.

**Primer ajuste de la experiencia del usuario**

La aplicación Interactive Benchmarking ofrece una experiencia de usuario inicial a los clientes cuando inician sesión por primera vez. Esto es para guiarles en la configuración inicial.

- Si ningún usuario ha iniciado sesión en Interactive Benchmarking para un cliente y lo ha configurado, la primera pantalla que verá (si es el primer usuario) es una página de introducción. Vea un ejemplo en la imagen inferior. Identifica los pasos que debes seguir para configurarlo. Nota: también ofrece una opción para omitir la configuración en caso de que desee (1) configurarlo más tarde utilizando el flujo de Configuración mencionado anteriormente o (2) configurarlo manualmente.

  Para continuar, haga clic en el botón **Comencemos**.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_4.jpg)
- Los siguientes pasos son similares a los descritos en las secciones anteriores, pero con una experiencia más guiada. Revise las dos primeras secciones para familiarizarse con los detalles. El primer paso es seleccionar la versión de ATUM. Aquí se le pide que elija su versión de ATUM. Haga clic en **Siguiente**.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_5.jpg)
- A continuación, seleccione la fuente Costing Standard . La pantalla que verás será como la siguiente. Elige tu aplicación Costing Standard y haz clic en Conectar. **NOTA:** Aquí tiene la opción de saltarse estos pasos e ir a la pantalla de Benchmarking (haciendo clic en **introducir los datos de costes manualmente** ) o buscarlos en R11 (haciendo clic en **introducir manualmente las credenciales de URL y AdminDB** ).

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_6.jpg)
- Una vez que haga clic en **Conectar**, se le pedirá que seleccione el proyecto y el periodo de tiempo adecuados. El banner amarillo es el mismo que el descrito en la primera sección.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_9.jpg)
- Puede seleccionar su proyecto y periodo de tiempo y hacer clic en "Ir". Véase a continuación un ejemplo screen.This recupera los datos reales del proyecto.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_10.jpg)
- El último paso de configuración es escribir el Perfil de la Organización. Vea un ejemplo en la pantalla siguiente. Introduzca los datos de su perfil de organización y haga clic en **Siguiente**.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_13.jpg)
- En este punto ha configurado la Evaluación Comparativa Interactiva. Verá una pantalla "Listo" como la siguiente. Si hace clic en "Explorar", accederá a una aplicación de evaluación comparativa interactiva configurada.

  ![pi1](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/pastedimage_14.jpg)

En cualquier momento, puede realizar modificaciones en su configuración haciendo clic en el volante de configuración situado en la parte superior derecha de la pantalla y siguiendo los pasos mencionados en la primera sección.
