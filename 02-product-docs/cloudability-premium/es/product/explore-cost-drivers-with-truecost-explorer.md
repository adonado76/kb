---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "TrueCost Explorer"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
source_path: "product/explore-cost-drivers-with-truecost-explorer.html"
images:
  - "images/explore_cost_drivers_1.jpg"
  - "images/topline-items.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# TrueCost Explorer

TrueCost Explorer le ayuda a comprender la estructuración de los archivos de facturación en nube. Ofrece una forma visualmente intuitiva de explorar sus datos de facturación y responder a preguntas sobre los inductores de costes.

![captura de pantalla de true cost explorer](../../../../03-media/cloudability-premium/images/explore_cost_drivers_1.jpg)

Caso práctico

La mayoría de los clientes han tenido una experiencia en la que los costes de transferencia de datos se disparan. En la mayoría de los casos, no es posible saber cuál de las docenas de atributos que su proveedor utiliza para identificar la transferencia de datos, así como las diversas formas en que la transferencia de datos puede manifestarse en el archivo de facturación (sólo en AWS hay más de 20.000 partidas distintas relacionadas con la transferencia de datos).

Con el explorador TrueCost, puede hacer lo siguiente:

- Haga clic en Añadir filtro y seleccione la dimensión Familia de uso que sea igual a Transferencia de datos. Podrá ver de una sola vez los costes de transferencia de datos de todos los proveedores. Además, independientemente del proveedor, los costes de transferencia de datos tienen un LeaseType de On-Demand. También puedes ver los servicios que generan los costes de transferencia de datos, que en este ejemplo son principalmente « AWS EC2 » y « Azure Networking».
- Ahora reorganice las columnas y añada la dimensión Operación para ver información adicional sobre los costes de transferencia de datos. Aquí, puede ver que en el lado Azure, sus costes de transferencia de datos son impulsados por la Transferencia de Datos hacia fuera. También puede ver que la gran mayoría de los costes de transferencia de datos son de InterZone. Dado que estos costes se refieren a la transferencia de datos entre zonas de disponibilidad dentro de AWS, seleccione la región y ajuste los filtros de trazado para ver cuántos gastos de transferencia de datos pequeños hay disponibles

Por lo tanto, aquí hemos aprendido que:

- Los costes de transferencia de datos se deben principalmente a las redes AWS EC2 y Azure, con otros 10 servicios que aportan cantidades menores
- Más del 80% de los costes de transferencia de datos están relacionados con el traslado de datos entre zonas de disponibilidad de AWS en US-East-1
- Azure La transferencia de datos se acumula principalmente en las regiones NorthCentralUS y WestEurope

Si desea comprender qué es lo que está determinando sus costes a nivel de recurso individual, haga clic en el nodo correspondiente y seleccione la opción Ver partidas principales.

![captura de pantalla de las partidas superiores](../../../../03-media/cloudability-premium/images/topline-items.jpg)

- **[Base de costes para la adaptación y Explorador de costes reales](../chatbot/cost-basis-for-rightsizing-true-cost-explorer.html)**
