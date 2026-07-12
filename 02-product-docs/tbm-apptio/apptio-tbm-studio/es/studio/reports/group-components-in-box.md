---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Agrupar componentes en una caja"
breadcrumb: []
source_path: "studio/reports/group-components-in-box.html"
images:
  - "resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png"
  - "resources/images/studio_images/studioimages/reports/rep144.png"
  - "resources/images/studio_images/studioimages/reports/rep145.png"
  - "resources/images/studio_images/studioimages/studio/aug159.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Agrupar componentes en una caja

**Se aplica a** : TBM Studio 12.0 y posteriores

Si está creando un informe con muchos componentes, puede resultarle útil agrupar visualmente los componentes añadiendo un borde alrededor de los mismos. Por ejemplo, la siguiente imagen muestra dos conjuntos de componentes sin bordes. Un conjunto de componentes muestra los costes de las unidades de negocio, el otro conjunto muestra los costes de los centros de datos:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep144.png)

La adición de bordes, como se muestra en la imagen siguiente, aclara la relación entre el gráfico y la tabla de cada conjunto. Al colocar los componentes del informe dentro de un cuadro de grupo, se agrupan físicamente para que puedan moverse como un grupo.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep145.png)

## Añadir un cuadro de grupo

1. En la pestaña **Informe**, haga clic en el icono **Grupo**. La aplicación añade el cuadro de grupo al informe.
2. Mueva y cambie el tamaño de la caja según sea necesario.
3. Para mover la caja, haga clic en la cabecera y arrástrela a la nueva ubicación.
4. Para cambiar el tamaño de la caja, arrastre los bordes.

## Añadir componentes a un cuadro de grupo

Para añadir componentes a un cuadro de grupo, selecciónelos y arrástrelos al cuadro. Cambie el tamaño del cuadro de grupo para acomodar los objetos. Cuando arrastre el cuadro de grupo, los objetos del cuadro también se moverán, conservando sus posiciones relativas en el cuadro.

## Organizar componentes en un cuadro de grupo

Si coloca varios objetos en un cuadro de grupo, puede organizar los componentes manualmente o mediante las herramientas de **disposición de grupos** de la pestaña **Grupo**. La ventaja de las opciones de disposición **Vertical** y **Horizontal** es que si un componente colocado en el grupo está oculto para un conjunto de usuarios, los componentes restantes se dispondrán para rellenar el espacio ocupado por el componente que falta.

A continuación se describen las opciones de disposición de los grupos:

- **Manual** - Puede colocar los componentes en cualquier lugar del grupo y permanecerán donde los coloque.
- **Vertical** - Alinea automáticamente los componentes verticalmente utilizando los ajustes de la opción **Espaciado**.
- **Horizontal** - Alinea automáticamente los componentes horizontalmente utilizando los ajustes de la opción **Espaciado**.
- **Espaciado** - Muestra un cuadro de diálogo en el que puede establecer el espaciado vertical y horizontal entre los componentes.

## Tamaño automático

El cuadro de grupo puede tener un tamaño fijo o cambiar de tamaño dinámicamente. Si la caja tiene un tamaño fijo, no cambia de tamaño en función del número de componentes visualizados. Si el número de componentes de un cuadro de grupo hace que éste muestre barras de desplazamiento, éstas aparecerán aunque sólo se visualice un componente en el cuadro.

Si el tamaño de la caja se establece de forma dinámica, se ajustará para adaptarse al tamaño de los componentes incluidos en la caja. Utilice las opciones de **Tamaño automático** de la pestaña **Grupo** para controlar cómo se ajusta el cuadro de grupo a los componentes.

## Cambiar el icono de un cuadro de grupo

Puede cambiar el icono por defecto de un cuadro de grupo. Los archivos gráficos de iconos se almacenan en un servidor central en una colección Icon Experience. Para cambiar el icono de un cuadro de grupo en un informe, cambie la ruta del icono en el HTML del cuadro de grupo.

Para cambiar el icono de un cuadro de grupo:

1. En otra ventana del navegador, vaya a este enlace: http://<yourapptiodomain>.apptio.com/graphics/IconExperience/search.html
2. Busca el icono que quieras utilizar.
3. Cuando haya localizado el icono, selecciónelo en las listas de la izquierda.
4. A la derecha, localice el icono del tamaño que desea utilizar.
5. Haga clic con el botón derecho en el icono y seleccione Copiar ubicación de imagen.
6. Pégalo en el Bloc de notas y copia el URL para el icono que empieza por la palabra "graphics" Ejemplo: graphics/IconExperience/v\_collections\_png/computer\_network\_security/24x24/plain/server\_lock.png.
7. Abra el menú **Acción** del cuadro de grupo y seleccione **Propiedades**.
8. En la pestaña **General**, pegue el nuevo URL en el campo **Agrupación de imágenes URL**.

## Añadir un título al borde

Un elemento tradicional de muchas aplicaciones es un título incrustado en el borde de los cuadros de grupo. Puede añadir fácilmente títulos incrustados a los cuadros de grupo de los informes, como se muestra en la siguiente imagen. En este ejemplo, se ha añadido el título Costes de aplicación al cuadro de grupo:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug159.png)

Para añadir un título al borde de un cuadro de grupo:

1. Haga clic con el botón derecho del ratón dentro del cuadro de grupo y seleccione **Propiedades** en el menú emergente.
2. En la pestaña **General** del cuadro de diálogo **Propiedades**, introduzca el texto del título en el campo **Título del borde de agrupación**.

## Añadir un fondo de color

Para añadir un fondo de color a un cuadro de grupo:

1. Haga clic con el botón derecho del ratón dentro del cuadro de grupo y seleccione **Propiedades** en el menú emergente.
2. En la pestaña **General** del cuadro de diálogo **Propiedades**, abra la lista desplegable del campo **Estilo de agrupación** y seleccione un color.
3. Para ver el nuevo color, pulse el botón **Aplicar**.

## Bordes de cuadro de grupo

Existen varias opciones para controlar el aspecto de los bordes de un cuadro de grupo. Los elementos de las fronteras se identifican en la siguiente imagen. Todas las opciones menos una se encuentran en la pestaña **General** del cuadro de diálogo **Propiedades** del cuadro de grupo:

![imagen](../../resources/images/studio_images/studioimages/visio%20diagrams/group-box-borders.png)

A continuación se describe cómo controlar cada uno de los elementos:

- El nombre del cuadro de grupo procede del campo **Nombre**.
- Para mostrar el nombre del cuadro de grupo, seleccione la opción **Mostrar encabezado**.
- El borde exterior se controla mediante el campo **Mostrar borde**. Cuando la opción está marcada, se muestra el borde exterior.
- El icono y el título del borde interior se muestran cuando la opción **Mostrar borde interior** está marcada.
- El texto del borde interior procede del campo **Título del borde de agrupación** de la pestaña **General**.
- El formato del texto del título del borde interior se controla mediante el campo **Título del borde de agrupación** de la pestaña **Estilos** del cuadro de diálogo **Propiedades del** cuadro de grupo. El estilo se controla introduciendo un estilo CSS en Apptio. Se trata de una función avanzada utilizada por los consultores de Customer Success de Apptio.

## Cuadros de grupo de tamaño automático

Si ha colocado varias tablas en un cuadro de grupo, y una o más de esas tablas están configuradas para autodimensionarse en función de su contenido, puede configurar el cuadro de grupo para que también se redimensione. Así se garantiza que el tamaño de la caja de grupo coincida con el de las mesas. Puede establecer la anchura, la altura o ambas para cambiar el tamaño. El cambio de tamaño sólo funciona en el modo Vista. Cuando esté editando un informe, el cuadro de grupo no cambiará de tamaño.

Para configurar las opciones de redimensionamiento:

1. Seleccione el cuadro de grupo.
2. En la pestaña Grupo, seleccione una de las opciones de redimensionamiento.

## Establecer las propiedades

Para editar las propiedades de un cuadro de grupo, muestre el cuadro de diálogo **Propiedades** realizando una de las siguientes acciones:

- En la esquina superior izquierda del icono, haga clic en el pequeño triángulo ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png) situado junto al nombre del componente para mostrar el menú **Acciones**. En el menú **Acciones**, haga clic en **Propiedades**.
- Haga clic con el botón derecho del ratón en cualquier lugar dentro de los bordes del componente y seleccione **Propiedades** en el menú emergente.

Las propiedades **generales** no descritas en las secciones anteriores se describen a continuación:

- **Nombre** - Introduzca un nombre que se mostrará en la cabecera del componente, encima del componente, cuando se seleccione **Mostrar cabecera**.
- **Leyenda** - Introduzca información adicional sobre el componente. La información se muestra en función de la configuración del campo **Posición del título**.
- **Posición del** pie de ilustración - En la lista, seleccione una posición del pie de ilustración relativa al botón: **Arriba**, **Abajo**, **Izquierda** o **Derecha**, o seleccione **Ocultar** para ocultar el pie de foto.
- **Mostrar cabecera** - La cabecera del componente muestra el contenido del campo **Nombre**. Seleccione esta opción para hacer visible la cabecera del componente (por defecto). Cuando la cabecera está oculta, puede mostrarla deteniendo el puntero del ratón sobre el componente.
- **Mostrar borde** - Seleccione esta opción para mostrar un borde alrededor del cuadro de grupo. Cuando el borde está oculto, puede mostrarlo deteniendo el puntero del ratón sobre el componente.
- **Ajustar título** - Ajusta el texto introducido en el campo **Nombre** a la anchura del componente.
- **Mostrar borde interior** - Seleccione esta opción para mostrar un título en el borde interior. El texto del título se toma del campo Título del borde de agrupación.
- **Imagen de agrupación URL** - Para cambiar el icono que aparece en el borde interior, introduzca la dirección URL al archivo de imagen del icono. A continuación se muestra URL para el icono por defecto:`/graphics/IconExperience/v_collections_png/computer_network_security/48x48/shadow/envelope_cushioned.png`
- **Título del borde de agrupación** : el texto ingresado en este campo se muestra como título en el borde interior.
- **Color de** fondo - Controla el color de fondo del área dentro del borde interior.

La propiedad Styles incluye:

- **Título del borde de agrupación** - Da forma al texto que aparece en el borde interior del cuadro de grupo. Introduzca un estilo CSS (Cascading Style Sheet) en Apptio para aplicar un formato. Se trata de una función avanzada utilizada por los consultores de éxito de clientes de Apptio.

La propiedad **avanzada** incluye:

- **Actualizar automáticamente al finalizar los cálculos** - Cuando la aplicación muestra un componente Cuadro de grupo, lo muestra con los datos calculados disponibles en ese momento. En muchos casos, la aplicación puede estar calculando nuevos valores en segundo plano. Si desea que se muestren los resultados una vez finalizados los cálculos, marque esta opción.
