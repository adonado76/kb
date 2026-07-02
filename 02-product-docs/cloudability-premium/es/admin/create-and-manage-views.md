---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Crear y gestionar vistas"
breadcrumb:
  - "Cloudability Premium"
  - "Administración"
source_path: "admin/create-and-manage-views.html"
images:
  - "images/Add-View-new.png"
  - "images/create_and_manage_views_4.jpg"
  - "images/manage-view.jpg"
  - "images/specified-dimensions.png"
  - "images/view_clone_duplicate.png"
  - "images/views_show_default_usage.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Crear y gestionar vistas

## Visión general

View en Cloudability es una potente herramienta de filtrado de datos para organizar y controlar cómo se presentan y comparten los datos de costes y uso de la nube entre los usuarios de Cloudability para su organización. Actúan como filtros para toda la aplicación que le ayudan a centrarse en los datos que más importan.

Con Views, puedes:

- Filtre y segmente los datos por cuentas, proveedores, etiquetas, grupos de cuentas o asignaciones empresariales.
- Controle la visibilidad compartiendo algunos datos ampliamente y restringiendo la información sensible a usuarios o grupos específicos.
- Aumente la flexibilidad permitiendo a los administradores crear múltiples vistas, como datos de costes por unidad de negocio o entorno.

Los administradores pueden configurar las vistas con diferentes parámetros de uso compartido (privado, toda la organización o usuarios/grupos específicos) para garantizar el nivel adecuado de acceso a los datos por parte de los usuarios adecuados. Cada vista ofrece una perspectiva personalizada de sus recursos en la nube, lo que permite a los equipos analizar los costes, optimizar el uso y tomar decisiones informadas.

**Ejemplos de casos de uso:**

- Un equipo financiero necesita una Vista para supervisar **los gastos mensuales por proveedor** en todas las cuentas.
- Un responsable de una unidad de negocio necesita una Vista para realizar un seguimiento de **la asignación de costes por departamento**.
- Un equipo de DevOps necesita disponer de una Vista para analizar **los costes de computación en los entornos de producción frente a los de ensayo**.

## Procedimiento

## Crear una vista

1. Vaya a Organizar > Vistas.
2. Seleccione Nueva vista. Se abre el panel Añadir una vista.

   ![añadir vistas captura de pantalla](../../../../03-media/cloudability-premium/images/Add-View-new.png)
3. En el campo Nombre, introduzca un nombre para la vista.
4. En el campo Descripción, describa el propósito de su vista.
5. En la sección Privacidad, indique su configuración de privacidad.

   - Selecciona Privado para evitar que otros accedan a tu vista.
   - Seleccione Toda la organización para que la vista sea accesible a todos los usuarios y administradores no restringidos de la organización.
   - Seleccione los Individuos para compartir su vista con usuarios específicos. Utilice el menú desplegable Compartido con para seleccionar usuarios específicos con los que compartir la vista.

   Nota:

   Cuando a los usuarios se les asigna una vista, no pueden ver ningún dato hasta que tengan el ViewsFeatureFullAccess permiso. Para más información, visite [Gestión de permisos y funciones de los usuarios](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(se abre en una pestaña o una ventana nueva)")
6. En la sección Filtros, seleccione el botón Añadir filtro para restringir el alcance de la vista.

   1. En el campo Medida, seleccione la dimensión que desea incluir en el argumento del filtro.
   2. En el campo Operador, seleccione el operador para el filtro, por ejemplo igual a.
   3. En el campo Valor, escriba una cadena de texto para utilizarla como valor a filtrar.
   4. Seleccione Enviar.
   5. Por ejemplo, este filtro limita el alcance de la vista a la Unidad de Negocio denominada ingeniería.

   ![vistas de filtro captura de pantalla](../../../../03-media/cloudability-premium/images/create_and_manage_views_4.jpg)
7. (Opcional) Si desea incluir otro filtro en la vista, vuelva a seleccionar Añadir filtro. Al introducir varios argumentos de filtro en una misma vista, el sistema inferirá un O implícito entre la misma dimensión y un Y implícito entre dos dimensiones distintas.

## Duplicar una vista

Como **administrador de vistas**, a menudo necesita crear varias vistas que compartan filtros y permisos similares. Recrear manualmente cada vista aplicando los mismos filtros y ajustes puede llevar mucho tiempo y resultar repetitivo. Con la función **Vista duplicada**,

- Puede clonar o duplicar una vista con un solo clic.
- Se copiarán todos los filtros, permisos y configuraciones.
- Basta con cambiar el nombre de la vista y realizar los ajustes necesarios.

Esta función le ayuda a ahorrar tiempo, reducir errores y facilitar la personalización y organización de Vistas para sus equipos.

1. Para duplicar, vaya a Organizar > Vistas.
2. Haga clic en la elipsis (...) en la fila de la vista que desea clonar/duplicar y seleccione Duplicar.
3. Esto abrirá un panel lateral con todos los datos rellenados previamente con la información. Basta con cambiar el nombre de la vista y realizar los ajustes necesarios en las condiciones de filtrado y los permisos.

![Clonar duplicar una vista](../../../../03-media/cloudability-premium/images/view_clone_duplicate.png)

## Gestionar una vista existente

Puede editar, compartir y eliminar vistas existentes en Cloudability.

Editar una vista

1. Vaya a Organizar > Vistas.
2. Haga clic en la elipsis (...) en la fila de la vista que desea editar y seleccione Editar.
3. Si desea editar varias vistas a la vez, seleccione las casillas de verificación situadas a la izquierda de las vistas y, a continuación, seleccione el icono EDITAR MÚLTIPLE. Se abrirá el panel Editar una vista.

## Borrar una vista

Cuando se elimina una vista, se aplica el siguiente comportamiento a los usuarios que la tienen configurada como vista predeterminada:

- Si se elimina una vista predeterminada (incluida una HV), la vista predeterminada del usuario volverá automáticamente a la **vista predeterminada a nivel de la organización**.
- Si no existe un valor predeterminado a nivel de organización, la vista predeterminada se establecerá en **blanco**.
- Ahora aparece **una** advertencia al eliminar una vista para informar a los administradores de que puede afectar a los valores predeterminados de los usuarios.

Antes de eliminar, los administradores pueden ver quién está utilizando una vista específica como predeterminada a través de: **Vista → Mostrar uso predeterminado**. Además, los usuarios pueden actualizar su vista predeterminada en cualquier momento a través de: **Administrar perfil → Preferencias**.

**Para eliminar una vista:**

1. Vaya a Organizar > Vistas.
2. Haga clic en la elipsis (...) en la fila de la vista que desea eliminar y seleccione Eliminar.
3. Si desea eliminar varias vistas a la vez, seleccione las casillas de verificación situadas a la izquierda de las vistas y, a continuación, seleccione el icono Eliminar vistas.

## Cambiar los permisos de privacidad de una vista compartida existente

Los autores de vistas pueden cambiar los permisos (aumentar o disminuir) de una vista compartida existente. Sin embargo, cuando se reducen o eliminan los permisos, se aplica el siguiente comportamiento:

- Si se elimina el acceso del usuario a una vista predeterminada (incluida una HV), la vista predeterminada del usuario volverá automáticamente a **la vista predeterminada a nivel de la organización**.
- Si no existe un valor predeterminado a nivel de organización, la vista predeterminada se establecerá en **blanco**.
- Ahora aparece una **advertencia** al modificar sus permisos para informar a los administradores de que puede afectar a los valores predeterminados de los usuarios.

Antes de modificar los permisos, los administradores pueden ver quién utiliza una vista específica como predeterminada a través de: **Vista → Mostrar uso predeterminado**. Además, los usuarios pueden actualizar su vista predeterminada en cualquier momento a través de: **Administrar perfil → Preferencias**.

Para cambiar el permiso:

1. Vaya a Organizar > Vistas.
2. Haga clic en la elipsis (...) en la fila de la vista que desea editar.
3. Cambia el permiso entre "Privado", "Toda la organización" e "Individuos".

## Identificar usuarios utilizando la vista por defecto

Antes de eliminar o restringir el acceso a una vista, los administradores ahora pueden ver quién la utiliza activamente como vista predeterminada, lo que les ayuda a tomar decisiones informadas a la hora de restringir los permisos de la vista o eliminarla. La función muestra exactamente qué usuarios dependen de una vista específica como predeterminada, ya sea que se haya compartido directamente, a través de grupos de usuarios, grupos de Entra ID o con toda la organización.

1. Utilizando la opción 'Mostrar uso por defecto':
   1. Vaya a Organizar > Vistas.
   2. Haga clic en la elipsis (...) en la fila de la vista y seleccione "Mostrar uso por defecto".
   3. En el panel lateral, verás la lista de usuarios que utilizan esta vista como vista predeterminada.![mostrar usuarios vista por defecto](../../../../03-media/cloudability-premium/images/views_show_default_usage.png)
2. Utilizando la función de exportación de « CSV »:
   1. Vaya a Organizar > Vistas.
   2. Utilice el botón "Exportar" para descargar la lista de todas las vistas.
   3. En el « CSV », la columna **«View Default Users»** muestra todos los usuarios que han establecido esa vista como predeterminada.

## Establecer una vista por defecto

Tu vista por defecto es la que ves cuando te conectas por primera vez, y también se aplica a tus correos electrónicos diarios de Cloudability. Para configurar la vista por defecto:

1. Haga clic en el icono de su perfil en la parte superior derecha y, a continuación, en Gestionar perfil.
2. En su página Perfil, haga clic en la pestaña Preferencias.
3. En Vista predeterminada de la cuenta, seleccione una vista.

   Nota: También puede seleccionar Vista jerárquica (HV) como vista predeterminada. Solo aparecerán en la lista desplegable los HV a los que el usuario tenga acceso, y solo se podrá establecer como predeterminado el nodo de nivel más alto.

   Nota: Cloudability recuerda la última vista a la que accediste y la guarda en la caché de tu navegador. La próxima vez que inicie sesión, se restaurará esa misma vista en lugar de la vista predeterminada. Si borras la caché de tu navegador y vuelves a iniciar sesión, Cloudability cargará tu vista predeterminada.

   ![establecer vistas por defecto captura de pantalla](../../../../03-media/cloudability-premium/images/manage-view.jpg)
4. Haga clic en Guardar configuración.

## Seleccione una vista

La selección de una vista reduce el alcance de los datos que se ven a través de Cloudability según las condiciones de filtrado de la vista. Para seleccionar una vista existente:

1. Haga clic en el menú desplegable Vista actual de la barra de navegación superior.
2. Elige una vista de la lista.

Cloudability Ahora se mostrarán los datos según los filtros configurados en la vista seleccionada.

![Lista desplegable que muestra las dimensiones especificadas en la vista](../../../../03-media/cloudability-premium/images/specified-dimensions.png)

Nota:

La opción **«Mostrar todos los datos»** solo está disponible para los usuarios con el rol **de administrador**. Los usuarios que no sean administradores solo pueden acceder a las vistas que se les hayan asignado.

## Preguntas más frecuentes

**Q1: ¿Por qué los nuevos usuarios ven varias Vistas aunque no se les haya concedido un acceso específico?**

Si un administrador de vistas ha compartido vistas con el permiso "Toda la organización", todos los usuarios podrán acceder a esas vistas de forma predeterminada, incluidos los usuarios recién añadidos.

**Q2: ¿Cómo funciona la edición masiva (Editar múltiples) para Vistas? (con ejemplos)**

Puede seleccionar varias Vistas y utilizar Editar varias para actualizar sus permisos en bloque. Los filtros no pueden editarse en bloque porque cada vista tiene sus propios filtros. Cuando se realiza una edición masiva, se muestran los permisos combinados de todas las Vistas seleccionadas.

Ejemplos:

- *Ejemplo 1:* Si la Vista A es Privada y la Vista B está compartida con Toda la Organización, la pantalla de edición masiva mostrará Toda la Organización como seleccionada. Los cambios que realice se aplicarán a ambas vistas.
- *Ejemplo 2:* Si la Vista A se comparte con los usuarios *u1, u2* y el grupo *g1*, y la Vista B con *u2, u3*, la pantalla de edición masiva mostrará *u1, u2, u3* y *g1* seleccionados. Al guardar se aplicarán estos permisos combinados a ambas Vistas.

Importante: Si sólo desea añadir un nuevo usuario a varias Vistas, la edición masiva puede no ser lo ideal. Por ejemplo, agregar *u4* a ambas Vistas usando la edición masiva también fusionará todos los permisos existentes, lo que dará como resultado que ambas Vistas tengan *u1, u2, u3, u4* y *g1*.

**Consejo de buenas prácticas: Cuándo utilizar la edición masiva frente a las ediciones individuales**

Utilice **Editar Múltiple** sólo cuando desee estandarizar los permisos en varias Vistas. Si su objetivo es realizar cambios pequeños y específicos (como añadir un único usuario), edite cada Vista individualmente para evitar fusionar permisos involuntariamente.

**Q3: ¿Por qué no veo la opción de vista duplicada para las vistas jerárquicas?**

La función de duplicar o cerrar no está disponible para las vistas jerárquicas. Esto se debe a que cada Vista Jerárquica Una Vista Jerárquica se construye a partir de un Mapeo Jerárquico de Negocio. Para crear un nuevo grupo de Vistas Jerárquicas, es necesario añadir primero una nueva Asignación Jerárquica de Negocio. Esto nos impide duplicar la vista jerárquica.

**Q4: ¿Por qué no aparece seleccionada mi vista predeterminada cuando inicio sesión en Cloudability?**

Cloudability Recuerda la última vista a la que accediste y la guarda en la caché de tu navegador. La próxima vez que inicie sesión, se restaurará esa misma vista en lugar de la vista predeterminada. Si borras la caché de tu navegador y vuelves a iniciar sesión, Cloudability cargará tu vista predeterminada.

**Q5: ¿Qué ocurre cuando el administrador elimina una vista o retira un permiso de visualización a un usuario?**

El usuario puede esperar el siguiente comportamiento cuando el administrador elimina una vista o quita los permisos de una vista a un usuario:

1. La configuración predeterminada del usuario volverá automáticamente a la vista predeterminada a nivel de la organización.
2. Si no existe un valor predeterminado a nivel de organización, la vista predeterminada se establecerá en blanco.
3. Los usuarios pueden actualizar su vista predeterminada en cualquier momento a través de: Administrar perfil → Preferencias.

## Resolución de problemas

- ¿No puede ver ningún dato bajo una Vista? Asegúrese de contar con el permiso de ViewsFeatureFullAccess.

## Mejores prácticas

- Utilice convenciones de nomenclatura coherentes para las vistas (por ejemplo, BU\_Prod\_Cost) para facilitar su identificación.
- Proporcione una descripción clara de cada Vista para explicar su finalidad y uso previsto.
- Limitar el uso compartido de "Toda la organización" sólo a las vistas esenciales. El uso excesivo de esta opción puede reducir la eficacia de las Vistas al hacer que demasiadas sean accesibles a todo el mundo.
- Revisar y limpiar periódicamente las Vistas no utilizadas para mantener un entorno organizado y eficiente.

- **[Organizar vistas mediante vistas jerárquicas](../admin/hierarchical-views.html)**
- **[Compatibilidad de la función «Vistas»](../admin/views-feature-compatibility.html)**
