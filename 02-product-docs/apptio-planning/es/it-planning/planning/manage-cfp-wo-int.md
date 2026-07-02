---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Gestionar los gastos en la nube (sin integración con CFP)"
breadcrumb:
  - "Planning"
  - "Integraciones"
  - "Conéctate a Cloudability Financial Planning"
source_path: "it-planning/planning/manage-cfp-wo-int.html"
images:
  - "resources/images/it_planning_images/managecfp.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gestionar los gastos en la nube (sin integración con CFP)

Importante: Disponible con la *suscripción* ***al estándar de planificación « Apptio ».***

Recuerde: La nueva vista está habilitada.

La pestaña **«Cloud»** (Nube) de la vista **«Expenses»** (Gastos) se puede utilizar de forma independiente sin la integración CFP para gestionar y realizar un seguimiento del gasto en la nube dentro de los presupuestos y las previsiones.

Para añadir o actualizar los gastos en la nube:

1. Abre tu plan y ve a la pestaña **Nube** dentro de la página **Gastos**.
2. Añade un nuevo gasto en la nube de una de las siguientes maneras:
   - Utilizando la **fila vacía** en la parte inferior de la tabla, o
   - **Hacer clic con el botón derecho** y seleccionar **Insertar fila.**
   - **Importar** los datos utilizando un archivo CSV desde el menú Acciones a nivel de tabla ( *botón de tres puntos*) → Opción **Importar líneas de la nube**.
3. Proporcione la información requerida para cada línea de gastos en la nube:
   - **Centro de costes (obligatorio)** : identifica el departamento o la unidad organizativa responsable financieramente del gasto en la nube.
   - **Cuenta (obligatorio)** : la cuenta contable en la que se registrará el gasto en la nube.
   - **Proveedor (opcional)** : proveedor o proveedor de servicios en la nube. Este campo es útil para la elaboración de informes a nivel de proveedor y el análisis de gastos.
   - **Ubicación (opcional)** : la ubicación geográfica donde se incurrió en el gasto en la nube.
   - **Tipo de coste (opcional)** : disponible cuando se habilita la planificación integrada de inversiones. Clasifica el gasto como **«Construcción»** o «**Ejecución** ». Si se deja en blanco, el sistema asigna automáticamente **Ejecutar** como valor predeterminado.
   - **Proyecto (opcional)** : disponible cuando se habilita la planificación integrada de inversiones. Utilice este campo para asociar el gasto en la nube a un proyecto específico con fines de seguimiento y generación de informes.
   - **Descripción y comentario** : contexto adicional o metadatos sobre la línea de gastos en la nube.

Una vez introducidos, Apptio Planning genera automáticamente el asiento contable correspondiente a cada gasto en la nube en la pestaña **Resumen**. Las líneas de la pestaña Cloud introducidas manualmente pueden coexistir sin problemas junto con las líneas de gastos de Cloud importadas desde Cloud Financial Planning (CFP).

![Gestionar CF sin integración](../../../../../03-media/apptio-planning/resources/images/it_planning_images/managecfp.png)

**Tema principal:** [Conectarse a Cloudability Financial Planning](../../it-planning/planning/connect-cfp.html)
