---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Mesa de trabajo de cálculo de costes estándar"
breadcrumb: []
source_path: "cost-transparency/workbench/introduction.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Mesa de trabajo de cálculo de costes estándar

Apptio proporciona la capacidad de realizar una variedad de actualizaciones de datos de referencia y transaccionales que son comunes en la mayoría de las organizaciones y proporcionan un mayor valor y visibilidad de la solución. En muchos casos, es posible que los datos del sistema de origen no contengan toda la información necesaria para realizar las asignaciones y los informes en su solución Costing Standard .

El Workbench de la solución Costing Standard ofrece una interfaz intuitiva que permite a los usuarios designados enriquecer y mantener sus datos de forma eficaz. Incluye tablas editables que permiten a los usuarios colmar lagunas de datos y perfeccionar las asignaciones.

El acceso al Workbench se rige por los permisos de su organización, y puede que no todos los usuarios tengan el acceso necesario.

## Cartografía detallada de los informes

Cada informe de asignación específico, como Asignación de proveedores o Asignación de mano de obra, se estructura en dos pestañas principales:

**Enriquecimiento de datos**

Esta sección permite a los usuarios actualizar la información o introducir la información que falta. Por ejemplo, en Mapeo Laboral, los usuarios pueden editar campos como Equipo, Rol y Tipo de Empleado para cada ID Laboral. Sin embargo, no está permitido añadir nuevas filas en las tablas de enriquecimiento de datos y la información que falta debe proceder del sistema de origen (por ejemplo, el sistema de registro de RRHH).

**Cartografía de datos**

Esta sección permite a los usuarios asignar o prorratear costes a una o más soluciones, productos o unidades de negocio. Por ejemplo, en Vendor Mapping, un usuario puede asignar el coste de un proveedor, como el de SAP, a múltiples ofertas como SAP Financial Accounting y SAP Production Planning. Para ello se utiliza la columna Ponderación.

Ejemplo:

1. Prorratear el 60% de SAP Coste de proveedores a SAP Contabilidad financiera y el 40% a SAP Planificación de la producción
2. Haga clic con el botón derecho del ratón en la fila SAP Proveedor y seleccione "Duplicar fila".
3. Introduzca el Tipo de solución, la Categoría de solución y los ID de oferta para ambas filas. Los nombres de las ofertas deberían rellenarse automáticamente.
4. Introduzca ' 0.6 ' en la columna Ponderación para la oferta SAP Contabilidad Financiera y ' 0.4 ' para la oferta SAP Planificación de la Producción.
