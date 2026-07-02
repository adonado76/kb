---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Conceptos básicos: servicios, unidades, tarifas, recuperación, diarios"
breadcrumb:
  - "Billing"
  - "cómo empezar"
  - "Introducción a la facturación"
source_path: "boit/billing/getting-started/core-concepts.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Conceptos básicos: servicios, unidades, tarifas, recuperación, diarios

El resto de esta guía se basa en un pequeño conjunto de conceptos recurrentes. Entenderlos aquí reduce la confusión más adelante.

## Servicios, productos y ofertas

La facturación necesita algo **que facturar**. Esto se suele modelar como un catálogo de servicios o productos.

Patrones comunes:

- **Servicio** : Oferta tecnológica consumida por las unidades de negocio (por ejemplo, «Correo electrónico y colaboración», «Base de datos gestionada», «Servidor virtual»).
- **Producto** : Oferta tecnológica en forma de producto, a menudo con versiones, niveles o paquetes definidos.
- **Oferta** : término genérico para cualquier elemento facturable que pueda aparecer en una línea de factura.

Cada oferta suele incluir:

- Un **nombre** que reconocen los actores del mundo empresarial.
- Una **unidad de medida** (por ejemplo, GB al mes, usuario al mes, máquina virtual al mes).
- Una o más **tarifas** y **factores** utilizados para calcular los cargos.

En Billing Essentials, las ofertas se gestionan normalmente mediante tablas e informes que definen qué elementos son facturables y a qué tarifa.

En Billing Standard, las ofertas suelen asignarse a varios dominios (servicios, aplicaciones, infraestructura, nube, proyectos) para realizar un análisis más detallado.

## Unidades y consumo

Una **unidad** es la cantidad medible de una oferta consumida en un período:

- Número de usuarios.
- Capacidad de almacenamiento.
- Horas de CPU.
- Entradas gestionadas.
- Horas o puntos del proyecto.

**El consumo** es el registro de esas unidades por consumidor y período. La facturación se basa en:

- **Claves** coherentes (por ejemplo, consumidor, período, oferta).
- Un **intervalo de tiempo** (normalmente mensual).
- Asignación clara al catálogo de ofertas facturables.

Conceptualmente:

Unidades × Tarifa = Cargo por una oferta, un consumidor y un período determinados.

**Tarifas y métodos de fijación de precios**

Una **tarifa** es la cantidad que se cobra por unidad. Las tarifas se pueden diseñar de múltiples maneras:

- **Basado en el coste** : Establecer igual al coste unitario de Costing.
- **Coste más** : Añadir un margen de beneficio o un porcentaje de gastos generales.
- **Basado en el precio** : Utilice un precio definido que puede ser superior o inferior al coste.
- **Basado en el presupuesto** : Establezca tarifas para recuperar un presupuesto objetivo en lugar del coste actual.
- **Híbrido** : Combina enfoques, por ejemplo, basado en los costes para algunos servicios y basado en los precios para otros.

Billing Essentials se centra en la tarificación directa ( PxQ ) y los ajustes básicos.

Billing Standard admite escenarios de tarifas más complejos y análisis de tarifas específicos del dominio (por ejemplo, vistas de tarifas unitarias por tipo de infraestructura o servicio en la nube).

## Consumidores y devolución de cargos frente a devolución de pagos

Un **consumidor** es la entidad a la que se le factura:

- Unidad de negocio o función.
- Región o geografía.
- Centro de coste o departamento.
- Proyecto o línea de productos, dependiendo del diseño.

La facturación admite ambos:

- **Showback** : Proporcionar visibilidad de los cargos sin transferencia financiera real.
- **Contracargo** : Registro de cargos en los sistemas financieros y tratamiento de los mismos como ingresos y gastos internos.

La misma configuración de facturación puede admitir showback, chargeback o una combinación de ambos, dependiendo de cómo se utilicen los diarios y de los acuerdos existentes con el departamento financiero.

## Facturas, diarios y archivos

Los resultados de facturación se dividen generalmente en tres categorías:

- **Facturas / Facturas**
  - Vistas a nivel de línea o resumidas de los cargos por oferta, consumidor y período.
  - Utilizado por las unidades de negocio y los propietarios de servicios o productos para comprender y discutir los cargos.
- **Diarios**
  - Datos estructurados que representan la visión contable de los cargos.
  - Utilizado por Finanzas para contabilizar asientos en el libro mayor u otros sistemas financieros.
- **Archivadores**
  - Instantáneas de los resultados de facturación para un período determinado.
  - Se utiliza para auditorías, cumplimiento normativo y análisis histórico.

Billing Essentials se centra en vistas tipo factura, tablas maestras de facturación sencillas y archivos.

Billing Standard añade vistas específicas del dominio y análisis de variaciones adicionales a esos conceptos básicos.
