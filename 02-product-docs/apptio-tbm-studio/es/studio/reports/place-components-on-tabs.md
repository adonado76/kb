---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Colocar los componentes en las pestañas"
breadcrumb: []
source_path: "studio/reports/place-components-on-tabs.html"
images:
  - "resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png"
  - "resources/images/studio_images/studioimages/studio/aug151.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Colocar los componentes en las pestañas

**Se aplica a** : TBM Studio 12.0 y posteriores

Si tiene una serie de componentes relacionados que desea incluir en un informe, pero no quiere distribuirlos en una gran área del informe, puede colocar los componentes en un grupo con pestañas. A continuación, el usuario puede seleccionar una pestaña para visualizar uno o varios componentes específicos. Todos los componentes, excepto los cuadros de agrupación, pueden colocarse en una pestaña. En la siguiente imagen se muestra un ejemplo de grupo de pestañas:

![componentes en fichas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug151.png)

## Añadir un grupo de pestañas

En la pestaña **Informe**, haga clic en el icono **Pestañas**.

## Realizar acciones en grupos con pestañas

A continuación se describen las acciones que puede realizar en un grupo de fichas:

| A: | Haz esto: |
| --- | --- |
| Añadir una ficha al grupo | Haga clic en la pestaña con el signo + e introduzca un nombre para la pestaña en el campo **Editar pestaña**. Para guardar la pestaña, pulse Intro. |
| Añadir un componente a una ficha | Cree el componente en la superficie de creación de informes y arrástrelo al grupo de fichas. Puede añadir más de un componente a una ficha. |
| Eliminar un componente de una ficha | Arrastre el componente fuera del grupo de fichas o haga clic en el icono de eliminación situado en la esquina superior derecha del componente. |
| Cambiar el orden de las pestañas | Seleccione una pestaña y haga clic en los iconos de doble flecha izquierda/derecha (<<) (>>) situados debajo del cuadro de grupo de pestañas. |
| Borrar una pestaña | Seleccione la pestaña y haga clic en el icono **Eliminar** situado debajo del cuadro de grupo de pestañas. |
| Cambiar el tamaño del cuadro de grupo | Haz clic y arrastra los bordes. |
| Añadir color de fondo a una pestaña | Haga clic con el botón derecho del ratón en la pestaña y seleccione **Propiedades** en el menú emergente. En la pestaña **General** del cuadro de diálogo **Propiedades**, seleccione un color en el campo **Color de fondo de la pestaña**. Puede seleccionar un color diferente para cada pestaña. |

## Establecer las propiedades

Para establecer las propiedades del grupo de pestañas, muestre el cuadro de diálogo **Propiedades** realizando una de las siguientes acciones:

- En la esquina superior izquierda del grupo de pestañas, haga clic en el pequeño triángulo ![triángulo pequeño](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png) situado junto al nombre del componente para mostrar el menú **Acciones**. En el menú **Acciones**, haga clic en **Propiedades**.
- Haga clic con el botón derecho del ratón en cualquier lugar dentro de los bordes del componente y haga clic en **Propiedades** en el menú emergente.

## Propiedades generales

- **Nombre** - Introduzca un nombre que se mostrará en la cabecera del componente, encima del componente, cuando se seleccione **Mostrar cabecera**.
- **Leyenda** - Introduzca información adicional sobre el componente. La información se muestra en función de la configuración del campo **Posición del título**.
- **Posición del** pie de ilustración - En la lista, seleccione una posición del pie de ilustración relativa al botón: **Arriba**, **Abajo**, **Izquierda** o **Derecha**, o seleccione **Ocultar** para no mostrar el pie de foto.
- **Mostrar cabecera** - La cabecera del componente muestra el contenido del campo **Nombre**. Seleccione esta opción para hacer visible la cabecera del componente (por defecto). Cuando la cabecera está oculta, puede detener el puntero del ratón sobre el componente para mostrarlo cuando esté en modo Edición.
- **Mostrar** borde - Seleccione esta opción para mostrar un borde alrededor de la tabla. Cuando el borde está oculto, puede detener el puntero del ratón sobre el componente para mostrarlo cuando esté en modo Edición.
- **Ajustar título** - Ajusta el texto introducido en el campo **Nombre** a la anchura del componente.
- **Color de fondo de** las pestañas - Seleccione un color para el fondo de las pestañas. Esta configuración se aplica a todas las pestañas del grupo.

## Propiedades avanzadas

**Actualizar automáticamente al finalizar los cálculos** - Cuando la aplicación muestra un componente de pestaña, lo muestra con los datos calculados disponibles en ese momento. En muchos casos, la aplicación puede estar calculando nuevos valores en segundo plano. Si desea que se muestren los resultados una vez finalizados los cálculos, marque esta opción.

## Colocar componentes en un grupo con fichas

Lo ideal es que los componentes de un grupo con pestañas se muevan con el grupo si lo reposiciona. Para que los componentes se muevan con el grupo, deben situarse bien dentro de los límites del grupo. Para garantizar su correcta colocación:

- Haga clic con el botón derecho del ratón en el encabezamiento del objeto y pulse **Posición y tamaño** en el menú emergente.
- En el cuadro de diálogo **Establecer posición y tamaño**, ponga a cero las coordenadas X e Y.

Utilice los márgenes resultantes como puntos de partida para posicionar el objeto. Puedes aumentar los márgenes y el objeto se moverá con el grupo. Si reduce los márgenes, el objeto se desacoplará del grupo.

## Controlar la visualización de las pestañas

Cuando se añade un grupo de pestañas a un informe, se puede utilizar texto dinámico para controlar qué pestañas se muestran. El texto dinámico puede hacer referencia a un conjunto de datos, o puede utilizar una sentencia If con filtros.

Las opciones para controlar las pestañas son:

- **activado** : la pestaña es visible y seleccionable
- **hidden** : la pestaña no es visible
- **desactivado** : la pestaña está visible pero no se puede seleccionar

Las opciones pueden aplicarse a todas las pestañas de un grupo excepto a la primera. La primera pestaña siempre será visible y seleccionable.

El siguiente ejemplo utiliza el valor "hidden" de un conjunto de datos denominado TabStatus:

> `<%=TabStatus:Hidden%>`

El siguiente ejemplo muestra una opción sencilla para ocultar la pestaña:
> <%="oculto"%>

El conjunto de datos podría tener el siguiente aspecto, con una fila de encabezamiento y una fila de valores:

| Habilitada | Oculto | Inhabilitado |
| --- | --- | --- |
| habilitado | oculto | inhabilitado |

A continuación se muestra un ejemplo de sentencia If:

> `<%=If(GetLastFilterValue()="Sales","hidden","enabled")%>`

El ejemplo anterior sólo funcionará en un informe filtrado.

Para que las pestañas se activen u oculten condicionalmente en función del rol del usuario, utilice la siguiente sentencia IF:

> ```
> <%=IF(eval("{$CurrentUser}:{Users.Role}")
>       ="Admin","enabled","hidden")%>
> ```

Para especificar la configuración de las pestañas:

1. Seleccione el grupo de pestañas.
2. En la pestaña **Pestañas**, haga clic en **Visibilidad**.
3. Introduzca una referencia a un conjunto de datos o una sentencia If para cada pestaña (excepto la pestaña 1, que siempre está visible).
4. Pulse **Guardar**.
