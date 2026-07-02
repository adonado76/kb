---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Productos Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de la solución"
  - "Productos"
source_path: "cost-transparency/solution-uc/product-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Productos Introducción

El componente TCO del producto permite a las organizaciones modelar, calcular y analizar el coste total de propiedad (TCO) de los productos a lo largo de todo su ciclo de vida. Proporciona transparencia integral en los costes de los productos al conectar los datos financieros y operativos, lo que permite a los equipos de Producto, Finanzas y Tecnología comprender los factores que influyen en los costes, realizar un seguimiento del gasto a lo largo del ciclo de vida y alinear las decisiones de inversión con los resultados estratégicos. Este componente forma parte del conjunto de productos de contenido de productos y permite una gestión financiera coherente y centrada en los productos en toda la cartera.

## Instalación de componentes

La solución Product TCO se habilita a través de dos nuevos componentes creados para la solución. Son los siguientes:

- Costo total de propiedad del producto
- Informes sobre el coste total de propiedad del producto

**Nota:** Estos componentes están disponibles en las plantillas **v120 y posteriores**.

## Prerrequisito

Debe instalar los siguientes componentes antes de instalar el componente TCO del producto:

- CTF: Fuente de costes
- CTF- Trabajo
- CTF- Torres de TI
- CT Apps: aplicaciones
- Aplicaciones de TC - Servicios
- CT - Unidades de negocio

## Fuentes comunes de datos

El TCO del producto aprovecha los datos financieros y operativos de múltiples sistemas empresariales. Los datos sobre costes suelen obtenerse del libro mayor, incluyendo OpEx y CapEx en todos los grupos de costes y cuentas. Los datos de apoyo suelen proceder de carteras de aplicaciones, sistemas de gestión de proyectos e inversiones, herramientas de seguimiento del tiempo y la mano de obra, y plataformas de gestión de proveedores o contratos. Estas fuentes permiten atribuir con precisión los costes a los productos y respaldan el análisis del ciclo de vida y a nivel de cartera.

**Conjuntos de datos**

Es posible que tenga que cargar la tabla del feed del catálogo de productos y asignarla al conjunto de datos maestro de All Business Services proporcionado dentro del componente.

Además, para clasificar las ofertas como productos, seleccione **Todos los servicios empresariales** como destino y establezca **Tipo de oferta de servicio = Producto** en el campo Oferta de servicio.
