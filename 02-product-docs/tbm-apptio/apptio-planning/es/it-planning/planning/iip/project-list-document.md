---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Gestionar proyectos"
breadcrumb:
  - "Planning"
  - "Planificación de proyectos"
source_path: "it-planning/planning/iip/project-list-document.html"
images:
  - "resources/images/it_planning_images/sync-data.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gestionar proyectos

Nota: Disponible con la Apptio suscripción Planning Standard

Recuerde: *la función de planificación integrada de inversiones (IIP) está habilitada.*

La planificación de inversiones es un proceso continuo impulsado por cambios en las prioridades, las condiciones del mercado y las necesidades de la organización. Aunque los clientes suelen elaborar su presupuesto anual durante la temporada de planificación, deben mantener la flexibilidad para:

- Añadir proyectos recién aprobados o financiados a lo largo del año
- Eliminar proyectos que ya no son relevantes
- Actualizar los atributos del proyecto a medida que evolucionan los planes

La función **Lista de** proyectos permite esta flexibilidad al permitir que determinados usuarios gestionen proyectos directamente dentro de cada plan.

## ¿Quién puede gestionar proyectos?

Los siguientes roles pueden añadir, editar o eliminar proyectos en un plan:

1. **Administrador**
2. **Responsable del proceso presupuestario**
3. **Gestor de cartera de IIP**
4. Usuarios con el **IIPProjectManage** permiso

Los proyectos se tratan como una **dimensión a nivel de plan**, lo que significa que se pueden gestionar de forma independiente dentro de cada plan sin modificar los datos de referencia globales.

## Proyectos globales frente a lista de proyectos a nivel de plan

Apptio La planificación apoya la gestión de proyectos en dos niveles:

**Dimensión global del proyecto (datos de referencia)**

**La dimensión global del proyecto** es la lista maestra de proyectos de todo el sistema. Representa la fuente oficial de información utilizada en toda Apptio la planificación.

**Comportamientos clave:**

- Al crear un plan **sin una línea de base**, todos los proyectos globales se copian en el nuevo plan.
- Los datos reales cargados en la gestión de gastos se validan con respecto a esta dimensión global.
- Si un código de proyecto en los datos reales **no** existe en la dimensión global Proyecto, su valor se borra durante la carga.
- Las actualizaciones de la dimensión global del proyecto **no** se incorporan automáticamente a los planes existentes.

**Lista de proyectos a nivel de plan**

Cada plan contiene su propia **lista de proyectos**, que es una copia local de los proyectos utilizados **únicamente dentro de ese plan**. Esto permite a los propietarios y administradores del presupuesto personalizar el conjunto de proyectos para cada plan anual o previsión sin afectar a la lista maestra global.

**Comportamientos clave:**

- La lista de proyectos se crea durante la creación del plan (ya sea desde la dimensión global o desde el plan de referencia).
- Puede **añadir**, **editar** o **eliminar** proyectos a nivel del plan sin que ello afecte a la dimensión global del proyecto.
- Los cambios personalizados realizados directamente en un plan (por ejemplo, nuevos códigos de proyecto) solo se aplican a ese plan, a menos que se añadan por separado a la dimensión global.
- Las listas de proyectos a nivel de plan siguen el mismo esquema que la dimensión global, lo que garantiza la coherencia entre todos los planes.

## Gestión de proyectos

**La Lista de proyectos** del nivel del plan permite a determinados usuarios añadir, editar o eliminar proyectos dentro de un plan. Estas acciones ayudan a mantener una cartera de proyectos actualizada a lo largo del ciclo de planificación.

**Añadir un proyecto**

1. En el panel de navegación de la izquierda, selecciona **Plan** > **Proyectos**.
2. Esto abre la página «**Lista de proyectos** ».
3. En el menú desplegable **«Planes»**, selecciona el plan al que quieras añadir un nuevo proyecto.
4. Selecciona **Añadir proyecto** (icono +). Aparecerá el cuadro de diálogo **Nuevo proyecto**.
5. Introduzca los detalles del proyecto:
   1. **Código** : identificador único del proyecto dentro del plan seleccionado. *(Obligatorio)*
   2. **Nombre** : nombre del proyecto.
   3. **Código principal** : código del grupo de proyectos principal. Este campo se obtiene de los datos de referencia **del Grupo de Proyectos**.
   4. **Permitir cualquier centro de coste** : active esta opción para permitir que todos los centros de coste realicen cargos al proyecto.
   5. **C** **ódigo del centro de costes predeterminado** : seleccione el centro de costes predeterminado asociado al proyecto.
   6. **C** **ódigo del centro de costes** : seleccione los centros de costes disponibles para su uso en el proyecto.
6. Haga clic en **Añadir** para crear el nuevo proyecto.

**Editar atributos del proyecto**

1. En la Lista de proyectos, selecciona **Editar** (icono del lápiz) junto al proyecto que deseas modificar.

   Aparecerá el cuadro de diálogo **Editar proyecto**.
2. Actualiza los atributos necesarios. Los cambios se guardan automáticamente.

**Eliminar un proyecto**

1. En la Lista de proyectos, seleccione uno o varios proyectos para eliminar.
2. O bien:
   1. Haga clic con el botón derecho para abrir el menú contextual y seleccione **Eliminar**, o
   2. Selecciona **Eliminar proyectos seleccionados** en el menú de puntos suspensivos.

      *Para seleccionar varios proyectos, mantén pulsada la tecla Comando en Mac o la tecla Control en Windows mientras seleccionas las filas.*
3. Si alguno de los proyectos seleccionados se utiliza en líneas de gastos, aparecerá un cuadro de diálogo de confirmación.
4. Seleccione **Confirmar** para continuar.

**Notas importantes sobre la eliminación de proyectos**

- Al eliminar un proyecto, este se elimina de la **lista de proyectos** del plan.
- Se eliminarán todas las líneas de gastos en las que **«Proyecto»** sea un *atributo obligatorio* (por ejemplo, **«Actividad laboral»** ).
- En las líneas de gastos en las que el proyecto *no* es obligatorio (por ejemplo, **contratos**, **activos**, **otros gastos** y **mano de obra** ), se borrará el valor del proyecto, pero la línea de gastos permanecerá.

**Importar lista de proyectos**

Puede importar datos del proyecto utilizando un archivo.csv.

1. Selecciona **Importar desde archivo** en el menú de puntos suspensivos.
2. Cargue el archivo.csv.

   **Importante:**
   - La importación permite **añadir nuevos proyectos** y **actualizar los atributos de los proyectos existentes**.
   - **No se admite la eliminación de proyectos mediante importación.**

   Para importar la lista de proyectos desde el cálculo de costes de Apptio, consulte [Importar la lista de proyectos desde el cálculo de costes](../import-pl-acost.html) de Apptio.

**Exportar lista de proyectos**

Para exportar la lista de proyectos:

1. Seleccione **Exportar a archivo** en el menú de puntos suspensivos.
2. El sistema descarga la lista de proyectos como un archivo.csv.

**Publicar lista de proyectos en datos de referencia**

Para publicar la lista de proyectos a nivel de plan, vaya a Configuración > Datos de referencia > Proyecto:

1. Seleccione **Publicar en datos de referencia** en el menú de puntos suspensivos.
2. La lista de proyectos se importa a los datos de referencia del proyecto.
3. Publicar los datos de referencia del proyecto para que los planes dispongan de datos de referencia actualizados.

## Sincronización de proyectos globales y a nivel de plan

Porque los planes hacen referencia a su propia lista de proyectos local:

- Los cambios en los proyectos globales **no se propagan automáticamente** a los planes existentes.
- Para obtener actualizaciones globales (añadidos/eliminaciones/cambios de atributos), utilice **Proyectos > Lista > Actualizar datos del proyecto**.
- El proceso de actualización añadirá, eliminará o modificará proyectos a nivel de plan en función de los cambios realizados en los datos de referencia globales del proyecto.

Esto garantiza que cada plan se mantenga estable a lo largo del ciclo de planificación, al tiempo que sigue ofreciendo a los administradores control cuando evolucionan las definiciones de los proyectos.

![Sincronización de datos de imagen](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/sync-data.png)

**Cómo se aplican los cambios en el proyecto**

Cuando ejecuta **Actualizar datos del proyecto** en un plan, Apptio compara la Lista de proyectos del plan con la dimensión global **Datos de referencia > Proyecto** y aplica los cambios según las reglas que se indican a continuación.

1. **Se ha eliminado un proyecto de los datos de referencia globales, pero sigue existiendo en el plan.**

   Si se elimina un proyecto de la dimensión global Proyecto, se producen los siguientes cambios cuando se aplica la actualización:
   - **Las líneas de actividad laboral** asociadas a ese proyecto se eliminan, incluyendo todas las finanzas relacionadas con la actividad laboral.
     - Estos aparecen como *líneas que se deben eliminar* en el cuadro de diálogo de confirmación.
   - En las líneas de gastos **de** mano de obra, contratos, activos y otros, en las que el proyecto *no* es un atributo obligatorio, se borra el valor del proyecto.
     - Estos aparecen como *líneas que deben actualizarse*.
   - El proyecto se elimina de la lista de proyectos del plan.
2. **Se añade un nuevo proyecto a los datos de referencia globales.**

   Si un proyecto existe globalmente pero no en el plan:
   - El nuevo proyecto se añade a la lista de proyectos del plan.
3. **Se ha creado un proyecto solo en el plan (no globalmente).**

   Si un proyecto existe en el plan pero no en los datos de referencia globales:
   - Ese proyecto se elimina del plan durante la actualización.
   - Cualquier impacto en los gastos sigue las mismas reglas descritas en **el Escenario 1** (eliminación de proyectos).
4. **Se elimina un centro de costes de un proyecto en los datos de referencia globales.**

   Si se elimina un centro de coste de un proyecto a nivel global, pero sigue asignado en el plan:
   - Se eliminan todas **las líneas de actividad laboral** que utilizan esa combinación de proyecto/centro de costes, junto con sus datos financieros.
   - Para cualquier otro tipo de gasto en el que se requiera un centro de coste, se borra el valor del proyecto y el gasto se reasigna al departamento.
   - Estas acciones aparecen como *líneas que se deben eliminar* o *actualizar* en el cuadro de diálogo de confirmación.

   Importante: Si desea conservar los gastos asociados a un centro de costes antes de eliminarlo de un proyecto, reasigne dichos gastos a un centro de costes válido antes de aplicar la actualización.
5. **Conflictos con otras actualizaciones de datos de referencia pendientes**

   Si hay actualizaciones pendientes para otras dimensiones de datos de referencia (como Centro de costes o Grupo de proyectos), la actualización del proyecto se **bloqueará** para evitar conflictos. Un mensaje le indicará que aplique primero esas actualizaciones.
