---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Objetos modelo"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
source_path: "studio/new-uc/reference/model-studio-reference/model-objects.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Objetos modelo

Los objetos del modelo son los componentes básicos fundamentales de un modelo de costes de TBM Studio. Cada objeto del modelo representa una capa o entidad concreta dentro de la estructura de costes de su organización, como fuentes de costes, proveedores, aplicaciones o unidades de negocio.

## Tipos de objetos de modelo y sus finalidades

TBM Studio admite un tipo de objeto de modelo unificado que puede cumplir diferentes funciones en función de su posición en la jerarquía del modelo y de su configuración.

**Objeto modelo**

**Descripción:** Para crear un objeto de modelo, hay que añadir un paso «Modelo» al proceso de transformación de una tabla. Esto convierte la tabla en una entidad modelada que puede participar en asignaciones, recibir factores determinantes y procesar métricas a través del modelo de costes.

**Objetivo:** Los objetos de modelo agrupan datos para su análisis y definen relaciones de asignación. Pueden actuar como objetos de origen (que aportan valor), objetos de destino (que reciben valor) o ambos.

**Funciones comunes de los objetos del modelo**

|  |  |  |
| --- | --- | --- |
| **Rol** | **Descripción** | **Ejemplos** |
| Fuente del coste | Punto de entrada para los datos financieros. Normalmente contiene datos del libro mayor o de facturas con los responsables de cada unidad. | Datos reales de origen de costes, Libro mayor, Libro mayor de activos fijos |
| Grupo de costes | Capa de agrupación intermedia. Recibe asignaciones de las fuentes de financiación y las distribuye entre la infraestructura o los servicios. | Mano de obra, instalaciones, activos fijos, licencias de software |
| Infraestructura | Capa de recursos tecnológicos. Representa activos físicos o virtuales. | Servidores, almacenamiento, redes, centros de datos |
| Servicio | Capa de servicios de TI. Representa los servicios que consume la empresa. | Servicios tecnológicos, aplicaciones, soluciones |
| Consumidor | Destino final de la imputación de costes. Representa a los clientes empresariales. | Unidades de negocio, departamentos, proyectos, clientes |

*→ Consulte [las capas del marco TBM para obtener una visión general conceptual](../../concepts-architecture/model-architecture/model-concepts-overview.html)*

*→ Consulta [«Crear un objeto modelo» para obtener instrucciones paso a paso](../../howtoguides/build-cost-model/create-model-rep.html)*

- **[Propiedades del objeto modelo](../../../../studio/new-uc/reference/model-studio-reference/model-objects-properties.html)**
- **[Relaciones y dependencias entre objetos](../../../../studio/new-uc/reference/model-studio-reference/objects-relationships.html)**
- **[Convenciones de nomenclatura de objetos](../../../../studio/new-uc/reference/model-studio-reference/object-naming-convention.html)**
