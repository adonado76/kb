---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "es"
doc_type: "apptio-cost-management"
title: "Mapa de proveedores"
breadcrumb:
  - "Costing Essentials"
  - "Entorno de trabajo"
source_path: "apptio-cost-management/workbench/vendor-mapping.html"
images:
  - "resources/images/acm_images/vendor-missing-mapping.png"
  - "resources/images/studio_images/ce-vm-1_969x598.png"
  - "resources/images/studio_images/vm-2_950x589.png"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Mapa de proveedores

## Enriquecimiento de datos de proveedores

Esta pestaña ofrece la posibilidad de mejorar los metadatos de proveedores, obtenidos de la lista maestra de proveedores de IDP, y permite un análisis más completo de sus gastos de proveedores.

- Tipo de proveedor
- Proveedor Servicio principal
- Categoría de proveedor
- Es CSP (es un proveedor de servicios en nube)
- Gestor de proveedores y propietario
- Objetivo de gasto anual
  - Representa el presupuesto del proveedor para el año fiscal en curso, no el gasto total previsto a lo largo de la vida del proveedor (por ejemplo, un contrato de 3 años)

Una de las asignaciones clave en el enriquecimiento de datos laborales es la columna "Es CSP". Esto determinará qué proveedor se definirá como Proveedor de Nube y se asignará a los Datos Maestros de Nube en lugar de a las Soluciones basadas en el Workbench de Asignaciones de Proveedores. Al asignar el coste a los datos maestros de la nube, el coste se asignará a las soluciones basándose en una asignación específica de la nube a las soluciones ponderada por el importe de la factura de recursos.

## Mapeo de datos de Cloud Master

A diferencia de otros costes que se asignan a la capa de Soluciones, los costes de nube se basarán en las Cuentas y/o Servicios de Aplicación asociados a una Solución.

![](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/ce-vm-1_969x598.png)

## Asignación de proveedores

Permite asignar los gastos de proveedores directamente a tipos y categorías de soluciones, junto con una ponderación de asignación:

- Tipo de solución
- Categoría de la solución
- Oferta de soluciones
- Entrega (On Prem vs Public Cloud) \*\*
- Identificación de la oferta
- Proyecto ID \*\*
- Asignación Ponderación
  - Permite determinar el porcentaje de asignación de los gastos de proveedores a cada solución. La ponderación por defecto es 1 (100%) para cada proveedor; sin embargo, los usuarios pueden ajustar o dividir los porcentajes de proveedores en sus áreas correspondientes.

|  |  |  |
| --- | --- | --- |
|  | • | Tipo de solución |

|  |  |  |
| --- | --- | --- |
|  | • | Categoría de la solución |

|  |  |  |
| --- | --- | --- |
|  | • | Oferta de soluciones |

|  |  |  |
| --- | --- | --- |
|  | • | Entrega (On Prem vs Public Cloud) \*\* |

|  |  |  |
| --- | --- | --- |
|  | • | Identificación de la oferta |

|  |  |  |
| --- | --- | --- |
|  | • | Proyecto ID \*\* |

|  |  |  |
| --- | --- | --- |
|  | • | Asignación Ponderación |

|  |  |  |
| --- | --- | --- |
|  | • | Permite determinar el porcentaje de asignación de los gastos de proveedores a cada solución. La ponderación por defecto es 1 (100%) para cada proveedor; sin embargo, los usuarios pueden ajustar o dividir los porcentajes de proveedores en sus áreas correspondientes. |

\*\* Entrega e Id de proyecto son atributos opcionales que pueden utilizarse para aumentar la granularidad de las asignaciones. Por ejemplo, permitir que los proyectos de los mismos proveedores se asignen a diferentes ofertas de servicios.

![](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/vm-2_950x589.png)

## Asignaciones que faltan

Identifica a los proveedores que no han sido asignados a un tipo/categoría de solución y oferta(s).

![Asignación de proveedores ausentes](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/vendor-missing-mapping.png)
