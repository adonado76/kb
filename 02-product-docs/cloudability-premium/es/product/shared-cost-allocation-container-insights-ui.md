---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Asignación de costes compartidos - Container Insights UI"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
  - "Imputación de los costes de los contenedores"
source_path: "product/shared-cost-allocation-container-insights-ui.html"
images:
  - "images/container_cost_allocation.jpg"
  - "images/namespace.jpg"
  - "images/shared_rules.jpg"
  - "images/shared_rules1.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Asignación de costes compartidos - Container Insights UI

Estamos introduciendo una nueva función de imputación de costes de contenedores que transforma la forma de realizar el seguimiento de los gastos de infraestructura compartida en los entornos Kubernetes. Esta función permite a los clientes anotar y asignar costes de infraestructura compartidos, como proxies de sistemas, herramientas de supervisión y otros recursos operativos, a propietarios de aplicaciones o centros de costes específicos.

Anteriormente, estos costes de infraestructura compartida se declaraban indistintamente como gastos de carga de trabajo estándar. Ahora, las organizaciones pueden etiquetar y distribuir con precisión estos costes operativos, proporcionando a los equipos de aplicaciones y a los responsables financieros una visión más transparente y granular de su verdadero gasto total en infraestructura.

Para empezar, esta capacidad admite la asignación de costes compartidos a nivel del espacio de nombres Kubernetes. En el futuro ampliaremos la compatibilidad a otras construcciones de Kubernetes.

## Principales características

Identificación automatizada de costes compartidos

- Reconoce automáticamente los costes de infraestructuras compartidas a partir de espacios de nombres predefinidos:

  - `kube-system`
  - `Cloudability`

- Aplicado de manera uniforme en todos los grupos

Controles administrativos flexibles

- Cloudability los administradores pueden:

  - Definir normas de costes de infraestructura compartida para los espacios de nombres aplicables
  - Configurar asignaciones de costes específicas de la organización o del clúster
  - Determinar con precisión las cargas de trabajo relacionadas con la infraestructura (espacios de nombres) y la fecha de entrada en vigor de las normas

Nuevas métricas de costes

- Se han introducido nuevas métricas de costes en la interfaz de usuario de Container Insights para proporcionar visibilidad de los costes compartidos asignados, incluido el coste compartido, así como los recursos específicos de red compartida, memoria compartida, CPU compartida, GPU compartida y otros. Esta métrica de costes compartidos refleja el coste total, incluidos los costes compartidos asignados, una vez aplicadas las normas compartidas.

Nota:

Los costes compartidos solo se calcularán a partir de la fecha de lanzamiento de la función. Las consultas que incluyan fechas anteriores a la fecha de lanzamiento mostrarán resultados vacíos en la columna «*Coste compartido* ».

Cómo configurar las reglas de gestión de recursos compartidos

Para configurar la asignación de costes compartidos, utilice Manage Share Rules en la interfaz Container Insights para definir cómo deben distribuirse los costes compartidos en los espacios de nombres de Kubernetes.

1. Vaya a la interfaz de usuario de asignación de costes de contenedores.
2. Localice el menú de elipsis (...) en la esquina superior derecha, junto al botón Provision Clusters.
3. Haz clic en la elipsis para abrir un menú desplegable.
4. En el menú desplegable, seleccione Gestionar reglas de uso compartido. ![pantalla de imputación de costes de contenedores](../../../../03-media/cloudability-premium/images/container_cost_allocation.jpg)
5. Configurar reglas y proporcionar la fecha de entrada en vigor.![captura de pantalla de normas compartidas](../../../../03-media/cloudability-premium/images/shared_rules.jpg)![captura de pantalla de normas compartidas](../../../../03-media/cloudability-premium/images/shared_rules1.jpg)
6. Seleccione Todos los clústeres para la configuración a nivel de organización o elija un clúster específico del desplegable para la configuración a nivel de clúster. A continuación, especifique los valores del espacio de nombres para asignar los costes compartidos.
7. Guardar cambios.

La métrica de costes compartidos proporciona una mayor visibilidad de los costes totales de sus espacios de nombres Kubernetes, incluidos los costes compartidos asignados. Una vez aplicadas las reglas de costes compartidos, la columna Coste compartido refleja el coste combinado, distribuyendo los recursos compartidos proporcionalmente entre los espacios de nombres seleccionados.

Esta función garantiza una mayor precisión en la asignación de costes para los procesos de showback y chargeback, ayudándole a contabilizar la infraestructura compartida y el uso de recursos de forma eficaz.

![captura de pantalla de clusters compartidos](../../../../03-media/cloudability-premium/images/namespace.jpg)

## Concienciación del cliente: Comportamientos conocidos y aclaraciones

Para garantizar una experiencia sin problemas, tenga en cuenta lo siguiente:

- Sólo normas con fecha futura
  - Las reglas para la imputación de costes compartidos sólo pueden crearse, actualizarse o eliminarse para fechas futuras (en UTC).
  - Los cambios no se aplicarán retroactivamente a los datos históricos.

- Fechas de entrada en vigor de las actualizaciones y supresiones de normas
  - Las actualizaciones o supresiones de reglas no surten efecto inmediatamente.
  - En su lugar, se creará una nueva regla programada con el valor actualizado o vacío, que entrará en vigor en la fecha programada.

- Relación de unión para varias reglas
  - Cuando se aplican varias normas, funcionan como una unión.
  - Ejemplo: Si una regla de «Todos los clústeres» incluye los espacios de nombres A y B, y una regla para *el clúster «foo»* incluye el espacio de nombres C, entonces los tres espacios de nombres (A, B y C) se considerarán costes compartidos para *el clúster «foo* ».

- Vaciar el coste compartido antes de la fecha de lanzamiento de la función
  - Si una consulta incluye fechas anteriores a la fecha de publicación, la columna «Coste compartido» aparecerá vacía, ya que los costes compartidos no se calculan con carácter retroactivo.
- Espacio de nombres compartido que refleja un importe de coste compartido distinto de cero
  - Si observas un coste compartido distinto de cero para un espacio de nombres compartido concreto, como `kube-system`, es probable que se deba a que dicho espacio de nombres se encuentra en un nodo que no tiene cargas de trabajo de aplicaciones no compartidas (espacios de nombres). Esto hará que el coste de reparto equitativo se refleje como el coste compartido de este espacio de nombres, ya que no hay cargas de trabajo «normales» con las que repartir el coste en el nodo.

**Tema principal:** [Imputación de costes de contenedores](../product/k8s-cost-allocation.html)
