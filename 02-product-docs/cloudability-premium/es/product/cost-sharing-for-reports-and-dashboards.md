---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Reparto de costes de informes y cuadros de mando"
breadcrumb:
  - "Cloudability Premium"
  - "Configuración"
  - "Reparto de costes en Cloudability"
source_path: "product/cost-sharing-for-reports-and-dashboards.html"
images:
  - "images/costsharing1.png"
  - "images/costsharing10.png"
  - "images/costsharing11.png"
  - "images/costsharing12.png"
  - "images/costsharing13.png"
  - "images/costsharing14.png"
  - "images/costsharing15.png"
  - "images/costsharing16.png"
  - "images/costsharing2.png"
  - "images/costsharing3.png"
  - "images/costsharing4.png"
  - "images/costsharing5.png"
  - "images/costsharing6.png"
  - "images/costsharing7.png"
  - "images/costsharing8.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Reparto de costes de informes y cuadros de mando

## Visión general

Un nuevo conmutador de costes compartidos en el editor de informes y widgets de cuadros de mando de Cloudability permite a los usuarios generar visualizaciones de datos a partir de datos de informes con costes asignados (compartidos) aplicados. Cuando se activa en un informe o widget, los resultados reflejan los costes asignados según las reglas configuradas en **Cloudability → Reparto de costes**.

Cómo empezar

1. Abra cualquier editor de informes o widgets.
2. Busque el botón de reparto de costes en la sección de cabecera.
3. Pulse el botón para ver sus datos con los costes imputados.
4. Explore las nuevas medidas de Tipo de Coste y Fuente de Imputación.
5. Guarda tu widget y busca la insignia de asignación en el título.

Puntos clave:

- Los usuarios pueden activar/desactivar **el reparto de costes** por informe o widget de apoyo.
- Al previsualizar o guardar un informe o widget se muestra cómo cambian los datos cuando se aplica el reparto de costes.
- Ahora hay disponibles medidas adicionales que sólo se admiten cuando está activado el reparto de costes.

Normas de asignación y ámbito de aplicación

- Las reglas de asignación se crean y gestionan en la función **de reparto de costes**.
- Las normas **sólo se aplican a Business Dimensions**. (Las dimensiones no empresariales no son objetivos de asignación)

Activación y desactivación de informes y widgets

- Cada tipo de widget compatible tiene un conmutador de **reparto de costes** (Aplicado / No aplicado) en la parte de la cabecera del cajón Crear/Editar informe y widget.
- Conmutar actualiza los parámetros de consulta utilizados para previsualizar y guardar el widget.
- El título del widget muestra una **insignia de asignación** cuando se aplica el reparto de costes, para que los usuarios puedan ver de un vistazo que las reglas de asignación han afectado al conjunto de resultados.
- Las Dimensiones de Negocio que tienen asignaciones aplicadas muestran un **icono de asignación** en todos los componentes de selección de dimensión.

![costsharing14](../../../../03-media/cloudability-premium/images/costsharing14.png)![costsharing15](../../../../03-media/cloudability-premium/images/costsharing15.png)![costsharing16](../../../../03-media/cloudability-premium/images/costsharing16.png)

Medidas disponibles con participación en los gastos

Cuando se **aplica** el reparto de costes, ahora se admiten las siguientes medidas nuevas:

- **Tipo de coste**

  Indica si un valor de dimensión tiene coste **Directo** o **Compartido**.
- **Fuente de asignación**

  Desglosa a qué dimensiones de la empresa se atribuyen los costes compartidos.

Dimensiones y sistema métrico

- Algunas **dimensiones/métricas sólo se admiten** cuando se **aplica** el reparto de costes.
- Por el contrario, otros **no se admiten** en ese estado.

Comportamiento en el editor:

- **Los elementos compatibles** siguen siendo seleccionables y utilizables.
- **Los elementos no admitidos** son:
  - Marcado con un **icono de error** si se ha seleccionado previamente y el usuario cambia los Cost Sharing a un estado en el que no son válidos.
  - **Desactivado** en los selectores para evitar una nueva selección.

![costsharing1](../../../../03-media/cloudability-premium/images/costsharing1.png)![costsharing2](../../../../03-media/cloudability-premium/images/costsharing2.png)![costsharing3](../../../../03-media/cloudability-premium/images/costsharing3.png)

Vista previa/Guardar solicitud Saneamiento

Para evitar errores de backend cuando se activa el reparto de costes:

- Al **previsualizar** o **guardar**, se **eliminan de la solicitud** todas las **dimensiones, métricas y filtros no admitidos** (dado el estado actual del conmutador).
- De este modo, se evitan las solicitudes fallidas debidas a combinaciones no válidas y se garantiza que la visualización se muestra correctamente con los campos admitidos.
- Al crear un informe o un widget de cuadro de mando, se notifica al usuario las medidas no admitidas que se han eliminado en el proceso de guardado.

![costsharing4](../../../../03-media/cloudability-premium/images/costsharing4.png)![costsharing5](../../../../03-media/cloudability-premium/images/costsharing5.png)

Creación de informes desde el widget de gráficos

- Un tooltip del Widget de Gráfico puede dirigir al usuario a un Informe. En la vista previa del widget, nos aseguramos de que sólo las medidas compatibles se incluyan en el informe generado a partir de los datos del widget de gráfico.

![costsharing6](../../../../03-media/cloudability-premium/images/costsharing6.png)

Filtros

- Los filtros **no pueden** dirigirse a dimensiones no admitidas.
- Si un usuario ha establecido previamente un filtro de este tipo y, a continuación, cambia a un estado no admitido:
  - El filtro muestra un **icono de error** en el editor.
  - Las opciones no seleccionadas se desactivan.
  - El filtro se **omite** en las solicitudes de Vista previa/Guardar.

![costsharing7](../../../../03-media/cloudability-premium/images/costsharing7.png)

Validación y notificaciones

- Los informes requieren al menos **una dimensión y una métrica**.
- Si al activar el reparto de costes la configuración deja de ser válida (por ejemplo, la dimensión única deja de ser compatible), el usuario no podrá elaborar un informe válido.
  - La interfaz de usuario muestra una **notificación de error** que explica que la configuración no es compatible con el estado actual de reparto de costes.

![costsharing9](../../../../03-media/cloudability-premium/images/costsharing8.png)

Si un usuario está intentando utilizar la nueva medida 'Fuente de Asignación', la configuración soportada para esta petición es incluir con 'Fuente de Asignación' al menos una Dimensión de Negocio, y otra dimensión.

- La interfaz de usuario muestra una **notificación de error tostada** que explica que la configuración no es compatible si no se cumplen estas condiciones.

Reglas de persistencia del Estado

- Durante la edición, la interfaz de usuario **conserva** visualmente las selecciones no admitidas (marcadas con errores) para que los usuarios puedan activar/desactivar **rápidamente** el reparto de costes y comparar los resultados con la **misma configuración prevista**.
- On **Save** :
  - **Los elementos no compatibles no se mantienen** en la definición del widget (porque una configuración de este tipo no puede producir un informe válido).
  - Los usuarios conservan la posibilidad de alternar y previsualizar mientras editan, pero los widgets guardados nunca incluyen campos no válidos.

Reparto de costes en los informes

- Todas las funciones son coherentes en los informes y cuadros de mando de CLDY. Los widgets pueden configurarse con costes compartidos aplicados directamente desde un informe y copiarse en el panel de control de un usuario.
- Los informes y widgets pueden exportarse y compartirse utilizando la función existente de exportación de informes.
- También puede suscribirse a un informe con reparto de costes a través del cajón de suscripción a informes.
- Un Informe puede copiarse al Cuadro de Mando, persistiendo el valor del Coste Compartido aplicado en el widget creado.

![costsharing10](../../../../03-media/cloudability-premium/images/costsharing10.png)

Resumen de la experiencia de usuario esperada

1. El usuario abre un widget, elige dimensiones/métricas y, opcionalmente, activa **el reparto de costes**.
2. El editor muestra:
   - Iconos de asignación en las Dimensiones Empresariales aplicables.
   - Iconos de error en los campos que dejan de ser compatibles al cambiar el estado de reparto de costes.
3. En Vista previa/Guardar:
   - Los campos/filtros no admitidos se **eliminan automáticamente** de la solicitud.
   - Si la eliminación hace que la configuración no sea válida, un **brindis de error** informa al usuario.
4. Después de guardar:
   - El título del widget muestra un **distintivo de asignación** si se aplica el reparto de costes.
   - El widget guardado sólo contiene los campos **admitidos** para su estado de reparto de costes.

Widgets de ejemplo:

1. Tabla que muestra la Dimensión de Negocio c/regla de asignación aplicada y la Categoría de Asignación de los valores de esta métrica:

![costsharing11](../../../../03-media/cloudability-premium/images/costsharing11.png)

Gráfico de Barras Apiladas mostrando el Tipo de Coste de los valores de una Dimensión de Negocio c/ regla asignada aplicada, apilado, mostrando métricas de coste(total) y coste(amortizado):

![costsharing12](../../../../03-media/cloudability-premium/images/costsharing12.png)

Comparación de dos gráficos circulares de la misma dimensión empresarial, que muestran cómo varía la métrica de coste (total) cuando se aplica o no el coste compartido:

![costsharing13](../../../../03-media/cloudability-premium/images/costsharing13.png)

**Tema principal:** [Compartir costes en Cloudability](../product/cost-sharing.html)
