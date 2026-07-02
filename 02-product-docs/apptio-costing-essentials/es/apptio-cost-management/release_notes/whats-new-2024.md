---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "es"
doc_type: "apptio-cost-management"
title: "Notas de la versión 2024"
breadcrumb:
  - "Costing Essentials"
  - "Notas del release"
source_path: "apptio-cost-management/release_notes/whats-new-2024.html"
images:
  - "resources/images/studio_images/compound-filter.jpg"
  - "resources/images/studio_images/config-filter.jpg"
  - "resources/images/studio_images/null-value-filter.jpg"
  - "resources/images/studio_images/r-notes/cp1.jpg"
  - "resources/images/studio_images/r-notes/cp2.jpg"
  - "resources/images/studio_images/r-notes/eud-1.jpg"
  - "resources/images/studio_images/r-notes/eud-2.jpg"
  - "resources/images/studio_images/report-filter.jpg"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Notas de la versión 2024

## Costing Essentials Mejoras ( v200 ) - 22 de noviembre de 2024

En esta versión se han introducido los dos nuevos componentes siguientes.

- Componentes de dispositivos de usuario final (GA) : Hay un nuevo componente de dispositivos de usuario final disponible en la plantilla v200. Proporciona información útil para que los gestores de activos de TI y los gestores de soporte técnico puedan tomar decisiones basadas en datos sobre la optimización y consolidación de la flota, lo que les ayuda a determinar el tamaño total de la flota y los costes asociados. También ayudará a planificar y prever los costes estimados de renovación de los dispositivos que han llegado al final de su vida útil y los que no cumplen con la normativa.

  ![Imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/r-notes/eud-1.jpg)

  ![Imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/r-notes/eud-2.jpg)

  Para obtener más información, consulte [Dispositivos de usuario final](../getting_started/eud-intro.htm "(se abre en una pestaña o una ventana nueva)").
- Componente Cost Pool Benchmark (BETA) : Cost Pool Benchmark proporciona información útil para los responsables de TI y finanzas de TI a la hora de tomar decisiones estratégicas de inversión relacionadas con el papel de las TI en la empresa, el modelo operativo actual de TI y las estrategias de abastecimiento. Los puntos de referencia pueden utilizarse para comprender la estructura de costes de la estrategia actual y para justificar o ajustar los enfoques actuales de inversión y abastecimiento. Compare el gasto en TI con los valores de referencia del sector (por ejemplo, el gasto en TI como porcentaje de los ingresos)

  ![Imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/r-notes/cp1.jpg)

  ![Imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/r-notes/cp2.jpg)

  Para obtener más información, consulte [Puntos de referencia de costes compartidos](../admin/setup-be.html).

## Apptio Transición de la comunidad a IBM TechXchange - 1 de noviembre de 2024

Hoy, la comunidad Apptio ha completado su transición a IBM TechXchange

## ApptioCosting Essentials Ahora disponible en japonés - 16 de agosto de 2024

La aplicación Costing Essentials (ACE) ahora está completamente localizada en japonés, lo que mejora la usabilidad para los usuarios de habla japonesa. Todas las cadenas utilizadas en ACE se han traducido al japonés y se han integrado en nuestro sistema. Se ha redimensionado y realineado el contenido dentro de la aplicación para mejorar el ajuste y el acabado general. Estos cambios garantizan una experiencia de usuario más pulida y visualmente atractiva.

## IBMCosting Essentials Apptio GA - 5 de julio de 2024

IBMCosting Essentials Apptio ha lanzado Template v200, diseñado para optimizar y simplificar las soluciones de cálculo de costes para nuestros usuarios. Es una solución de cálculo de costes prescriptiva creada en R12, diseñada para clientes más pequeños y menos complejos. Se implementa a través de CS Delivery para la configuración inicial y TAS para el soporte continuo. Utiliza componentes estándar para facilitar su uso y garantizar la coherencia en todas las implementaciones.

Los administradores pueden crear nuevos proyectos utilizando el tipo de proyecto «Costing
Essentials». Estos proyectos constan de componentes creados directamente en R12. Es un marco actualizable que admite componentes futuros, ampliando la funcionalidad a Costing Standard. Utiliza tablas editables para la introducción y el mantenimiento de datos, incluyendo asignaciones que impulsan métodos de asignación predefinidos.

![Imagen](../../resources/images/studio_images/r-notes/rn-12117-1_662x386.png)

![Imagen](../../resources/images/studio_images/r-notes/rn-12117-2_1372x764.png)

![Imagen](../../resources/images/studio_images/r-notes/rn-12117-3_1377x754.png)

## Costing Essentials Comunicado de prensa 12.11.4, 1 de marzo de 2024

Mejoras en el filtrado para los clientes de Costing Essentials que utilizan Apptio BI

A partir de hoy, los usuarios pueden filtrar rápida y fácilmente los datos para acceder a la información más importante. Antes de esta versión, Costing Essentials los usuarios no podían filtrar la información de una manera tan eficaz.

Mejoras

- Filtros a nivel de informe,
- Filtrado compuesto con opciones de agregación previa y posterior
- Filtrado de valores nulos.

Característica 1: Filtros a nivel de informe

Esta mejora permite a los usuarios configurar filtros a nivel de informe y aplicarlos a todas las visualizaciones que pertenecen a dicho informe. Una vez creados, los filtros de nivel de informe se muestran en la parte superior del informe.

Pasos para crear un filtro a nivel de informe:

1. En la esquina superior derecha de un informe, seleccione y vaya a Gestionar filtros de informe.
2. En la lista Fuente de datos, seleccione la fuente de datos requerida.
3. Seleccione Añadir dimensiones y, a continuación, seleccione la dimensión en la que desea basar el filtro.
4. Seleccione Aplicar.

![Imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/config-filter.jpg)

![Imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/report-filter.jpg)

Para obtener más información, consulte [Filtros a nivel de informe](../../apptio_bi/self-service-reporting_user_guide/bi-create-and-manage-report-filters.htm "(se abre en una pestaña o una ventana nueva)").

Característica 2: Filtrado compuesto con opciones de agregación previa y posterior

Esta mejora permite a los usuarios crear consultas complejas para filtrar la información más importante. Está disponible en modo de edición y permite a los usuarios definir sentencias con múltiples operaciones AND y OR que se pueden aplicar antes o después de la agregación. La preagregación aplicará el filtro a cada línea individual del conjunto de datos, mientras que la posagregación aplicará el filtro después de que los datos se hayan agregado.

Pasos para crear un filtro a nivel de informe:

En el modo de edición, desplázate hacia abajo por el panel de navegación lateral izquierdo hasta llegar a Filtros.

1. Seleccione si el filtro debe aplicarse antes o después de la agregación.
2. Defina la consulta que desea procesar seleccionando las medidas, los operadores y los valores adecuados.
3. Combine las consultas utilizando las conjunciones AND y OR si es necesario.

![Imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/compound-filter.jpg)

Característica 3: Filtrado de valores nulos

Esta mejora permite a los usuarios filtrar fácilmente los valores nulos y centrarse en la información más relevante.

Pasos para aplicar el filtrado de valores nulos:

En el modo de edición, desplázate hacia abajo por el panel de navegación lateral izquierdo hasta llegar a Filtros.

1. Seleccione si el filtro debe aplicarse antes o después de la agregación.
2. Elija la medida que desea filtrar.
3. Como operador,seleccione: «es nulo» o «no es nulo», dependiendo de la información que desee ver.
4. Seleccione Aceptar.

![Imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/null-value-filter.jpg)
