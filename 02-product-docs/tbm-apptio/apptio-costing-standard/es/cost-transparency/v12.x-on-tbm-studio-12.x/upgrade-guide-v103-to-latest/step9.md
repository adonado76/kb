---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Paso 9: Integrar los cambios en el proyecto principal (Trunk)"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step9.html"
images:
  - "resources/images/ct_images/upgrade-from-v3-17.png"
  - "resources/images/ct_images/upgrade-from-v3-18.png"
  - "resources/images/ct_images/upgrade-from-v3-19.png"
  - "resources/images/ct_images/upgrade-from-v3-20.png"
  - "resources/images/ct_images/upgrade-from-v3-21.png"
  - "resources/images/ct_images/upgrade-from-v3-22.png"
  - "resources/images/ct_images/upgrade-from-v3-23.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Paso 9: Integrar los cambios en el proyecto principal (Trunk)

Consulte [las mejores prácticas de ramificación, revisión y bifurcación](https://community.apptio.com/docs/DOC-5472 "(se abre en una pestaña o una ventana nueva)") en Product Central.

1. Volver a la página **TBM Studio**.
2. Seleccione la rama de actualización (por ejemplo, Actualización de la versión 104).
3. En la pestaña **Proyecto**, haga clic en **Historial de entradas**.
4. Desplácese hasta la parte inferior de la lista y haga clic en el primer elemento situado encima de las entradas "bootstrap", por ejemplo, "Configuración del proyecto: cambiar a v104 " check-in.

   Nota: Puede seleccionar elementos adicionales para facturar como una fusión única, pero no seleccione más de 5 elementos a la vez. Fusionar más de 5 elementos en un mismo registro podría provocar el fallo de la aplicación.
5. Haga clic con el botón derecho del ratón en la partida y seleccione **Combinar cambios en la rama**.

   Para las capturas de pantalla de este ejemplo, utilizaremos el elemento de fusión Aplicación CT-Apps.
6. Seleccione **Troncal** como destinatario de la fusión.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-17.png)

   Se abre el cuadro de diálogo **Combinar conjuntos de cambios**.
7. Seleccionar todos los elementos para la fusión (por defecto).

   Nota: No deseleccione ningún elemento individual. Todos los elementos se fusionan, estén seleccionados o no.
8. Pulse **Aceptar**.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-18.png)

   **RECOMENDACIÓN:** Realice un seguimiento manual de los pasos fusionados a medida que actualiza los componentes, ya que el cuadro de diálogo Historial de registros no indicará qué elementos se han fusionado. Si intenta registrar un elemento dos veces y aparece el siguiente mensaje, haga clic en **Cancelar** y, a continuación, proceda con otro componente.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-23.png)
9. Una vez completado, la ventana podría cambiar a **Tronco**.
10. Cambie a **Trunk** para comprobar el elemento fusionado en su proyecto.
11. Para verificar que el cambio se ha propagado al entorno de Desarrollo:
    1. En la barra de navegación, seleccione el entorno **En desarrollo**.
    2. Haga clic en la pestaña **Proyecto**.
    3. Haga clic en **Componentes**.
    4. Compruebe que el componente ya no muestra la flecha de actualización, como en este ejemplo, para el componente Aplicación CT-Apps. ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-19.png)
12. En el menú Entorno de la barra de navegación, seleccione **Puesta en escena**.
13. En la cinta **Proyecto**, asegúrese de que el icono Bloqueado está en gris (no bloqueado).

    Sólo tiene que hacerlo una vez.
14. Haga clic en **Componentes** y observe que el componente Aplicaciones de CT Apps muestra la flecha de actualización para v103.
15. En el menú Entorno de la barra de navegación, seleccione **En desarrollo** y, a continuación, haga clic en **Registrar**.

    Se abre el cuadro de diálogo **Check In**.

    Nota: Si el icono de **registro de** la cinta de opciones aparece atenuado, es posible que deba esperar unos minutos a que se procesen los documentos y, a continuación, ir al entorno **de ensayo**, volver al entorno de **desarrollo** e intentarlo de nuevo.
16. Seleccionar todos los elementos del panel izquierdo (por defecto). Esto debería limitarse a los elementos fusionados.
17. Introduzca una descripción de los elementos en el panel **Mensaje**.

    **RECOMENDACIÓN:** Utilice una descripción útil como "Fusión - CTF- Fuente de costes: revertir cambios en el conjunto de datos, componente actualizado"
18. Pulse **Check In**.

    ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-20.png)

    Espere a que finalice la compilación.

    ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-21.png)
19. Verifique que el cambio esperado del paso de fusión de rama se aplica al entorno de puesta en escena.

    En este ejemplo, en la pestaña **Proyecto**, haga clic en **Componentes** para comprobar que v104 está ahora activo.

    ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-22.png)
20. Vuelva a la rama de actualización (por ejemplo, Actualización de la versión 104) para proceder con el siguiente elemento a fusionar.

Problemas conocidos:

- **Mensaje de error** - El primer elemento fusionado debería ser el **cambio de Configuración del proyecto a v104** (o a la versión a la que se esté actualizando). Después de fusionar el elemento, es posible que aparezca un mensaje de error: "Error del servidor: Contacte con su administrador"

  **Solución** - Salga del navegador, vuelva a abrirlo y continúe con el paso de registro en Trunk. Una vez realizado el cambio en la rama de actualización y propagado a la puesta en escena, ya no debería aparecer el mensaje de error.
- **Información contradictoria en la barra de navegación** - Al cambiar entre Trunk y la rama para la nueva plantilla (como Actualización de la versión 104), la nueva rama de actualización podría aparecer en la barra de navegación mientras que el Historial de registros es de Trunk. Si esto ocurre, sigue estos pasos:
  1. Cierre el cuadro de diálogo **Historial de check-in**, y quizás todos los demás cuadros de diálogo.
  2. Cambia a **Tronco**.
  3. Vuelva a la rama de **actualización de la versión 104**.
  4. Vuelva a abrir el **historial de registros**.
  5. Continúe con la fusión en el siguiente paso.
- **Fusionar componentes** desactivados - Después de fusionar un componente desactivado, es posible que los elementos de la fusión anterior sigan apareciendo en el panel izquierdo.

  **Solución** - Introduzca la descripción adecuada para lo que se acaba de fusionar (por ejemplo, "Fusionar - ATUM 2.0 componente desactivado"). Una vez finalizado el cálculo, puede verificar los cambios previstos en la puesta en escena.

## Información relacionada

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
