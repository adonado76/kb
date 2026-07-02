---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Redimensionamiento avanzado para contenedores de Kubernetes"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto avanzado"
source_path: "product/advanced-k8s-container-rightsizing.html"
images:
  - "images/advanced-k8s-container-rightsizing-cs-details.png"
  - "images/advanced-k8s-container-rightsizing-wc-details.png"
  - "images/advanced-k8s-container-rightsizing.png"
  - "images/edit-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Redimensionamiento avanzado para contenedores de Kubernetes

Puede utilizar el panel de control de ajuste avanzado para ver las recomendaciones de optimización de recursos para sus implementaciones de contenedores de Kubernetes. El panel de control muestra recomendaciones de optimización tanto para ahorros como para inversiones, impulsadas por un motor de optimización de cartera ( Turbonomic ).

[Redimensionamiento avanzado en Cloudability Premium](advanced-rightsizing-powered-by-turbonomic.html)

Antes de empezar

Para ver el panel de control de contenedores, asegúrese de haber instalado los agentes Cloudability y Turbonomic Kubernetes en cada uno de sus clústeres

Nota: Debe asegurarse de que tanto el agente de métricas Cloudability como los agentes Kubeturbo Turbonomic estén presentes en cada uno de sus clústeres Kubernetes. Siga las instrucciones de instalación que se describen aquí: [Provisión de agentes de Kubernetes.](advanced-rightsizing-powered-by-turbonomic.html)

Acceder al panel de control de contenedores

Para acceder al panel de control de Containers, abra la página de inicio de Cloudability y, en el menú de navegación izquierdo, seleccione Optimizar > Redimensionamiento > Avanzado. En la página Rightsizing, seleccione la pestaña Contenedores. Puede ver todas las acciones de optimización **del redimensionamiento** del controlador de carga de trabajo impulsadas por el motor Turbonomic.

![](../../../../03-media/cloudability-premium/images/advanced-k8s-container-rightsizing.png)

Personalizar el panel de control

Puede configurar las siguientes opciones para personalizar su panel de control.

Especificar la base del coste

La base de costes determina cómo se calculan las recomendaciones. La base de coste puede ser bajo demanda o efectiva. La base del coste efectivo se selecciona de forma predeterminada.

Utilice la base de costes bajo demanda si desea eliminar la naturaleza impredecible de los descuentos basados en compromisos de su análisis y maximizar el número de recomendaciones que se le proporcionan. Utilice la base de coste efectivo si prefiere basar sus recomendaciones en el coste real histórico de ejecutar sus instancias y adoptar un enfoque conservador.

Seleccionar cuenta

De forma predeterminada, el panel muestra recomendaciones para todas las cuentas. Para ver las recomendaciones para una cuenta en particular, seleccione el nombre de la cuenta en el menú desplegable Cuenta.

Aplicar filtros

Puede añadir filtros para incluir o excluir datos en función de una o varias condiciones.

Añadir un filtro

Para añadir un filtro:

1. Selecciona Añadir filtro en la barra de herramientas.
2. En el menú Añadir filtro, elige una dimensión.
3. Seleccione un operador para proporcionar una condición lógica.
4. Elija un valor para refinar su filtro.
5. Seleccione Añadir filtro para aplicar el nuevo filtro a la página.

Aplicar filtros con enlaces

También puede añadir filtros seleccionando los valores con hipervínculos azules de la tabla principal. La regla de filtro se aplica automáticamente al campo Filtros. Solo puede seleccionar un valor o parámetro de cada columna a la vez.

Eliminar un filtro

Para eliminar un filtro:

1. Seleccione el icono del filtro ![icono de filtro](../../../../03-media/cloudability-premium/images/edit-icon.jpg) .
2. Seleccione X junto al filtro que desea eliminar.

Indicadores clave de rendimiento

Puede ver los siguientes indicadores clave de rendimiento (KPI) en su panel de control de Advanced Rightsizing:

- Gasto total : muestra el gasto total asignado actualmente
- Ahorros potenciales : muestra el ahorro potencial total estimado que se puede conseguir con todas las recomendaciones de optimización con un impacto en los costes menor que el coste actual
- Inversiones necesarias : muestra el total estimado de inversiones potenciales en todas las recomendaciones de optimización con un impacto en los costes superior al coste actual

Tabla de recomendaciones de redimensionamiento

El panel de control contiene una tabla de recomendaciones de redimensionamiento, que ofrece una visión general de los recursos del controlador de carga de trabajo para los que se han identificado recomendaciones. La tabla incluye las siguientes columnas:

Nota:

De forma predeterminada, los datos se ordenan por la columna Impacto en el coste. Para cambiar el orden de clasificación, solo tienes que seleccionar el nombre de la columna.

- Estado: Estado que indica la disponibilidad para la ejecución de la acción
- Nombre del controlador de carga de trabajo : El nombre del recurso del controlador de carga de trabajo
- Nombre del clúster de contenedores : El nombre del clúster
- Espacio de nombres: El espacio de nombres configurado
- Réplicas : el número de réplicas configuradas
- Riesgo : El riesgo identificado por un motor de Turbonomic
- **Coste** : el coste actual de la instancia del controlador de carga de trabajo
- Categoría de la acción : La categoría de la acción recomendada. Los que se admiten actualmente son «Rendimiento» o «Ahorro»
- Acción : La acción recomendada. La tabla siguiente enumera las distintas acciones compatibles
- Impacto en los costes : Impacto en los costes de la implementación de esta medida

| Recomendación | Descripción |
| --- | --- |
| Escala | Acción de cambio de tamaño recomendada por el motor de optimización. Esto puede ser una acción de «ampliación» o «reducción» según las políticas configuradas |

Recomendaciones para optimizar las exportaciones a un archivo Excel

Para exportar las acciones recomendadas a un archivo Excel, seleccione Exportar. Tenga en cuenta que el archivo Excel incluirá varias columnas adicionales, como región, sistema operativo, precio unitario y otras.

Detalles de la recomendación

Para ver los detalles de la acción recomendada para un recurso concreto, seleccione Ver detalles en el menú Más opciones (3 puntos). Esto muestra los detalles del controlador de carga de trabajo seleccionado.

La siguiente figura muestra un panel de detalles de acciones del controlador de carga de trabajo de muestra.

![](../../../../03-media/cloudability-premium/images/advanced-k8s-container-rightsizing-wc-details.png)

Verá una lista de cargas de trabajo en la sección «Cargas de trabajo» más arriba. Para ver los detalles de una carga de trabajo concreta, seleccione Ver detalles en el menú Más opciones (3 puntos). Esto muestra los detalles de la carga de trabajo seleccionada.

![](../../../../03-media/cloudability-premium/images/advanced-k8s-container-rightsizing-cs-details.png)

**Tema principal:** [Redimensionamiento avanzado](../product/advanced-rightsizing-powered-by-turbonomic.html)
