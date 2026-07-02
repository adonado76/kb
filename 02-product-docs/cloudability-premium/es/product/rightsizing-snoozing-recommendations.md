---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Recomendaciones sobre el tamaño de la cama"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/rightsizing-snoozing-recommendations.html"
images:
  - "images/snooze_rs1.jpg"
  - "images/snooze_rs2.jpg"
  - "images/snooze_rs3.jpg"
  - "images/snooze_rs4.jpg"
  - "images/snooze_rs5.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Recomendaciones sobre el tamaño de la cama

Si es necesario, puede aplazar las recomendaciones de dimensionamiento para recursos específicos cuando se haya determinado que no se va a realizar ninguna acción sobre el recurso en este momento. Esto puede ayudar a mejorar la eficacia a la hora de revisar y poner en práctica las recomendaciones de reajuste, ocultando dichas recomendaciones.

Antes de empezar

Para poder aplicar las recomendaciones de dimensionamiento, necesitará los permisos administrativos adecuados.

[Roles y permisos en Cloudability](../admin/iam.html)

Acceder al cuadro de mandos de Rightsizing

Para acceder al panel de Rightsizing, abra la página de inicio Cloudability y, en el menú de navegación de la izquierda, seleccione Optimizar > Rightsizing. El panel de Rightsizing muestra la pestaña Explorador por defecto, sin embargo las capacidades de snoozing están disponibles para los servicios bajo las pestañas de proveedores también.

Recomendaciones para dormir

Para iniciar las recomendaciones de snooze, haz clic en el conmutador de Modo Snooze en la esquina superior derecha de la página de Derechos para activar el Modo Snooze.

![captura de pantalla del modo snooze](../../../../03-media/cloudability-premium/images/snooze_rs1.jpg)

Una vez activado el modo snooze, habrá varios métodos disponibles para hacer snooze a las recomendaciones.

Método (a granel)

1. A partir de ahora habrá un botón «Posponer todo» en la esquina superior derecha de la tabla de recomendaciones. ![icono snooze all](../../../../03-media/cloudability-premium/images/snooze_rs2.jpg)
2. A partir de ahora, la tabla de recomendaciones mostrará también una columna adicional (con casillas de selección) como primera columna de la tabla.![icono adicional](../../../../03-media/cloudability-premium/images/snooze_rs3.jpg)
3. Para snooze recomendaciones, tampoco:
   - Haga clic en el botón Posponer todo para posponer todas las recomendaciones de los recursos de la tabla.
   - Marque la casilla de las recomendaciones que desea aplazar y haga clic en el botón Aplazar seleccionados (x) para aplazar sólo las recomendaciones de los recursos seleccionados.![icono snooze seleccionado](../../../../03-media/cloudability-premium/images/snooze_rs4.jpg)
4. Aparecerá un modal que le permitirá elegir la duración del snooze de las recomendaciones. Haga clic en Enviar para aplazar las recomendaciones o en Cancelar para anularlas.

Método (individual)

1. Haz clic en los puntos suspensivos para ver una recomendación y abrir el submenú de recomendaciones. ![pantalla del submenú de recomendaciones](../../../../03-media/cloudability-premium/images/snooze_rs5.jpg)
2. Para snooze recomendaciones, tampoco:
   - Haz clic en la opción del submenú Snooze.
   - Haga clic en el submenú Ver detalles y, en la esquina superior derecha del panel Detalles, haga clic en el icono Posponer.
3. Aparecerá un modal que le permitirá elegir la duración de la recomendación. Haga clic en Enviar para aplazar las recomendaciones o en Cancelar para anularlas.

Recomendaciones para desestresarse

Para des-snooze recomendaciones:

1. Haga clic en el menú desplegable Opciones en la parte superior de la página Redimensionamiento y seleccione Mostrar recursos snoozed.
2. La tabla de recomendaciones mostrará ahora las recomendaciones que están actualmente pospuestas..![icono de repetición](../../../../03-media/cloudability-premium/images/snooze_rs3.jpg)
3. Para anular las recomendaciones de un recurso, siga el mismo proceso que para anular las recomendaciones:
   - Haga clic en el botón Desactivar todas para desactivar todas las recomendaciones para los recursos de la tabla.
   - Marque la casilla de verificación de las recomendaciones que desea eliminar y haga clic en el botón Eliminar recomendaciones seleccionadas (x) que aparece para eliminar sólo las recomendaciones de los recursos seleccionados.
   - Haga clic en las elipses de una recomendación que se haya repetido para abrir el submenú de recomendaciones y haga clic en la opción Despeticionar para cancelar las recomendaciones.
   - Haga clic en los puntos suspensivos de una recomendación pospuesta para abrir el submenú de recomendaciones, haga clic en el elemento del submenú Ver detalles y, en la parte superior del Panel de detalles, en la esquina superior derecha, haga clic en el ícono Dejar de posponer.

Editar la duración de las recomendaciones snoozeadas

Para editar la duración de las recomendaciones repetidas:

1. Haga clic en el menú desplegable Opciones situado en la parte superior de la página Asignación de derechos y seleccione Mostrar recomendaciones rezagadas
2. La tabla de recomendaciones mostrará ahora las recomendaciones que están actualmente en snooze.
3. Haga clic en las elipses de una recomendación para abrir el submenú de recomendaciones.
4. En el submenú, seleccione la opción Editar repetición (la edición de la duración de una repetición también se puede hacer desde el panel de detalles con el icono de edición de repetición en la esquina superior derecha).
5. Aparecerá un modal que le permitirá elegir la duración de la recomendación. Haga clic en Enviar para aplazar las recomendaciones o en Cancelar para anularlas.

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
