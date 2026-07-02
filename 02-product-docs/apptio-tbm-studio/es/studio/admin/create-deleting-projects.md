---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear, gestionar y eliminar proyectos"
breadcrumb: []
source_path: "studio/admin/create-deleting-projects.html"
images:
  - "resources/images/icons/icon-settings.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear, gestionar y eliminar proyectos

**Se aplica a** : TBM Studio 12.0 y posteriores

Al crear un nuevo proyecto, tiene dos opciones:

- **Cree un proyecto de aplicación.** Los proyectos de aplicación sirven como plantillas para nuevos proyectos. Cuando se crea un proyecto de aplicación, la aplicación crea automáticamente conjuntos de datos, métricas, modelos e informes basados en la plantilla de la aplicación. Las plantillas de solicitud incluyen: Costing Standard.
- **Crear un proyecto personalizado.** Un proyecto en blanco no tiene conjuntos de datos, modelos, métricas ni informes. Cree un nuevo proyecto personalizado si no desea basarse en trabajos anteriores.

En las siguientes secciones, hablaremos sobre la creación de nuevos proyectos personalizados. Para más información, consulte las distintas guías de aplicación:

- [Crear un proyecto personalizado](#Createmanageanddeleteprojects__Createacustomproject)
- [Hacer un proyecto visible para los usuarios](#Createmanageanddeleteprojects__Makeaprojectvisibletousers)
- [Editar la información global del proyecto](#Createmanageanddeleteprojects__Editglobalprojectinformation)
- [Navegar entre proyectos](#Createmanageanddeleteprojects__Navigatebetweenprojects)
- [Eliminar un proyecto](#Createmanageanddeleteprojects__Deleteaproject)
- [Renombrar un proyecto](#Createmanageanddeleteprojects__Renameaproject)

## Crear un proyecto personalizado

Cuando se crea uno de los tipos de proyectos anteriores, excepto un proyecto personalizado, la aplicación crea conjuntos de datos, modelos e informes específicos para el tipo de proyecto seleccionado. Si crea un proyecto personalizado, no habrá contenido. No habrá conjuntos de datos, métricas, modelos, objetos ni informes. Tendrás que crearlas tú. Hay muchas razones para crear un nuevo proyecto:

- Hay varios usuarios diferentes de la aplicación y cada uno de ellos pertenece a un departamento distinto. Quieres la libertad de trabajar en tu proyecto sin preocuparte de que otro usuario cambie tus conjuntos de datos, modelo, métricas e informes.
- Hay que tener en cuenta tanto los costes reales como las previsiones de costes futuros. La mejor práctica sería crear un proyecto real y un proyecto de previsión.
- Está analizando diferentes productos de software empresarial, como un sistema ERP o CRM, y desea realizar comparaciones de costes.

Su licencia Apptio le permite crear un número ilimitado de proyectos. Para crear un proyecto personalizado:

1. Abra el menú Configuración ![](../../../../../03-media/apptio-tbm-studio/resources/images/icons/icon-settings.png) en la esquina superior derecha de la pantalla y haga clic en **Nuevo proyecto**.
2. En el cuadro de diálogo Nuevo proyecto, introduzca la información del nuevo proyecto.
3. Para crear el proyecto y cerrar el cuadro de diálogo, haga clic en **Aceptar**.
4. Compruebe en el project.When que comprueba en el proyecto, se hace una entrada en la consola Access Administration como se muestra a continuación. Inicialmente, el proyecto no será visible para los usuarios (el proyecto no aparecerá en el menú Aplicaciones). Esto es útil si desea configurar completamente el proyecto antes de hacerlo visible a los usuarios.

   ![](../../resources/images/studio_images/studioimages/studio_access%20admin_applications_sui.png)

## Hacer un proyecto visible para los usuarios

Cuando esté listo para hacer que un proyecto sea visible para los usuarios, siga los pasos que se indican a continuación:

1. Abra la consola Access Administration haciendo clic en el menú **Configuración** ![](../../../../../03-media/apptio-tbm-studio/resources/images/icons/icon-settings.png) situado en la esquina superior derecha de la pantalla y, a continuación, haga clic en **Access Administration**.
2. En la pestaña **Aplicaciones**, localice su proyecto y haga clic en **Editar visibilidad**.
3. Haga clic en las funciones a las que desea dar acceso al proyecto.
4. Pulse **Guardar**.
5. Haz clic en **Mostrar**.

## Editar la información global del proyecto

Después de crear un proyecto, puede editar su información.

1. Echa un vistazo al proyecto.
2. En la pestaña **Proyecto**, en el grupo **Configuración del proyecto**, haga clic en **Configuración del proyecto**. Aparecerá el cuadro de diálogo Editar configuración del proyecto.

   ![](../../resources/images/studio_images/studioimages/studio_project%20setup_project%20settings_sui.png)
3. Realice los cambios y pulse **OK**.

## Navegar entre proyectos

En la aplicación, sólo puedes tener abierto un proyecto a la vez. Los proyectos se abren desde el menú Proyectos.

![](../../resources/images/studio_images/studioimages/studio_bank%20demo%20menu_bankdemo_sui.png)

En TBM Studio v12.3.1 y posteriores, puedes hacerlo:

- Especifique qué versión utilizar para las actualizaciones de componentes ( [specify-version-component.html](specify-version-component.html "(se abre en una pestaña o una ventana nueva)") )
- Especifique el proyecto por defecto de su dominio ( [change\_default\_project.htm](change_default_project.htm "(se abre en una pestaña o una ventana nueva)") )

## Eliminar un proyecto

Sólo los administradores del sistema Apptio pueden eliminar proyectos. Si desea eliminar un proyecto, consulte a su administrador.

## Renombrar un proyecto

No es posible renombrar un proyecto desde el producto. Si desea cambiar el nombre de un proyecto, póngase en contacto con el administrador del sistema Apptio y solicite el cambio de nombre.
