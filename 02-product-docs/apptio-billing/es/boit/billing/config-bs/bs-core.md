---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Tablas y relaciones del dominio principal"
breadcrumb:
  - "Billing"
  - "Configuración del estándar de facturación (implementación)"
source_path: "boit/billing/config-bs/bs-core.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Tablas y relaciones del dominio principal

La fortaleza de Billing Standard proviene de su modelo rico en dominios. Como mínimo, espere trabajar con las siguientes familias de tablas:

- **Catálogo de servicios/ofertas**
  - ID, nombre, unidad de medida, estado del ciclo de vida, indicador de facturación.
- **Consumidores**
  - Compartido con Costing o alineado con él.
  - Identificación del consumidor, nombre, jerarquía y atributos como región, función o gerente.
- **Unidades y definiciones de unidades**
  - Unidades estándar (por ejemplo, VM al mes, GB al mes, usuario designado al mes, ticket al mes).
  - Correspondencias entre medidas específicas de un dominio y unidades estándar.
- **Aplicaciones**
  - ID de la aplicación, nombre, propietario, estado del ciclo de vida.
  - Enlaces a servicios/ofertas y, posiblemente, a proyectos y consumidores.
- **Los servidores y el almacenamiento**
  - Servidores: ID, tipo, entorno, plataforma, propiedad, capacidad.
  - Almacenamiento: grupo, nivel, capacidad, asignación o mapeo a consumidores/servicios.
- **Dispositivos de usuario final**
  - ID o grupo del dispositivo, tipo de dispositivo, propietario, ubicación, reglas de asignación.
- **Nube**
  - Proveedor, ID de cuenta/suscripción, tipo de servicio.
  - Asignaciones de etiquetas a servicios, consumidores y dominios.
- **Proyectos**
  - ID y nombre del proyecto, tipo ( CapEx/OpEx/other ), propietario, servicios o aplicaciones vinculados.
- **Entidades jurídicas / precios de transferencia** (si procede)
  - Identificación de la entidad jurídica, nombre, país, atributos fiscales, relaciones de emparejamiento entre empresas.
- **Tablas de precios y variaciones**
  - Listas de precios, configuración de costes frente a planes frente a precios, categorías de variaciones.

Estas tablas están diseñadas para funcionar juntas. Evita crear tablas personalizadas aisladas que dupliquen su propósito, a menos que haya una razón clara para ello.
