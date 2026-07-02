---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Funciones de los trabajadores del proyecto"
breadcrumb:
  - "Planning"
  - "Planificación de la actividad laboral del proyecto"
source_path: "it-planning/planning/iip/manage-project-labor-role-data-ref.html"
images:
  - "resources/images/it_planning_images/three-dots.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Funciones de los trabajadores del proyecto

Importante: Disponible con la *suscripción* ***Apptio Planning Standard.***

Recuerde: *la función de planificación integrada de inversiones (IIP) está habilitada.*

Los datos de referencia **de las funciones laborales del** proyecto definen las funciones específicas del proyecto utilizadas para los recursos laborales internos o externos, junto con las tarifas laborales por hora aplicadas cuando dichos recursos facturan horas a un proyecto.

Esta dimensión permite planificar la mano de obra a nivel de proyecto, ya que las organizaciones pueden asignar funciones de RR. HH. a funciones específicas del proyecto y establecer tarifas de reembolso o de cargo cruzado adecuadas. Por ejemplo, a un empleado con una función de RR. HH. de desarrollador de software 2 se le puede asignar la función laboral del proyecto de desarrollador cuando trabaje en un proyecto.

## Configurar funciones laborales del proyecto

***Nota:*** *Para realizar estas tareas se requieren los roles de administrador o responsable del proceso presupuestario.*

1. En el menú de navegación, vaya a **Configuración** → **Datos de referencia** → **Dimensiones estándar** → **Función laboral del proyecto**.
2. Exporta la plantilla y rellena los campos clave:

   |  |  |
   | --- | --- |
   | **Campo** | **Descripción** |
   | **Nombre** | El nombre que se muestra de la función laboral del proyecto. Esto es obligatorio. |
   | **Moneda** | El código de moneda para la tarifa laboral. Requerido cuando se habilita la compatibilidad con múltiples divisas en *el perfil de la empresa*. Si se deja en blanco, el sistema utiliza la moneda común predeterminada. |
   | **Tarifa laboral del proyecto** | La tarifa por hora asociada al puesto laboral del proyecto. Admite valores decimales. Se utiliza para cargos cruzados por mano de obra. |
   | **Origen** | El origen del rol laboral (por ejemplo, *interno*, *externo*, *nombre del proveedor* ). Ayuda a distinguir la atribución del trabajo entre múltiples modelos de abastecimiento. |
3. Importar el CSV actualizado
4. Haga clic en ![menú de elipses](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/three-dots.jpg) y **publique** los cambios para que estén disponibles para los planes.

## Cómo se utilizan las funciones laborales del proyecto

Las funciones laborales del proyecto se utilizan en **la planificación de actividades laborales**, donde las organizaciones asignan recursos laborales a funciones específicas del proyecto para estimar el esfuerzo y el coste.

- **Asignación de funciones específicas para cada proyecto:**

  Las funciones de RR. HH. pueden no reflejar cómo se distribuye la mano de obra en los proyectos. Las funciones laborales del proyecto le permiten definir categorías de funciones relacionadas con el proyecto (por ejemplo, desarrollador, analista, arquitecto).
- **Planificación del esfuerzo laboral:**

  Durante la planificación del proyecto, se pueden asignar horas o ETC a las funciones laborales del proyecto para estimar el esfuerzo laboral.
- **Cargo cruzado o aplicación de tasa interna:**

  Las tarifas por hora asignadas a las funciones laborales del proyecto determinan el coste que se cobra a los proyectos por utilizar los recursos de esa función.
