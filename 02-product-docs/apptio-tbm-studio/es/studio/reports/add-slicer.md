---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir una cortadora"
breadcrumb: []
source_path: "studio/reports/add-slicer.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep017.png"
  - "resources/images/studio_images/studioimages/reports/rep044.png"
  - "resources/images/studio_images/studioimages/studio/stu625.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir una cortadora

**Se aplica a** : TBM Studio 12.0 y posteriores

Puede añadir un número ilimitado de cortadoras a un informe. Después de añadir las cortadoras, puede moverlas y ajustar su tamaño.

Los cortadores pueden ser una lista o un deslizador. Los campos de texto crean rebanadas de lista. Los campos numéricos crean correderas.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep017.png)

## Añadir una cortadora

Para añadir un slicer a un informe:

1. Visualice el informe en el que desea añadir el slicer.
2. Seleccione **Row Slicer** en la pestaña **Informe**. La aplicación añade un objeto slicer en blanco al informe y muestra el panel de **Configuración del Slicer** que se muestra en la siguiente imagen:

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu625.png)
3. Arrastre un campo de una perspectiva (Dimensiones, Cálculos o Tiempo) al área **Cortar por**.

Los valores de los campos se muestran en el slicer. Los campos de texto crean rebanadas de lista. Los campos numéricos crean controles deslizantes. Los campos bloqueados son campos que se han añadido a dimensiones personalizadas. Para obtener más información sobre perspectivas personalizadas, consulte [Creación de perspectivas personalizadas](creating-custom-perspectives.htm "(se abre en una pestaña o una ventana nueva)").

## Desplazar y dimensionar cortadoras

Después de haber colocado un slicer en un informe, puede realizar las siguientes acciones:

- Mueva la cortadora haciendo clic en la barra de título y arrastrando la cortadora a una nueva posición.
- Cambie el tamaño de la rebanadora arrastrando los bordes y esquinas izquierdo, derecho e inferior.

## Cambiar los estilos de la cortadora

Hay varios esquemas de color disponibles para las cortadoras. Para aplicar una combinación de colores, seleccione un estilo en la pestaña Rebanadora.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep044.png)

## Configurar las opciones de búsqueda

Si hay muchos valores en una rebanadora, puede introducir texto en el cuadro de búsqueda automática situado en la parte superior de la rebanadora para limitar la lista de valores. Cuando añades el slicer a un informe, puedes seleccionar una de las dos opciones de búsqueda siguientes.

- **Contiene** - Busca todos los valores que incluyen los caracteres introducidos. Si el usuario escribe abc, el filtro encontrará abcefg, defabc y defabcefg, pero no abdc ni adbc.
- **Empieza por** - Busca todos los valores que empiezan por los caracteres introducidos. Si el usuario escribe abc, el filtro encontrará abcefg y abc, pero no dabc ni 1abc.

Para obtener información más detallada sobre estas opciones, consulte [Seleccionar una opción de búsqueda](select-search-option.html "Se aplica a: TBM Studio 12.0 y posteriores").

## Ocultar el campo de búsqueda

En la parte superior de una rebanadora aparece un campo de búsqueda. Los usuarios pueden introducir texto en el campo para limitar el número de elementos mostrados en el slicer. Si está creando un slicer con un número reducido de elementos, y no habrá barra de desplazamiento en el slicer, puede ocultar el campo de búsqueda. Para ocultar el campo de búsqueda:

1. Abra las **Propiedades de** la cortadora haciendo clic en la flecha hacia abajo situada a la izquierda del nombre de la cortadora.
2. Desactive la opción **Mostrar filtro de búsqueda automática** en la pestaña **General**.
