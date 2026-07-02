---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Organizar los componentes del informe"
breadcrumb: []
source_path: "studio/reports/arrange-report-components.html"
images:
  - "resources/images/studio_images/studioimages/reports/studio_report_components_align.png"
  - "resources/images/studio_images/studioimages/reports/studio_report_components_front_back.png"
  - "resources/images/studio_images/studioimages/reports/studio_report_components_horiz-vert.png"
  - "resources/images/studio_images/studioimages/reports/studio_report_components_snap_to_grid.png"
  - "resources/images/studio_images/studioimages/reports/studio_report_components_width_height.png"
  - "resources/images/studio_images/studioimages/reports/studio_reports_arrange_reports.png"
  - "resources/images/studio_images/studioimages/reports/studio_reports_visibility_1100x167.png"
  - "resources/images/studio_images/studioimages/studio_arrange_report_components_set_position_and_size.jpg"
  - "resources/images/studio_images/studioimages/studio_component_visibility_report_component_visibility.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Organizar los componentes del informe

**Se aplica a** : TBM Studio 12.0 y posteriores

TBM Studio R12 ofrece herramientas de diseño flexibles para colocar y organizar los componentes de un informe. La mayoría de estas herramientas de diseño se encuentran en la pestaña **Formato** :

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_reports_arrange_reports.png)

## Seleccionar componentes

Al menos un componente debe estar seleccionado para activar los comandos de la pestaña **Formato**. Para empezar, haga clic en la cabecera del componente que desea modificar. Por defecto, la cabecera del informe muestra el nombre del componente.

Algunas herramientas de diseño requieren la selección de varios componentes. Para seleccionar más de un componente:

- **En Windows** : Mantenga pulsada la tecla **Ctrl** y, a continuación, haga clic en la cabecera de cada componente que desee modificar.
- **En MacOS** : Mantenga pulsada la tecla **Alt** y, a continuación, haga clic en la cabecera de cada componente que desee modificar.

## Desplazar componentes del informe

En un informe, puede reposicionar los componentes.

- Haga clic y mantenga pulsada la cabecera del componente del informe y, a continuación, arrastre el componente a una nueva ubicación.

Si desplaza un componente a una posición en la que se solapa con otro, puede seleccionar qué componentes deben estar delante del otro.

1. Seleccione el componente.
2. En la pestaña **Formato**, en el grupo **Posición y tamaño**, haga clic en **Traer al frente** o **Enviar al fondo**.

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_report_components_front_back.png)

## Alinear componentes

Utilice los comandos del grupo Alinear de la pestaña Formato para controlar el aspecto relativo de dos o más componentes. Estos comandos sólo se activan después de seleccionar dos o más componentes en un informe.

1. Seleccione los dos o más componentes que desea alinear.
2. En el grupo **Alinear** de la pestaña **Formato**, haga clic en las opciones de alineación que desee.

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_report_components_align.png)

Los comandos **Izquierda**, **Centro** y **Derecha** controlan la alineación horizontal de los componentes seleccionados. Los comandos **Superior**, **Medio** e **Inferior** controlan la alineación vertical de los componentes seleccionados.

## Cambiar el tamaño de los componentes del informe

Cambie el tamaño de un componente del informe arrastrando la parte inferior, los lados o las esquinas del borde de un componente.

1. Sitúe el puntero del ratón sobre la parte inferior, lateral o esquina del borde de un componente. El puntero del ratón cambiará a Resize icon.If el borde está oculto, posicione el puntero del ratón en cualquier lugar sobre el componente para ver su borde.
2. Cuando aparezca el icono Redimensionar, haga clic y arrastre el borde para cambiar la altura o anchura del componente.

## Distribuir componentes

Para espaciar uniformemente los componentes horizontal o verticalmente en un informe, utilice los comandos del grupo Distribuir. La aplicación utiliza los componentes externos para establecer los límites y, a continuación, distribuye los componentes uniformemente dentro de los límites. Si es necesario, la aplicación solapará componentes.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_report_components_horiz-vert.png)

## Hacer que los componentes tengan el mismo tamaño

Para que los gráficos y las tablas de un informe tengan el mismo tamaño, utilice los comandos del grupo **Igualar tamaño**. La aplicación utiliza el primer componente que seleccione como estándar y redimensiona todos los demás componentes para que coincidan. Puedes redimensionar la anchura, la altura o ambas.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_report_components_width_height.png)

## Ajustar a cuadrícula

Cuando se selecciona **Ajustar a cuadrícula**, los componentes se ajustarán al punto más cercano de una cuadrícula invisible.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_report_components_snap_to_grid.png)

## Fijar la posición y el tamaño de los componentes mediante coordenadas

Para posicionar o dimensionar componentes con precisión, utilice **Fijar posición y tamaño**. Los componentes pueden colocarse en relación con la ventana del informe o con un marco de grupo.

Tanto los números de posición como los de tamaño se muestran en píxeles. También puede utilizar números negativos (hasta -24 píxeles) en el campo de posición X. Esto es útil si desea ocultar la cabecera del componente y desplazar el componente al borde superior del cuadro de grupo.

1. Haga clic con el botón derecho del ratón en el componente que desee mover y, a continuación, en **Posición y tamaño**.
2. Introduzca los valores de posición y tamaño (en píxeles) que desee.

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_arrange_report_components_set_position_and_size.jpg)
3. Haga clic en **Aplicar** para guardar los cambios y, a continuación, en **Aceptar** para cerrar la ventana.

## Fijar la visibilidad de los componentes

Puede controlar si componentes enteros aparecen bajo ciertos criterios.

1. Seleccione un componente.

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_reports_visibility_1100x167.png)
2. En el grupo Avanzado de la pestaña **Informe**, haga clic en **Visibilidad**.

   Las opciones del cuadro Visibilidad de los componentes del informe varían en función del tipo de componente seleccionado.

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_component_visibility_report_component_visibility.jpg)

Las opciones pueden incluir:

El **componente contiene datos** : Ocultará el componente seleccionado si no contiene o calcula datos.

**Rol actual del usuario** : Permite elegir roles específicos que pueden ver el componente seleccionado.

**El texto dinámico no se evalúa como "oculto"** : Oculta el componente si el argumento se resuelve como "oculto"

**Ejemplo** : Quiero que un componente sea visible si la varianza es negativa. Si la varianza es positiva, establecer como "oculta"

## Configuración de la página impresa

Para establecer la orientación y el tamaño de página de los informes impresos, y para ver el informe en la vista Página, utilice las herramientas de Diseño de impresión. Para obtener más información, consulte [Imprimir y exportar informes](printexportreports.html "Se aplica a: Apptio TBM Studio R12.5 y posteriores. TBM Studio se basa en la exportación de informes a formato PDF para imprimirlos y compartirlos fuera de la suite TBM. El administrador de TBMA o TBM Studio puede personalizar las opciones de diseño PDF por informe para todos los usuarios de Apptio al imprimir o enviar informes por correo electrónico.").
