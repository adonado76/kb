---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Datos de referencia"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
source_path: "it-planning/planning/edit-publish-reference.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Datos de referencia

Nota: Para gestionar los datos de referencia se requieren roles de administrador o responsable del proceso presupuestario.

Los datos de referencia definen las dimensiones principales y los valores de consulta utilizados en toda Apptio la planificación. Estas dimensiones clasifican y contextualizan los datos financieros, laborales, contractuales, de activos y de proyectos, lo que garantiza la coherencia, la precisión y el tratamiento limpio de los datos en todos los planes.

Piense en los datos de referencia como el «vocabulario» que utiliza su entorno de planificación para clasificar costes, recursos, centros de coste, proyectos, departamentos, cuentas y otros atributos clave.

## Cuándo gestionar los datos de referencia

Como administrador o responsable del proceso presupuestario, configurará los datos de referencia cuando:

- Configurar un nuevo entorno o plan
- Incorporar nuevos centros de coste, departamentos, proyectos, proveedores, cuentas u otras entidades
- Necesidad de actualizar códigos de clasificación, añadir nuevos valores o reorganizar jerarquías
- ¿Desea adaptar los datos de referencia a la estructura o al plan contable de su organización?

Estas tareas se realizan en **Configuración > Datos de referencia**. Los cambios en los datos de referencia se aplican automáticamente a todos los planes recién creados. Para aplicar esos cambios a un plan existente, debe ejecutar **Actualizar datos de referencia** para ese plan.

## Dimensiones estándar

Apptio Planificación de buques con un conjunto de «dimensiones estándar» integradas que cubren las necesidades básicas de planificación. La lista exacta puede variar en función de las funciones habilitadas en su entorno.

|  |  |  |
| --- | --- | --- |
| **Categoría** | **Nombre de dimensión** | **Descripción** |
| Finanzas | Cuenta | El campo Cuenta clasifica el tipo de gasto o ingreso que representa una partida, como software, hardware, viajes, salarios o servicios. Las cuentas suelen ajustarse al plan contable de la organización y proporcionan coherencia entre la planificación, la elaboración de presupuestos y la presentación de informes financieros. |
| Categoría de cuenta | La categoría de cuenta agrupa cuentas financieras similares en categorías de informe más amplias (por ejemplo, viajes, instalaciones, salarios) para simplificar la planificación y la presentación de informes. |
| Centro de costes | Un centro de costes representa una unidad organizativa utilizada para realizar un seguimiento y gestionar dónde se incurren los costes. |
| Departamento | Un departamento representa un grupo funcional dentro de la organización. Se utiliza para definir la propiedad y la responsabilidad en Apptio la planificación. |
| Ubicación | El campo Ubicación identifica el sitio geográfico o la región asociada a una partida, como un centro de datos, una oficina o un país. |
| Controlador de varianza | El impulsor de la varianza se utiliza para agrupar y explicar las variaciones mediante la identificación de las causas fundamentales o los factores contribuyentes. |
| Proveedor | El campo «Proveedor» representa a terceros proveedores de servicios o recursos. Se utiliza para realizar un seguimiento y planificar los gastos externos por proveedor. |
| Planificación laboral | Reglas de asignación de mano de obra | Las reglas de asignación de mano de obra definen en qué cuentas GL se contabilizan los costes laborales para un determinado número de empleados. Estas reglas controlan cómo se generan y asignan los gastos laborales en función de atributos como el puesto, el proveedor, la ubicación o el tipo de empleado, lo que garantiza que los datos financieros relacionados con la mano de obra se asignen a las cuentas correctas de forma coherente en todos los planes. |
| Tarifas laborales | Las tarifas laborales recogen las hipótesis sobre las tarifas laborales por atributos tales como función, ubicación, tipo de empleado y proveedor, que se utilizan para la planificación de la plantilla. |
| Rol | El campo «Función» representa las funciones o títulos laborales utilizados en la planificación laboral para aplicar las hipótesis de costes adecuadas. |
| Planificación de contratos | Tipo de contrato | Los valores predeterminados del tipo de contrato especifican los atributos predeterminados para los diferentes tipos de contrato, incluyendo cómo se amortizan los costes y a qué cuentas se asignan. |
| Tipo de IVA | La tasa del IVA define los porcentajes del impuesto sobre el valor añadido que se pueden aplicar a las partidas de contrato elegibles. Los tipos del IVA garantizan que los impuestos se calculen de forma coherente y precisa en todos los planes, basándose en los requisitos fiscales regionales u organizativos. |
| Planificación de activos | Clase de activo | Los valores predeterminados de clase de activos definen la configuración predeterminada de contabilidad y depreciación para diferentes tipos de activos fijos (por ejemplo, hardware, software, mejoras en edificios). |
| Planificación de proyectos | Proyecto | El campo Proyecto representa el trabajo planificado o en curso, como el desarrollo de aplicaciones, las actualizaciones de infraestructura o las iniciativas de transformación empresarial. Asociar los gastos con los proyectos permite a las organizaciones realizar un seguimiento de los costes, la mano de obra y los recursos en relación con inversiones específicas, lo que proporciona visibilidad sobre el gasto total del proyecto y facilita el análisis a nivel de cartera. |
| Grupo de proyecto | El Grupo de Proyectos organiza múltiples proyectos relacionados bajo una estructura común con fines de presentación de informes o elaboración de presupuestos. |
| Planificación de la actividad laboral | Tipo de actividad laboral | El tipo de actividad laboral define cómo se cobran y se transfieren los costes laborales entre los centros de coste cuando se asigna el esfuerzo laboral a los proyectos. Cada tipo de actividad asigna una cuenta de proveedor (departamento) y una cuenta de consumidor (proyecto), lo que garantiza que los gastos de mano de obra se asignen correctamente a las cuentas adecuadas. |
| Función laboral del proyecto | La función Laboral del proyecto especifica las definiciones de las funciones laborales en el contexto de un proyecto, incluidas las tarifas laborales asociadas y la moneda de facturación. |
| Multidivisa | Tipo de cambio real | El tipo de cambio real representa los tipos de cambio utilizados para convertir el gasto real de la moneda de origen a la moneda de destino. |
| Tipo de cambio del plan | El tipo de cambio del plan representa los tipos de cambio utilizados durante el proceso de planificación para convertir los importes planificados de la moneda de entrada de la planificación a la moneda de reporte o corporativa. |

## Dependencias entre dimensiones

Muchas dimensiones son interdependientes, lo que significa que ciertos atributos dependen de valores definidos en otras dimensiones. Por ejemplo:

- Un **departamento** puede hacer referencia a un código **de centro de costes**.
- **Una clase** de **activo o un tipo de contrato** pueden hacer referencia a un código **de cuenta** para la cuenta de depreciación o amortización.
- **Una regla de asignación de mano de obra** puede hacer referencia a un código **de cuenta** para la asignación de costes.

Estas dependencias garantizan la integridad de los datos y una clasificación coherente entre los diferentes tipos de entradas financieras. Al editar o eliminar valores, revise siempre las dependencias para evitar romper referencias.

## Dimensiones personalizadas

Apptio La planificación admite dimensiones personalizadas, lo que le permite ampliar el modelo de datos estándar para capturar atributos específicos de la organización. Puede crear hasta 40 dimensiones personalizadas para satisfacer sus necesidades de planificación y generación de informes.

Para crear y gestionar dimensiones personalizadas, consulte Esquemas.

## Actualización de datos de referencia en un plan

Cuando se crea un plan, este utiliza automáticamente la última versión publicada de los datos de referencia disponibles en ese momento. Si los datos de referencia se actualizan posteriormente, los planes existentes no heredan automáticamente esos cambios. Debe actualizar explícitamente el plan para aplicar los datos de referencia más recientes.

Cómo actualizar los datos de referencia

1. Abre el plan que deseas actualizar.
2. Asegúrese de que está viendo **Todos los departamentos**.
3. Abre los **puntos suspensivos (...) menú** y seleccione **Actualizar datos de referencia**.
4. Revise el **resumen del impacto** que se muestra en la ventana modal de confirmación, que incluye:
   1. Partidas que se actualizarán
   2. Partidas que se eliminarán
   3. Nuevos artículos
   4. Elementos eliminados
   5. Códigos principales modificados
5. Si el impacto parece correcto, seleccione **Actualizar** para aplicar los cambios.

**Notas importantes**

- De forma predeterminada, las actualizaciones que eliminarían elementos de línea existentes se bloquean para evitar la pérdida accidental de datos.
- Para permitir actualizaciones destructivas, un administrador debe habilitar **la opción Desactivar restricciones de datos de referencia de actualización** en el perfil de la empresa.
- Cuando se permiten actualizaciones destructivas, **se crea automáticamente** un plan de copia de seguridad antes de aplicar la actualización de los datos de referencia.

- **[Dimensiones estándar](../../it-planning/planning/manage-reference-data.html)**
