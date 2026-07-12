---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Establecer las propiedades del gráfico"
breadcrumb: []
source_path: "studio/reports/set-chart-properties.html"
images:
  - "resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png"
  - "resources/images/studio_images/studioimages/icons/hydration_warning.png"
  - "resources/images/studio_images/studioimages/icons/properties_icon_21x21.png"
  - "resources/images/studio_images/studioimages/reports/rep061.png"
  - "resources/images/studio_images/studioimages/reports/rep173.png"
  - "resources/images/studio_images/studioimages/reports/rep175.png"
  - "resources/images/studio_images/studioimages/reports/rep176.png"
  - "resources/images/studio_images/studioimages/reports/rep177.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Establecer las propiedades del gráfico

**Se aplica a** : TBM Studio 12.0 y posteriores

Hay una amplia gama de propiedades disponibles para los gráficos que controlan el aspecto de los mismos. El diálogo **Propiedades del Gráfico** se muestra en la siguiente imagen:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep173.png)

## Mostrar el cuadro de diálogo Propiedades

Para editar las propiedades de un gráfico, muestre el cuadro de diálogo **Propiedades** realizando una de las siguientes acciones:

- Seleccione el gráfico y haga clic en el icono **Propiedades** ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/properties_icon_21x21.png) en la pestaña **Autor**.
- En la esquina superior izquierda del gráfico, haga clic en el pequeño triángulo ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png) situado junto al nombre del gráfico para mostrar el menú **Acciones**. En el menú **Acciones**, seleccione **Propiedades**.
- Haga clic con el botón derecho del ratón en la barra de título del gráfico y seleccione **Propiedades** en el menú emergente.

## Propiedades de los gráficos

A continuación se muestran las propiedades **del Gráfico**. Para ver todas las propiedades, es posible que tenga que desplazarse por la pantalla.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep173.png)

A continuación se describen los campos **del gráfico**. **NOTA** : algunos gráficos tendrán un subconjunto de estos campos. Los campos marcados con un asterisco (\*) sólo se aplican a los gráficos heredados y no a los gráficos ad hoc.

- **Etiqueta Eje X** - Selecciona la columna de origen para los valores del eje X en el gráfico.
- **Etiqueta Valor Y** - Selecciona la columna de origen para los valores del eje Y en el gráfico.
- **Escala del eje Y** - Seleccione Lineal o Logarítmica.
- **Estilo de gráfico\*** - Seleccione la opción Tarta, Barra, Barra horizontal, Barra apilada, Barra horizontal apilada, Radar relleno, Radar con marcadores o Tendencia (línea).
- **Color Spec** - Introduzca una cadena de formato de color para cambiar el color de una entidad en el gráfico. Para obtener más información, consulte [Configuración de los colores por defecto de las métricas en los gráficos](set-default-colors-charts.html "Se aplica a: TBM Studio 12.0 y posteriores").
- **Formato de números del** gráfico: introduzca un patrón para dar formato a los números del eje del gráfico. La sintaxis es la misma que utiliza la función NumberFormat pero sin el nombre de la función ni las comillas. Por ejemplo, para mostrar números como 5.000.000 $, introduzca #,###. No puede utilizar una fórmula en este campo.
  - Para eliminar todo el formato de los números, introduzca #.
  - Si está visualizando un cálculo métrico en el gráfico, el formato del gráfico anula el formato métrico. Si deja este campo (y los campos Prefijo numérico y Sufijo numérico) en blanco, se utilizará el formato por defecto especificado para la métrica que se está visualizando.
  - Para formatear números como moneda utilizando el símbolo de moneda de la configuración regional seleccionada para el proyecto, anteponga a la declaración de formato el símbolo Unicode de moneda universal (¤). La forma más sencilla de hacerlo es copiar el símbolo de la frase anterior y pegarlo en el campo.
  - Para más información sobre el formato de los números, consulte la [función NumberFormat](../formulas-and-functions/functions/numberformat.html "Da formato a un valor numérico en una etiqueta (cadena) utilizando patrones personalizados para números positivos y negativos, duraciones o formato de tamaño de datos. Esta función está diseñada para su uso en columnas de tipo Etiqueta.") en la *Guía de Studio*.
- **Prefijo del número del gráfico** - Introduzca el texto que se mostrará antes de todos los números del gráfico (por ejemplo, $ para dólares).
  - Si desea que las cifras en dólares se muestren en el formato $#.##M (por ejemplo, $7.28M ), introduzca un signo $ en este campo y borre todo el formato del campo **Formato de número de gráfico**.
  - Para formatear números como moneda utilizando el símbolo de moneda de la configuración regional seleccionada para el proyecto, introduzca el símbolo Unicode de moneda universal (¤) en el campo en lugar del signo $. La forma más sencilla de hacerlo es copiar el símbolo de la frase anterior y pegarlo en el campo. Utilice el símbolo Unicode en este campo o en el campo **Formato de número de gráfico**, pero no en ambos.
  - Si deja este campo en blanco, se utilizará el formato por defecto especificado para la métrica que se está visualizando.
- **Sufijo del número del gráfico** - Introduzca el texto que se mostrará después de los números en el gráfico (por ejemplo, M para millones).
- Si deja este campo en blanco, se utilizará el formato por defecto especificado para la métrica que se está visualizando.
- **Mostrar valores de datos** - Seleccione esta opción para mostrar los valores de datos de cada punto de datos del gráfico.
- **Gráficos de una sola serie multicolor** - En un gráfico con una sola serie de valores, por ejemplo, **Coste por unidad de negocio**, la serie se muestra en un solo color. Seleccione esta opción para mostrar cada elemento de la serie en un color diferente.
- **Invertir orden** - Invierte el orden de las series mostradas en los ejes x o y.
- **Ocultar eje X** - Oculta el eje X.
- **Ocultar eje Y** - Oculta el eje Y.
- **Ocultar líneas de cuadrícula** - Oculta las líneas de cuadrícula horizontales y verticales.
- **Ubicación de la leyenda** : seleccione una ubicación para la leyenda del gráfico o seleccione **Oculto** para que la leyenda sea invisible. La ubicación por defecto es Sur (debajo del gráfico).
- **Incluir cero en el eje Y** - Si se selecciona, esta opción fuerza al eje Y a empezar en 0. Si se desactiva, el eje Y puede comenzar en un número mayor para mostrar mejor las pequeñas variaciones.
- **Eje compartido** - Se utiliza sólo con gráficos superpuestos. Hace que las escalas de los ejes izquierdo y derecho sean iguales.
- **Rebanada explosionada** - Introduzca el nombre de una de las rebanadas que se va a desplazar ligeramente (explosionada) del resto del gráfico. En el ejemplo siguiente, se explota el trozo de Nueva York. También puede explotar una porción seleccionando una porción en un gráfico circular, haciendo clic con el botón derecho y seleccionando **Explotar**.

  ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep061.png)

## Propiedades de los datos de los gráficos

Las propiedades de Datos mostradas en la siguiente imagen controlan los datos mostrados en el gráfico:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep175.png)

A continuación se describen los campos de datos.

Nota: Algunos gráficos tendrán un subconjunto de estos campos. Los campos marcados con un (\*) sólo se aplican a los gráficos heredados y no a los gráficos ad hoc.

- **Máximo de filas** - Determina el número de elementos que se muestran en el gráfico.
  - En los gráficos de barras, controla el número de barras.
  - En los gráficos circulares, controla el número de porciones.
  - En los gráficos de líneas, controla el número de elementos en el eje X.
  - Si el número de elementos supera el número especificado en este campo, los elementos restantes se agruparán en un elemento denominado Otros.

  Consejo: Antes de poder ver estos datos, vaya a **Informes > Datos** y, en la opción **Suma**, seleccione **Mostrar otra fila**.
- **Incluir columnas\*** - Restringe las columnas mostradas a las seleccionadas de esta lista.
- **Excluir columnas\*** - Permite que se muestren todas las columnas excepto las seleccionadas de esta lista.
- **Mostrar filas para las que todos los valores métricos son 0\*** - Anula el comportamiento por defecto permitiendo que se muestren las filas de valor cero.
- **Pivotar conjunto de datos\*** - Pivota los datos contenidos en el gráfico, cambiando los ejes X e Y. Esta opción sólo se aplica a las cartas heredadas.

## Propiedades generales de los gráficos

Las propiedades **Generales** se muestran en la siguiente imagen. A medida que cambie la configuración, puede previsualizar los cambios haciendo clic en **Aplicar**.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep176.png)

A continuación se describen los campos **generales**.

- **Nombre** - Introduzca un nombre que se mostrará en la cabecera del gráfico encima del componente. El nombre aparece cuando se selecciona la opción **Mostrar encabezado**.
- **Leyenda** - Introduzca información adicional sobre el gráfico. La información se muestra en función de la configuración del campo **Posición del título**. Puede utilizar código HTML en este campo, pero el código HTML no puede incluir enlaces. La restricción del código HTML es por motivos de seguridad.
- **Posición del** título - En la lista, seleccione una posición de título relativa al gráfico. La información: **Arriba**, **Abajo**, **Izquierda** o **Derecha**, o seleccione **Ocultar** para no mostrar el pie de foto en absoluto.
- **Mostrar** borde - Seleccione esta opción para mostrar un borde alrededor del gráfico. Cuando el borde está oculto, puede detener el puntero del ratón sobre el gráfico para mostrarlo cuando esté en modo **Edición**.
- **Mostrar cabecera** - La cabecera del componente muestra el contenido del campo **Nombre**. Seleccione esta opción para hacer visible la cabecera del gráfico (por defecto). Cuando la cabecera está oculta, puede detener el puntero del ratón en el gráfico para mostrarla cuando esté en modo **Edición**.
- **Ajustar título** - Ajusta el texto introducido en el campo **Nombre** a la anchura del gráfico.

## Propiedades avanzadas de los gráficos

Las propiedades **Avanzadas** controlan varias opciones de visualización de los gráficos. La pestaña se muestra a continuación:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep177.png)

A continuación se describen los campos **avanzados**.

Nota: Algunos gráficos tendrán un subconjunto de estos campos. Los campos marcados con un (\*) sólo se aplican a los gráficos heredados y no a los gráficos ad hoc.

- **Datos URL** \* - Muestra la ruta a la tabla que suministra los datos para este informe. Puede introducir una función de tabla en este campo haciendo clic en el icono **Editar ruta de datos** situado a la derecha del campo. La aplicación muestra el cuadro de diálogo **Editar ruta**. **ATENCIÓN** : no modifique la ruta si no está muy familiarizado con las rutas de datos.
- **Actualizar automáticamente al finalizar los cálculos** - Cuando la aplicación muestra un gráfico, lo hace con los datos calculados disponibles en ese momento. En muchos casos, la aplicación puede estar calculando nuevos valores en segundo plano. Si desea que se muestren los resultados una vez finalizados los cálculos, marque esta opción.
  - Esta opción está disponible cuando la Política de cálculo de un proyecto (en el cuadro de diálogo **Cálculo del proyecto** ) está establecida en **Publicación dinámica**.
- **Período de tiempo de los datos** - Determina el período de tiempo aplicado al gráfico. Por defecto, la **Fecha actual del proyecto** muestra los datos de la fecha que aparece en el selector de fecha. Hay muchas otras opciones disponibles en la lista desplegable.
- **Ocultar advertencia de bloqueo de tiempo** : si ha configurado el campo **Período de tiempo de los datos** con un valor distinto de **la Hora actual del proyecto**, aparecerá un icono de bloqueo en la esquina inferior derecha del gráfico. Al marcar esta opción se oculta el icono.
- **Ocultar advertencia de hidratación** : si coloca un gráfico en un informe de objetos que se basa en una unidad diferente a la del propio informe, la aplicación muestra un icono de advertencia ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/hydration_warning.png) y un mensaje de texto en la esquina inferior derecha del componente en el modo Editar. No se muestran en el modo Vista. Si selecciona esta opción, las advertencias no se mostrarán en el modo Edición.
  - Por ejemplo, suponga que tiene un objeto Unidades de Negocio y que desglosa un informe de la Unidad de Negocio A con un gráfico y una tabla que muestran datos sobre la Unidad de Negocio A. En el mismo informe, desea mostrar información sobre la Unidad de Negocio B con fines comparativos. Se añaden componentes al informe para mostrar esta información. Como lo ha hecho intencionadamente, no quiere que la aplicación muestre el aviso de hidratación, por lo que selecciona la opción **Ocultar aviso de hidratación**.
- **Acortar automáticamente nuevos nombres de columna con puntos** - Muestra sólo la parte de un nombre de columna que sigue a la "." punto. Por ejemplo, si el nombre de la columna es Data Center Costs.Data Center Hosting Cost, el nombre se mostraría como Data Center Hosting Cost.
- **Líneas por fila** - Este campo se utiliza con tablas y no se aplica a los gráficos. Deje el campo en blanco.
- **Máx. Columnas a mostrar** - Determina el número máximo de columnas procesadas en la tabla de origen. Esto no afecta a los datos mostrados en el gráfico.
- **Col fila pivotante\*** - La columna de la tabla de origen que proporciona los valores para la primera columna de la tabla pivotante.
- Columna **pivotante Col\*** - La columna de la tabla de origen que proporciona los encabezados para las columnas de datos de la tabla pivotante.
- **Pivot Val Col\*** - La columna de la tabla de origen que proporciona los valores para las celdas de la tabla pivotada.
- **Incluir columna PK** - Incluirá la columna por defecto en el gráfico, esté o no especificada en la lista normal de "columnas a incluir". Para los gráficos que muestran datos no agrupados, suele ser el identificador del objeto que respalda el componente del informe. Para los gráficos que muestran datos agrupados, suele ser la columna utilizada para la agrupación.
- **Usar alias de columna** - En circunstancias en las que tiene dos objetos con las mismas columnas mostradas en la misma tabla como Consumer.Master Table.L0 Nombre y Provider.Master Table.L0 Nombre, marcando esta opción es posible configurar correctamente las columnas en la tabla. **Recomendación** : Deje esta opción seleccionada.
