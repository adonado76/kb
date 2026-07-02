---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Configurar proyectos"
breadcrumb:
  - "Planning"
  - "Planificación de proyectos"
source_path: "it-planning/planning/iip/manage-iip-data-ref.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurar proyectos

Importante: *Disponible con la* *suscripción a* ***Apptio Planning Standard***

Recuerde: *la función de planificación integrada de inversiones (IIP) está habilitada.*

Cuando utilice la Planificación de Proyectos en Apptio Planning, debe configurar la tabla de datos de referencia de Proyectos para habilitar la planificación basada en proyectos. Los proyectos pueden organizarse como una lista plana o dentro de una jerarquía y se utilizan para etiquetar partidas del plan, navegar por los planes por proyecto y asignar permisos de usuario a nivel de proyecto.

## Configurar la planificación de proyectos

Nota: *Para realizar estas tareas se requieren los roles de Administrador o Propietario de Proceso Presupuestario.*

Antes de empezar a introducir partidas de proyecto, tendrá que activar la Planificación Integrada de Inversiones (PII) y configurar los datos de referencia para que los proyectos se comporten de forma coherente en su modelo.

Al habilitar la Planificación Integrada de Inversiones se activan las tablas de Datos de Referencia relacionadas y se añade el desplegable Proyecto para navegar por los planes**.**

**Permitir la planificación de proyectos**

1. Vaya a **Ajustes** (icono de engranaje) **→ Perfil de empresa**.
2. Seleccione **Activar planificación integrada de inversiones.**
3. Haga clic en **Guardar y salir**.

**Configurar datos de referencia del grupo de proyectos**

Los datos de referencia **del Grupo de** Proyectos definen la estructura jerárquica a la que se enrollan los Proyectos. Los grupos de proyectos suelen utilizarse para representar carteras, flujos de valor o programas estratégicos que organizan proyectos relacionados bajo una única capa de gestión o información.

Los Grupos de Proyectos son opcionales si tiene una lista plana de Proyectos.

1. Vaya a **Configuración → Datos de referencia → Grupo de proyectos.**
2. Exporte la plantilla y rellene los campos clave:

   |  |  |  |
   | --- | --- | --- |
   | **Campo** | **Obligatorio** | **Descripción** |
   | Código | x | Un identificador único para el Grupo de Proyectos. Se utiliza como clave para la asignación jerárquica de proyectos. |
   | Nombre | x | Nombre para mostrar del grupo de proyectos (por ejemplo, "Cartera de experiencia del cliente" o "Modernización del centro de datos"). |
   | Código paterno | Condicional | Obligatorio si su jerarquía de Grupo de Proyectos incluye varios niveles (por ejemplo, Flujo de Valor → Cartera → Programa). Dejar en blanco para los grupos de nivel superior. |
   | Código de moneda | Condicional | Obligatorio si está activada la multidivisa. Define la moneda por defecto para todos los proyectos dentro de este Grupo de Proyectos. |
   | Código del centro de costes |  | Centros de coste asociados a este grupo de proyectos. Introduzca los Códigos de Centro de Coste correspondientes, separados por comas. Este campo es opcional: los centros de costes también pueden definirse a nivel de proyecto. |
   | Grupo de precios |  | Campo opcional para agrupar proyectos o servicios similares para la fijación interna de precios o modelos de tarifas. |
3. Importe el CSV actualizado y **publique** los cambios para que estén disponibles para los nuevos planes.

**Configurar los datos de referencia del proyecto**

La tabla de datos de referencia **del proyecto** define todos los **proyectos o inversiones a nivel de hoja** que representan el nivel más bajo de su jerarquía de proyectos. Estos son los registros que asignará a las partidas presupuestarias en Apptio Planning.

1. Vaya a **Configuración → Datos de referencia → Proyecto.**
2. Exporte la plantilla y rellene los campos clave:

   |  |  |  |
   | --- | --- | --- |
   | **Campo** | **Obligatorio** | **Descripción** |
   | Código | x | Un identificador único para el proyecto. Se utiliza como clave para las importaciones de datos, las asignaciones y los informes. |
   | Nombre | x | El nombre para mostrar del proyecto, normalmente el nombre completo del proyecto o de la inversión. |
   | Código paterno | x | El código del grupo de proyectos al que pertenece este proyecto. Define la alineación jerárquica entre Proyectos y Grupos de Proyectos. |
   | Permitir cualquier centro de coste | x | Valor booleano (Verdadero/Falso). Cuando se establece en **Verdadero**, permite que el proyecto se asocie a cualquier centro de coste durante la planificación. Cuando **es False**, restringe la planificación sólo a los centros de coste asignados. |
   | Centro de costes por defecto |  | El centro de costes por defecto asociado al proyecto. Cuando una partida se etiqueta con este proyecto, el centro de coste se rellena automáticamente. Introduzca el Código de Centro de Coste correspondiente. Asegúrese de que este Código de Centro de Coste aparece en el campo Código de Centro de Coste. |
   | Código del centro de costes | x | Centros de coste en los que se incurre en los gastos de este proyecto. Introduzca los Códigos de Centro de Coste correspondientes, separados por comas. |
   | Descripción |  | Campo de texto opcional que describe el objetivo, el alcance o los principales resultados del proyecto. |
   | Gestor de proyectos |  | La persona responsable de la ejecución y entrega diarias del proyecto. |
   | Fecha de inicio |  | La fecha prevista de inicio del proyecto. Puede utilizarse para la elaboración de informes basados en la cronología o el filtrado. |
   | Iniciativa |  | Un campo de agrupación para asociar este proyecto a una iniciativa o programa estratégico de nivel superior. Puede utilizarse para informes o filtros |
   | Tipo de inversión |  | Define el tipo de inversión. Puede utilizarse para informes o filtrado. |
   | Prioridad |  | Indica la prioridad o clasificación del proyecto dentro de la cartera. Útil para informes de PMO o de alineación estratégica. |
   | Propietario del proyecto |  | La persona o función responsable de la financiación, dirección y toma de decisiones del proyecto. |
   | Patrocinador BU |  | La unidad de negocio patrocinadora que financia o se beneficia del proyecto. |
3. Importe el CSV actualizado y **publique** los cambios para que estén disponibles para los nuevos planes.
