---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Componente de botón"
breadcrumb: []
source_path: "studio/reports/button.html"
images:
  - "resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png"
  - "resources/images/studio_images/studioimages/icons/edit_21x21_icon.png"
  - "resources/images/studio_images/studioimages/reports/rep147.png"
  - "resources/images/studio_images/studioimages/reports/rep148.png"
  - "resources/images/studio_images/studioimages/studio/aug114.png"
  - "resources/images/studio_images/studioimages/studio/stu629.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Componente de botón

**Se aplica a** : TBM Studio R.12.0 y posteriores.

Utilice el componente **Botón** en los informes para proporcionar enlaces a cualquier informe de un proyecto. Además, utilice los botones para cambiar el período de tiempo que se muestra actualmente en un informe y para añadir y eliminar filas en una tabla. Por ejemplo, consulte el botón Presupuesto de la aplicación que aparece a continuación:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu629.png)

Al añadir un botón a un informe, puede cambiar su aspecto, añadir gráficos y definir acciones para el botón.

Nota: Tenga cuidado cuando cree un botón que navegue a un informe. Si muestra un informe que requiere un cálculo significativo, esto puede afectar al rendimiento del sistema.

## Añadir un botón

En la pestaña **Informe**, haga clic en el icono **Botón**. La aplicación añade el objeto botón al informe como se muestra en la siguiente imagen. El botón se encuentra dentro de un panel de componentes de informe estándar.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug114.png)

## Cambiar el aspecto de un botón

Después de añadir un botón a un informe, puede cambiar su aspecto. Además, puede sustituir o complementar el texto del botón con una imagen personalizada.

Para cambiar la apariencia del botón:

1. En la esquina superior izquierda del componente botón, haga clic en el pequeño triángulo ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png) para abrir el menú **Acciones** y, a continuación, haga clic en **Propiedades**. Aparece el cuadro de diálogo **Propiedades** :![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep147.png)
2. Utilice los campos de la pestaña **Botón** para cambiar el aspecto del botón. Los campos se describen a continuación.
   - **Texto del** botón - El texto introducido en este campo se muestra en el botón. Normalmente, será una etiqueta estática. Sin embargo, puede utilizar texto dinámico en este campo. Para obtener información sobre el texto dinámico, consulte [Cuadro de texto HTML](html.html "Se aplica a: TBM Studio 12.0 y posteriores").También puede sustituir o complementar el texto de un botón con una imagen de la biblioteca de imágenes Apptio insertando código HTML que haga referencia a la imagen.
   - **Información sobre el botón** - El texto introducido en este campo se mostrará como información sobre el botón cuando el usuario pase el puntero del ratón por encima del botón.
   - **Activado** - Determina si el botón está activo, desactivado u oculto.
     - Para ocultar el botón, introduzca la palabra "oculto" en el campo.
     - Para desactivar el botón, introduzca la palabra "desactivado" en el campo. El botón aparecerá en gris y no se podrá seleccionar.
     - Puede introducir una función que se evaluará para determinar el estado del botón. Por ejemplo, para activar un botón si el coste es superior a 5.000 dólares, debe introducir `<%=IF(Cost>5000,"enabled","disabled")%>`. Para obtener más información sobre las funciones, consulte "Introducción a las fórmulas y funciones" en la *Guía de Studio*.
   - **Color del** botón - Establece el color de fondo del botón.
   - **Color del texto del botón** - Establece el color del texto.
   - **Tamaño del texto** - Establece el tamaño del botón y el texto que se muestra en el botón. También puede cambiar el tamaño de un botón arrastrando el borde del panel que lo rodea. El tamaño mínimo del botón está restringido por la cantidad de texto mostrado.
   - **Botón Crecimiento**
     - **Auto** : Ajusta el botón al tamaño por defecto.
     - **Horizontal** : Alarga el botón para que se ajuste al panel circundante.
   - **Color de fondo del panel** - Establece el color del panel que rodea al botón.
3. Para previsualizar los cambios, haga clic en **Aplicar**. Para guardar los cambios, haga clic en **Aceptar**.

## Definir las acciones de un botón

Cuando un usuario hace clic en un botón, puede realizar una acción programada, cambiar la fecha y/o navegar a un informe.

Para establecer las acciones de un informe:

1. En el cuadro de diálogo **Propiedades**, seleccione la pestaña **Acciones** de la cabecera. La aplicación muestra los siguientes campos:![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep148.png)
2. Rellene los campos.
   - **Acción del servidor** - En este campo se puede introducir un script de servidor utilizando el lenguaje de scripting Apptio. El script se ejecuta primero antes de que se ejecuten las entradas de los campos **Cambiar fecha** y **Navegar**. Se trata de una función avanzada utilizada por los consultores de Customer Success de Apptio.
   - **Cambiar fecha** : seleccione una opción de la lista desplegable o introduzca una fecha en el campo **Fecha de** la parte inferior de la lista. El formato de fecha es periodo:año. Ejemplos: January:FY2012, P3:FY2012.
     - Para aceptar una entrada en el campo **Fecha**, haga clic en el signo más situado a la derecha del campo.
     - Para borrar el ajuste **Cambiar fecha**, seleccione **Borrar fecha seleccionada** en la lista desplegable.
   - **Navegar** - Introduzca un enlace a un documento utilizando la sintaxis de estilo Wiki. Para más detalles y ejemplos, véase [Codificación de enlaces a otros informes](coding-links-to-other-reports.html "Se aplica a: TBM Studio 12.0 y posteriores").
   - **Botón Atrás** - Cuando se selecciona esta opción, al hacer clic en el botón el usuario volverá al último informe en el que se encontraba. Esto proporciona al usuario una alternativa a las migas de pan del informe. Esta opción anula cualquier entrada realizada en los campos Acción del servidor, Cambiar fecha y Navegar.
   - **Enviar formulario** - Si el botón se coloca en un formulario, enviará el formulario cuando se haga clic en él.
3. Para previsualizar los cambios, haga clic en **Aplicar**. Para guardar los cambios, haga clic en **Aceptar**.

## Establecer las propiedades generales

A continuación se describen las propiedades generales.

- **Nombre** - Introduzca un nombre para que aparezca en la cabecera del botón encima del componente. El nombre aparece cuando se selecciona la opción **Mostrar encabezado**.
- **Leyenda** - Introduzca información adicional sobre el componente. La información se muestra en función de la configuración del campo **Posición del título**.
- **Posición del** pie de ilustración - En la lista, seleccione una posición del pie de ilustración relativa al botón: **Arriba**, **Abajo**, **Izquierda** o **Derecha**, o seleccione **Ocultar** para no mostrar el pie de foto.
- **Mostrar cabecera** - La cabecera del componente muestra el contenido del campo **Nombre**. Seleccione esta opción para hacer visible la cabecera del componente. Cuando la cabecera está oculta, puede detener el puntero del ratón sobre el componente para mostrar la cabecera.
- **Mostrar** borde - Seleccione esta opción para mostrar un borde alrededor de la tabla. Cuando el borde está oculto, puede detener el puntero del ratón sobre el componente para mostrar el borde.
- **Ajustar título** - Ajusta el texto introducido en el campo **Nombre** a la anchura del componente.

## Establecer propiedades avanzadas

Las propiedades **avanzadas** incluyen:

- **Actualizar automáticamente al finalizar los cálculos** - Cuando la aplicación muestra un botón, lo muestra con los datos calculados disponibles en ese momento. En muchos casos, la aplicación puede estar calculando nuevos valores en segundo plano. Si desea que se muestren los resultados una vez finalizados los cálculos, seleccione esta opción. Esta opción sólo se aplica a la tabla seleccionada en ese momento. Esta opción sólo está disponible cuando la **Política de cálculo** (en el cuadro de diálogo **Cálculo del proyecto** ) de un proyecto está establecida en **Publicación dinámica**.
- **Activar pestañas de aplicación en el proyecto** - Esta opción ya no está activa en la versión 12.0 del producto. Se trata de una función heredada de las versiones v.11.x del producto.
- **Datos URL** - Muestra la ruta a la tabla que suministra los datos para el informe. Puede introducir una función de tabla en este campo haciendo clic en el icono **Editar ruta de datos** ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/edit_21x21_icon.png) situado a la derecha del campo. La aplicación muestra el cuadro de diálogo **Editar ruta**.
- **Crear nuevo proyecto** - Si selecciona un valor para este campo, la aplicación creará un nuevo proyecto cuando un usuario haga clic en el botón. Tiene dos opciones:
  - **Derivado** - La aplicación crea un proyecto independiente basado en un proyecto existente. Utilícelo cuando desee conservar el proyecto antiguo como referencia. La eliminación del proyecto original no elimina el proyecto derivado.
  - **Instantánea del proyecto actual** - La aplicación marca un punto en el tiempo en el registro del proyecto existente y crea un nuevo proyecto. El nuevo proyecto se vincula al antiguo. Si borras el proyecto antiguo, se borrará el nuevo.

  Nota: Si está creando un nuevo proyecto, debe completar los campos **Derivar proyecto generado desde** y **Fecha de inicio del proyecto**.
- **Derivar proyecto generado de** - Utilícelo cuando cree un nuevo proyecto derivado. Introduzca el nombre del proyecto que se utilizará como base para el proyecto derivado. El nombre debe incluir el ejemplo domain.For :

  ```
  abc_company.com:Project
                123
  ```
- **Fecha de inicio del proyecto** - Se utiliza al crear un nuevo proyecto derivado. Introduzca la fecha de inicio que se asignará al proyecto derivado. Puede utilizar cualquiera de los formatos de fecha admitidos. Un formato típico es MMM-FYyyyy.For ejemplo: ENE FY2012.
- **Crear proyecto personal** - Crea un proyecto al que sólo puede acceder la persona que lo crea. Añade el ID de usuario de la persona que pulsa el botón al nombre del proyecto. Por ejemplo, si psmith@abc \_company.com hace clic en el botón e introduce un nombre de proyecto "nuevo-proyecto", el nombre completo del proyecto será "\_psmith@abc \_company.com\_new-project. "Observe el guión bajo delante del nombre del proyecto.
