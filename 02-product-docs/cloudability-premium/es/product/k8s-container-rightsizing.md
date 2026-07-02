---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Redimensionamiento para contenedores Kubernetes"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/k8s-container-rightsizing.html"
images:
  - "images/cloudy-vertical-elipsis.jpg"
  - "images/containers-summary-kpis.jpg"
  - "images/edit-icon.jpg"
  - "images/kubernetes-rightsizing-dash-new.png"
  - "images/rightsizing-recommendation-detail.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Redimensionamiento para contenedores Kubernetes

Con Cloudability rightsizing for Kubernetes containers, puede ver recomendaciones para optimizar sus despliegues de contenedores Kubernetes basándose en los 10 o 30 días anteriores de uso de recursos.

Más información sobre [el redimensionamiento en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Más información sobre [Cloudability Imputación de costes de contenedores](https://www.apptio.com/products/cloudability/container-cost-allocation/ "(se abre en una pestaña o una ventana nueva)")

Nota:

Visite el [blog](https://www.apptio.com/emerge/cloud-cost-optimization-10-day-vs-30-day-rightsizing/ "(se abre en una pestaña o una ventana nueva)") para aprender a utilizar 10 o 30 días de uso de recursos para generar recomendaciones.

Antes de empezar

Nota: El dimensionamiento de contenedores utiliza el mismo agente informador y la misma infraestructura de datos que la funcionalidad de asignación de costes de contenedores. Si su organización ya utiliza esta funcionalidad en Cloudability, no necesita hacer nada para utilizar la redimensión de derechos.

Nota: Aunque se reducirán los costes asignados, no se producirá ningún ahorro real en Kubernetes hasta que se redimensionen los clusters.

Para utilizar Rightsizing para GCP, asegúrese de que dispone de:

- Aprovisione sus clústeres Kubernetes desplegando el agente opensource.

Más información sobre [el aprovisionamiento de clústeres en Kubernetes](k8s-cluster-provisioning.html)

Acceso al panel de control de Contenedores

En el menú de inicio de Cloudability, vaya a Optimizar > Redimensionar > Contenedores.

![contenedores en la captura de pantalla de redimensionamiento](../../../../03-media/cloudability-premium/images/kubernetes-rightsizing-dash-new.png)

Puede seleccionar Cargas de trabajo o el conmutador Clusters para elegir el tipo de recomendaciones.

Por defecto, los recursos se ordenan por ahorro de costes. Los recursos que encabezan la lista tienen el mayor potencial de ahorro.

Seleccione Exportar para descargar las recomendaciones en forma de hoja de cálculo. Se incluye información adicional sobre la cuenta, como la región, el sistema operativo, las etiquetas disponibles por recurso y la tarifa efectiva para los tipos de recursos actuales y nuevos.

El cuadro de mandos muestra lo siguiente:

Base de costes

- **A la carta** : Valores de ahorro basados puramente en precios a la carta. Aunque se incluyen los precios personalizados, no se incluye el impacto potencial de los compromisos (Instancias Reservadas (IR) o Planes de Ahorro (PA)).
- **Efectivo** : El coste efectivo de ejecutar su configuración actual. Tiene en cuenta el impacto histórico de los compromisos de forma similar a la métrica de Coste (Amortizado), en la que se incluyen todos los costes iniciales y recurrentes asociados. Para el tipo de instancia recomendada Nueva, las cifras de coste se basan en los precios bajo demanda porque la configuración Nueva puede no beneficiarse de RI o SP. Esta comparación es la opción más conservadora. Incluso si se aleja inadvertidamente de los RI o los SP, su nueva tarifa global seguirá siendo mejor. En consecuencia, el ahorro global notificado con esta metodología será a veces inferior. Si procede, se aplicarán precios personalizados a estas cifras.

Filtros

Al igual que con la función de asignación de costes de contenedores, puede aprovechar las vistas basadas en cuentas para filtrar las recomendaciones a un subconjunto de cuentas de su organización.

Para añadir un filtro:

1. Seleccione **Añadir filtro** en la barra de herramientas.
2. En la superposición de filtros, elija una Dimensión.
3. Seleccione un Operador para proporcionar una condición lógica.
4. Elija un valor para afinar el filtro.
5. Seleccione **Añadir filtro** para aplicar el nuevo filtro a la página.

Para quitar un filtro:

1. Seleccione el icono de filtro ![editar icono captura de pantalla](../../../../03-media/cloudability-premium/images/edit-icon.jpg).
2. Seleccione X junto al filtro que desea eliminar.

Aplicar filtros con enlaces

También puede añadir filtros seleccionando los valores hipervinculados en azul en la tabla principal. Sus filtros se añaden al Configurador de filtros.

Nota:

Sólo se puede seleccionar un valor o parámetro de cada columna a la vez.

Indicadores clave de rendimiento

Los indicadores clave de rendimiento (KPI) resumidos se muestran en función de las vistas y los filtros que haya seleccionado.

![captura de pantalla de contenedores kubernetes](../../../../03-media/cloudability-premium/images/containers-summary-kpis.jpg)

Los KPI resumidos incluyen:

- Gasto total : El gasto total asignado actual a través de todos los contenedores instrumentados en la plataforma Cloudability.
- Ahorro estimado por inactividad : Muestra el ahorro total estimado para todas las recomendaciones de Terminar.
- Ahorro estimado de Rightsize : Muestra el ahorro potencial total estimado que se puede conseguir con todas las recomendaciones de Rightsize.
- Gasto optimizado estimado: El gasto total estimado en todos los contenedores mostrados después de aplicar las recomendaciones.

Nota:

El cambio de tamaño de los contenedores ajusta la asignación de costes para los contenedores y módulos con esa especificación de contenedor, pero normalmente no afecta a su factura. La asignación de derechos a la especificación del contenedor permite disponer de capacidad en la implantación, que las organizaciones pueden utilizar para otras cargas de trabajo o para asignar derechos a la instancia informática subyacente. Redimensionar la instancia informática subyacente tendrá un impacto positivo en la factura de una organización.

Ver detalles de la recomendación

Para ver los detalles de un recurso concreto, seleccione  ![elipsis vertical captura de pantalla](../../../../03-media/cloudability-premium/images/cloudy-vertical-elipsis.jpg) > Ver detalles.

En el panel de detalles, Cloudability muestra al menos una recomendación, siendo la opción de menor riesgo la selección por defecto.

Cada opción incluye recomendaciones de petición y límite de memoria y CPU para una especificación de contenedor determinada. Los gráficos de recursos individuales muestran la asignación actual de recursos (en rojo) y el consumo (en azul) junto con los ajustes recomendados (en amarillo).

![pantalla de cargas de trabajo](../../../../03-media/cloudability-premium/images/rightsizing-recommendation-detail.jpg)

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
