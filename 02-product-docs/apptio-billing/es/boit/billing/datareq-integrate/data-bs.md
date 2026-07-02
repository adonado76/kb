---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Requisitos de datos para la norma de facturación"
breadcrumb:
  - "Billing"
  - "Requisitos e integración de datos"
source_path: "boit/billing/datareq-integrate/data-bs.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Requisitos de datos para la norma de facturación

Billing Standard utiliza un conjunto más amplio de componentes y, por lo tanto, un modelo de datos más amplio. Sigue necesitando los mismos fundamentos básicos que Essentials, pero los extiende a múltiples dominios.

Nota: Se aplica únicamente al estándar de facturación.

Tablas maestras y conjuntos de datos de dominio común:

- **Unidades y definiciones de unidades**
  - Unidades estandarizadas utilizadas en todos los ámbitos (por ejemplo, VM al mes, GB al mes, usuario designado al mes).
  - Se utiliza para mantener la coherencia y comparabilidad entre diferentes dominios.
- **Aplicaciones**
  - Datos maestros de la aplicación:
    - ID y nombre de la aplicación.
    - Equipo o función propietaria.
    - Estado del ciclo de vida (activo, en fase de retirada, retirado).
  - Relaciones con:
    - Servicios u ofertas.
    - Proyectos e iniciativas.
    - Consumidores, en diseños de facturación centrados en aplicaciones.
- **Infraestructura**
  - **Servidores** : ID del servidor, tipo, entorno, plataforma y propiedad.
  - **Almacenamiento** : asignaciones de grupos, niveles y capacidad de almacenamiento.
  - **Dispositivos de usuario final** : tipo de dispositivo, propietario, ubicación y reglas de asignación.

- **Nube**
  - Cuenta en la nube o ID de suscripción.
  - Asignaciones de proveedores y niveles de servicio.
  - Etiquetas o rótulos agrupados en:
    - Servicios u ofertas.
    - Consumidores.
    - Dimensiones de asignación de costes.
- **Proyectos**
  - Identificación y nombre del proyecto.
  - Tipo (capital, operativo, interno, externo).
  - Aplicaciones, servicios o productos relacionados.
  - Correspondencias entre el coste del proyecto y los resultados de facturación cuando los proyectos se facturan o se utilizan como consumidores.
- **Entidades jurídicas e impuestos**
  - Códigos de entidades jurídicas y empresas.
  - Atributos fiscales e interempresariales.
  - Se utiliza para la fijación de precios de transferencia y la presentación de informes a nivel de entidad jurídica.
- **Tablas maestras específicas de facturación**
  - Catálogo de ofertas facturables y listas de precios, similar a Essentials pero alineado con el modelo de dominio más rico.
  - Configuración de la tasa unitaria y la varianza por dominio.

Patrones de integración para el estándar de facturación:

- Las fuentes de datos son más amplias y suelen incluir:
  - CMDB y sistemas de activos.
  - Archivos de facturación y API de proveedores de servicios en la nube.
  - Herramientas PPM (para datos de proyectos).
  - Sistemas de recursos humanos o directorios (para la asignación de usuarios y propietarios).
  - Sistemas financieros para personas jurídicas y atributos fiscales.
- ETL e integración son:
  - A menudo se implementa con Datalink, plataformas de integración o procesos por lotes en TBM Studio.
  - Por lo general, se rige por una mayor propiedad de los datos y un mayor control de calidad, ya que hay más dominios y más partes interesadas.

El objetivo es modelar la tecnología y la realidad financiera una sola vez y, a continuación, reutilizar esos maestros de dominio en los procesos de cálculo de costes y facturación, en lugar de mantener listas separadas y duplicadas.
