---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Resumen de la planificación de la actividad laboral"
breadcrumb:
  - "Planning"
  - "Planificación de la actividad laboral del proyecto"
source_path: "it-planning/planning/iip/labor-resource-planning.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Resumen de la planificación de la actividad laboral

Importante: *Disponible con la* *suscripción a* ***Apptio Planning Standard***

Recuerde: *la función de planificación integrada de inversiones (IIP) está habilitada.*

**La planificación de la actividad laboral** permite a las organizaciones planificar el esfuerzo laboral necesario para los proyectos por horas o ETC, al tiempo que admite el cobro cruzado, la asignación de costes laborales y la visibilidad de las asignaciones excesivas o insuficientes en los recursos del proyecto.

Cuando se habilita la función Planificación integrada de inversiones (IIP), hay dos atributos de mano de obra opcionales disponibles en **Gastos** → **Mano de obra** :

- **Función laboral del proyecto**
- **Tipo de actividad laboral**

## Habilitar la planificación de actividades laborales

Nota:

- *Para realizar estas tareas se requieren los roles de administrador o responsable del proceso presupuestario.*
- La función **de planificación integrada de inversiones (IIP)** debe estar habilitada *antes de* poder activar la actividad laboral.

Antes de que los usuarios puedan asignar el esfuerzo laboral en la pestaña **Gastos** → **Actividad laboral**, se debe habilitar la Planificación de la actividad laboral en el Perfil de la empresa.

**Pasos para habilitar la planificación de la actividad laboral**

1. Ve al icono de **Ajustes (en forma de engranaje)** → **Perfil de la empresa**.
2. Asegúrese de que **la planificación integrada de inversiones (IIP)** esté habilitada primero; la actividad laboral no se puede activar sin ella.
3. Habilitar **actividad laboral**.
4. Elija si desea **evitar la sobreasignación** o **permitir la sobreasignación** de los recursos laborales.
5. **Evitar la sobreasignación:** El sistema bloqueará las asignaciones que superen la capacidad de recursos disponible.
6. **Permitir sobreasignación:** El sistema permitirá asignaciones por encima de la capacidad.
7. Si se permite la sobreasignación, especifique el **porcentaje de sobreasignación/subasignación** permitido.

Una vez habilitada, la pestaña **Actividad laboral** estará disponible para planificar la mano de obra del proyecto.

## Función y tarifa laboral del proyecto

Los datos de referencia **de las funciones laborales del** proyecto definen las funciones específicas del proyecto utilizadas para los recursos laborales internos o externos, junto con las tarifas laborales por hora aplicadas cuando dichos recursos facturan horas a un proyecto.

Esta dimensión permite planificar la mano de obra a nivel de proyecto, ya que las organizaciones pueden asignar funciones de RR. HH. a funciones específicas del proyecto y establecer tarifas de reembolso o de cargo cruzado adecuadas. Por ejemplo, a un empleado con una función de RR. HH. de desarrollador de software 2 se le puede asignar la función laboral del proyecto de desarrollador cuando trabaje en un proyecto.

Para obtener detalles sobre la configuración, consulte [Funciones laborales](manage-project-labor-role-data-ref.html) del proyecto.

## Tipo de actividad laboral

Los datos de referencia **del tipo de actividad laboral** definen la correspondencia entre la cuenta del centro de costes del departamento (el proveedor) y la cuenta del centro de costes del proyecto (el consumidor) para un tipo de actividad determinado. Este mapeo determina cómo fluyen los cargos laborales y los cargos cruzados entre los centros de costos.

Los tipos de actividad laboral se utilizan durante la planificación de actividades laborales para:

- Identificar qué centro de costes proporciona la mano de obra
- Identificar qué proyecto o centro de costes consume la mano de obra
- Asignar los importes correspondientes de los cargos y contracargos a las cuentas correctas del proveedor y del consumidor

Para obtener detalles sobre la configuración, consulte [Tipo](manage-labor-activity-type-data-ref.html) de actividad laboral.

## Asignación de funciones laborales y planificación del esfuerzo del proyecto

La planificación de la actividad laboral es un proceso de dos pasos. En primer lugar, asigne un recurso de mano de obra a una **función laboral del proyecto** en la pestaña **Mano de obra**. A continuación, planifica el esfuerzo del proyecto del recurso (horas o FTE) en la pestaña **Actividad laboral**.

Solo los recursos laborales con una función laboral asignada al proyecto aparecerán como **recursos** en la pestaña **Actividad laboral**.

**Paso 1: Asignar una función y una tarifa laboral al proyecto (pestaña «Labor»)**

Para establecer la función del recurso en el proyecto y la tarifa facturable:

1. Vaya a **Gastos** → **Mano de obra** y cree o edite una línea de recursos de mano de obra.
2. Seleccione la **función laboral del proyecto** en el menú desplegable.
3. **La tarifa laboral** del proyecto se rellena automáticamente en función de los datos de referencia.

***Comportamientos importantes:***

- Al seleccionar una **función laboral del proyecto,** se establece automáticamente la **tarifa laboral del proyecto**.
- Puede anular la tarifa predeterminada.
- Si un recurso laboral **no** se factura a un proyecto, puede dejar en blanco los campos «Función laboral del proyecto» y «Tarifa».
- Los cargos cruzados por mano de obra se generan en la pestaña **Resumen** utilizando Precio x Cantidad (Horas).

**Paso 2: Asignar horas o ETC a los proyectos (pestaña Actividad laboral)**

La pestaña Actividad laboral le permite planificar el esfuerzo laboral para los proyectos por **función laboral del proyecto** o por **recurso designado**. Los recursos que se muestran en esta pestaña se filtran en función de las asignaciones de funciones laborales del proyecto realizadas en **Gastos** → **Mano de obra**.

Siga los pasos que se indican a continuación para asignar mano de obra a un proyecto:

1. **Seleccionar el proyecto** : en la pestaña **Actividad laboral**, elija el **proyecto** para el que desea planificar la mano de obra.
2. **Elija cómo asignar los recursos** : puede asignar la mano de obra de dos maneras:
   1. **Por función laboral en el proyecto**
   2. **Por recurso designado**
3. **Seleccionar una función laboral en el proyecto**
   1. Seleccione la **función laboral del proyecto** en el menú desplegable.
   2. **La tarifa laboral** del proyecto se completará automáticamente en función de los datos de referencia de la función laboral del proyecto.
   3. Puede anular la tarifa si es necesario.
4. **Seleccionar un recurso con nombre (opcional)**
   1. En la dimensión **Recurso**, elija un recurso con nombre para asignarlo.
   2. La lista de recursos se filtra automáticamente para mostrar solo aquellos asignados a la **función laboral** seleccionada en la pestaña «Labor».
      1. Utilice la dimensión **Centro de costes de recursos** para limitar la lista a los recursos que pertenecen a un centro de costes específico.
      2. Nota: No es posible realizar la asignación de recursos cuando un **centro de costes de recursos** se encuentra en estado **enviado** o **bloqueado**. Cualquier intento de modificar o asignar un centro de coste de recursos que ya se haya enviado o bloqueado dará lugar a un error de validación, y el cambio no se guardará.
5. **Seleccione el tipo de actividad** : si la mano de obra es facturable o se cobra de forma cruzada:
   1. Elija el **tipo de actividad** adecuado.
   2. Esto determina cómo se asignan los cargos y los cargos cruzados entre las cuentas del proveedor y del consumidor en función de las asignaciones de tipos de actividad laboral.
6. **Introduzca el esfuerzo en horas o ETC**
   1. Introduzca el esfuerzo laboral requerido en **horas mensuales** o **ETC**.
   2. El esfuerzo introducido determinará los cálculos de los costes laborales.
7. **Revisar los costes de mano de obra** : los costes de mano de obra se calculan utilizando **el precio × la cantidad** en función de la función de mano de obra del proyecto seleccionada, la tarifa de mano de obra, el tipo de actividad y las reglas de asignación. Los importes resultantes aparecen en la pestaña **Resumen**, donde el centro de costes del proveedor recibe un abono y el centro de costes del consumidor recibe un cargo.
