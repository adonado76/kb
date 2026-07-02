---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Rellenar los datos maestros del dominio"
breadcrumb:
  - "Billing"
  - "Configuración del estándar de facturación (implementación)"
source_path: "boit/billing/config-bs/bs-pop-domain.html"
images:
  - "resources/images/boit_images/apps.png"
  - "resources/images/boit_images/cloud.png"
  - "resources/images/boit_images/server.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Rellenar los datos maestros del dominio

Los administradores de dominio habilitan los informes estándar de facturación que desglosan los cargos por aplicación, infraestructura, nube, proyecto y entidad legal.

## Aplicaciones

- Cargar o alinear datos maestros de la aplicación:
  - ID de la aplicación, nombre, propietario, estado del ciclo de vida, criticidad.
- Aplicaciones de mapas para:
  - Servicios u ofertas.
  - Consumidores (si las aplicaciones se tratan como consumidores).
  - Proyectos, si el trabajo del proyecto se centra en las aplicaciones.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/apps.png)

Fig. n.º: Tabla de datos maestros de aplicaciones vista desde TBM Studio

## Servidores, almacenamiento y dispositivos de usuario final

- **Servidores**
  - Asegúrese de que cada servidor (o grupo de servidores) tenga un ID, tipo, entorno, plataforma, propietario y asignación a servicios o consumidores.
- **Almacenamiento**
  - Mantener grupos o niveles de almacenamiento, capacidad y asignaciones a consumidores o servicios.
- **Dispositivos de usuario final**
  - Mantener el tipo de dispositivo (ordenador portátil, ordenador de sobremesa, VDI, etc.) usuario o grupo, y reglas de asignación.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/server.png)

Fig. n.º: Tabla de datos maestros de servidores vista desde TBM Studio

## Nube

- Patrón estándar:
  - Cargar los datos de facturación del proveedor en una tabla consolidada de uso de la nube.
  - Mantenga una tabla de asignación de etiquetas o cuentas que vincule:
    - Proveedor e ID de cuenta.
    - Etiquetas (por ejemplo, aplicación, propietario, centro de costes).
    - Identificadores de servicio y consumidor resultantes.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/cloud.png)

Fig. n.º: Tabla de datos maestros del proveedor de servicios en la nube vista desde TBM Studio

## Proyectos

- Rellene los datos maestros del proyecto con:
  - ID del proyecto, nombre, tipo, propietario.
  - Enlace a servicios, productos o aplicaciones.
  - Identifique qué proyectos, si los hay, se tratan como consumidores facturables.

**Personas jurídicas y relaciones entre empresas**

- Si los precios de transferencia están dentro del ámbito de aplicación:
  - Mantener una tabla de entidades jurídicas con atributos fiscales y normativos.
  - Asignar consumidores, servicios e infraestructura a entidades jurídicas.
  - Configurar la lógica de emparejamiento entre empresas (de entidad a entidad).
