---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Ver y configurar paneles de control"
breadcrumb:
  - "Cloudability Premium"
  - "Trabajar con cuadros de mando e informes"
  - "Cloudability Paneles de control"
source_path: "product/view-and-configure-dashboards.html"
images:
  - "images/date-range-selector.png"
  - "images/delete-grey.png"
  - "images/duplicate-grey.png"
  - "images/export-widget.png"
  - "images/interactive-widgets.png"
  - "images/on-hover-widget.png"
  - "images/widget-icons.png"
  - "images/widget-navigation.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Ver y configurar paneles de control

Acceder a la página del panel de control es una excelente manera de explorar en detalle su gasto en la nube. Los paneles de control pueden abordar una gran variedad de casos de uso y se pueden personalizar según los requisitos específicos de su empresa.

Hay diferentes acciones que puedes realizar para cada configuración, dependiendo de tus permisos.

**Añadir widget**

Al hacer clic en el icono «Añadir widget», los usuarios pueden crear un nuevo widget en el panel de control actual. Encontrará una descripción detallada de esta funcionalidad en la página «Crear o editar un widget en un panel de control» de la documentación.

Para crear un nuevo widget se necesitan permisos de edición para el panel de control actual.

**Vistas en paneles de control**

Cloudability Las vistas se respetan cuando se trabaja con paneles de control de Cloudability. Las vistas se pueden seleccionar utilizando el menú desplegable «Vista actual» situado en la parte superior derecha de la página. Los usuarios también pueden navegar a la página «Vistas» al seleccionar la opción «Administrar vistas...» en el menú desplegable. Al hacer clic en la «X» situada junto al nombre de la vista en este menú desplegable, se borrará la vista aplicada.

**Paneles favoritos**

Al visualizar un panel de control, los usuarios pueden navegar rápidamente a otro panel de control favorito haciendo clic en el icono de estrella amarilla situado en la parte superior izquierda del panel de control. Esto abrirá un menú contextual que mostrará todos sus paneles favoritos, lo que permitirá navegar rápidamente entre los paneles importantes. La lista de paneles favoritos se puede modificar desde la lista «Todos los paneles».

**Intervalo de fechas del panel de control**

Con esta opción, los usuarios pueden cambiar el intervalo de fechas que se aplica a todos los widgets de un panel de control determinado. Esta configuración ajusta temporalmente el intervalo de fechas, y solo para los usuarios actuales, lo que permite que diferentes personas trabajen con el mismo panel de control al mismo tiempo. El intervalo de fechas del panel de control no requiere permisos de edición para el panel de control.

Hay varias selecciones preconfiguradas disponibles para esta opción:

- Ayer
- Hoy (UTC)
- Esta semana
- Semana pasada
- Este mes
- Último mes
- Este trimestre
- Último trimestre
- Este año
- Último año
- Últimos 7 días
- Últimos 14 días
- Últimos 30 días
- Últimos 60 días
- Últimos 90 días

Los usuarios también pueden seleccionar cualquier intervalo de fechas personalizado eligiendo las fechas con el calendario modal o escribiendo el intervalo de fechas manualmente.

![](../../../../03-media/cloudability-premium/images/date-range-selector.png)

La selección del intervalo de fechas se puede borrar haciendo clic en el icono «X» situado junto al intervalo de fechas configurado.

[ADVERTENCIA] Algunas fuentes de datos no admiten la configuración del intervalo de fechas del panel de control. Los widgets que utilizan fuentes de datos **de Rightsizing** o **Estimate** conservarán el intervalo de fechas configurado en el nivel del widget.

**Compartir un panel de control**

Esta opción se describe detalladamente en la sección «Compartir un panel» de esta documentación.

**Anotar**

Esta opción se describe detalladamente en la sección «Anotar en paneles» de esta documentación.

**Duplicar un panel de control**

![](../../../../03-media/cloudability-premium/images/duplicate-grey.png)Al hacer clic en el icono «Duplicar», se creará una copia del panel de control actual. Esta es otra opción para copiar un panel, tal y como se describe en «Copiar un panel» en la sección Lista de paneles.

**Eliminar un panel de control**

![](../../../../03-media/cloudability-premium/images/delete-grey.png)Al hacer clic en el icono «Eliminar», se eliminará definitivamente el panel de control actual. Esta funcionalidad es equivalente a la funcionalidad «Eliminar» de la página «Lista de paneles».

Desde el panel de control, los usuarios también pueden realizar acciones específicas de los widgets. Hay varias opciones disponibles al pasar el cursor sobre un widget.

![](../../../../03-media/cloudability-premium/images/widget-icons.png)

**Editar**

Al hacer clic en el icono «Editar», los usuarios pueden modificar el widget existente. Encontrará una descripción detallada de esta funcionalidad en la página «Crear o editar un widget en un panel de control» de la documentación.

Para editar un widget se necesitan permisos de edición para el panel de control actual.

**Copiar**

Al hacer clic en el icono «Copiar», los usuarios pueden copiar el widget seleccionado y añadirlo al mismo panel de control o a otro diferente. Para copiar el widget solo se necesitan permisos de visualización del panel de control actual, pero para guardar una copia del widget se necesitan permisos de edición en el panel de control de destino.

**Exportar**

Los usuarios pueden elegir descargar los datos de un widget determinado en un formato separado por comas haciendo clic en el icono «Exportar». Esta opción mostrará un modal informativo en la parte inferior izquierda de la página, informando al usuario de que se está generando el informe. Una vez que los datos estén listos, comenzará la descarga de datos. Cada capa del widget y cada comparación de fechas generarán un archivo independiente con valores separados por comas. El permiso «Ver» es suficiente para exportar los datos de un widget.

![](../../../../03-media/cloudability-premium/images/export-widget.png)

Los tipos de widgets «Rightsizing» y «Estimate» no se pueden exportar.

**Suprimir**

Los usuarios pueden eliminar un widget haciendo clic en el icono «Eliminar». Se pedirá a los usuarios que confirmen la eliminación de un widget.

[ADVERTENCIA] Esta acción no se puede deshacer.

**Widgets interactivos**

Los widgets de los paneles de control de Cloudability son interactivos para permitir un mejor análisis en tiempo real de sus datos.

Los usuarios pueden elegir ocultar o mostrar las dimensiones haciendo clic en el nombre de cada dimensión en la leyenda para centrarse en los elementos que más les interesan en ese momento.

![](../../../../03-media/cloudability-premium/images/interactive-widgets.png)

Al pasar el cursor sobre una sección de un widget, se muestra información adicional, como el valor exacto de la métrica en un punto determinado del gráfico, o se muestran anotaciones adicionales relevantes para un punto de datos.

![](../../../../03-media/cloudability-premium/images/on-hover-widget.png)

Al hacer clic en una sección de un widget, los usuarios pueden navegar a un informe más detallado para realizar un análisis más profundo.

![](../../../../03-media/cloudability-premium/images/widget-navigation.png)

- **[Crear o editar un widget en un panel de control](../product/create-or-edit-a-widget-in-a-dashboard.html)**
- **[Compartir un panel de control](../product/share-a-dashboard.html)**
- **[Anotar en paneles de control](../product/annotate-in-dashboards.html)**

**Tema principal:** [Paneles de control de Cloudability](../product/cloudability-dashboards.html)
