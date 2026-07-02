---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Creación de planes"
breadcrumb:
  - "Planning"
  - "Creación y gestión de planes"
source_path: "it-planning/planning/create-plan.html"
images:
  - "resources/images/icons/icon-add.png"
  - "resources/images/it_planning_images/settings-icon.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Creación de planes

Nota: Para gestionar planes se requieren los roles de Administrador o Propietario de Proceso Presupuestario.

Apptio La planificación permite crear y gestionar planes financieros que apoyan tanto la presupuestación como la previsión. Los planes proporcionan un espacio de trabajo central para elaborar presupuestos, ajustar previsiones y alinear inversiones entre departamentos, proyectos y recursos.

## Tipos de planes

Apptio La planificación admite dos tipos de planes:

- **Plan presupuestario:** un plan sin datos reales. Todos los periodos son editables, lo que le permite elaborar un plan desde cero o restablecer proyecciones sin datos históricos.
- **Plan de previsiones** - Un plan que incluye los datos reales de períodos históricos (procedentes de la Gestión de gastos). Sólo son editables los periodos futuros, por lo que puede ajustar las proyecciones en función de los resultados pasados.

## Crear un plan

1. En el menú de navegación, seleccione **Planificación** > **Planes**
2. Seleccione el botón ![añadir botón](../../../../../03-media/apptio-planning/resources/images/icons/icon-add.png) .
3. Elija un **tipo de plan** (Presupuesto o Previsión)
4. Introduzca los siguientes datos:

   |  |  |
   | --- | --- |
   | **Elemento** | **Descripción** |
   | Año de inicio del plan | Seleccione el año de inicio del plan. |
   | Plan Longitud | Seleccione la duración del plan (hasta diez años). |
   | Período inicial de previsión  (Sólo previsiones) | Seleccione el primer periodo editable para la previsión. Los periodos históricos se rellenarán previamente con datos reales. Para crear un plan de previsión utilizando únicamente datos reales para la duración del plan seleccionado, seleccione **Ninguno** como Período de inicio de la previsión. |
   | Referencia básica | Opcionalmente, copie los datos de un plan existente para utilizarlos como referencia. |
   | Copia de códigos de partidas individuales | Elija copiar los Códigos de Partida de la línea de base o generar nuevos códigos.  Más información sobre [los códigos de partidas individuales](line-item-codes.html). |
   | Rellenar automáticamente los datos del plan | Si la base de referencia y el nuevo plan incluyen ejercicios fiscales diferentes, esta opción rellena los valores que faltan con los datos del último año de la base de referencia. |
   | Nombre del plan | Introduzca un nombre único para el plan. |
5. Haga clic en el botón **Crear plan**.

   Cuando se inicia la creación del plan, éste aparece en la página Planes con el estado **Pendiente**. Una vez completado, verá un mensaje de confirmación y el plan estará disponible para su selección en Planificación.

   Nota: La creación de un plan a partir de una línea de base puede tardar varios minutos si se están copiando grandes volúmenes de datos.

## Módulos del plan

Los planes pueden ampliarse con módulos adicionales para cubrir diversas necesidades de planificación:

- **Planificación financiera** - Planificar los gastos de explotación ( OpEx ) y los gastos de capital ( CapEx ). Este módulo está activado por defecto en todos los planes.
- **Planificación de la mano de obra** - Planifique la plantilla y los costes de la mano de obra.
- **Planificación de contratos** - Planifique los contratos de proveedores con opciones de amortización.
- **Planificación de** activos - Planifique la compra y amortización de activos.
- **Planificación de proyectos** - Planifique los gastos del proyecto (construcción vs. ejecución).
- **Planificación de la actividad laboral de los** proyectos - Capture el esfuerzo y los costes laborales de los proyectos.

**Para habilitar módulos** :

1. En la parte superior derecha, vaya a **Configuración** (![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/settings-icon.jpg) ) > **Perfil de empresa**.
2. Seleccione los módulos que desea activar:
   - Plantilla laboral
   - Contratos
   - Activos
   - Permitir la planificación integrada de las inversiones
   - Actividad laboral (requiere Planificación Integrada de Inversiones)
