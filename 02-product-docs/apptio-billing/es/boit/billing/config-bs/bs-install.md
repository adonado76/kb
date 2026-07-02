---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Instalación de componentes estándar de facturación"
breadcrumb:
  - "Billing"
  - "Configuración del estándar de facturación (implementación)"
source_path: "boit/billing/config-bs/bs-install.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Instalación de componentes estándar de facturación

El estándar de facturación se envía como un conjunto de componentes instalados en el proyecto estándar de costes existente. El punto final Billing Standard en el front-end muestra el contenido creado por estos componentes.

Componentes típicos (los nombres pueden variar ligeramente según la versión):

- Fundacional
- unidades
- Servicios/Ofertas (a menudo parte de la Fundación)
- Aplicaciones
- Servidores
- Almacenamiento
- Dispositivos de usuario final
- Nube
- Proyectos
- Precio
- Variación de costes
- Variación del plan
- Precios de transferencia entre empresas

Pasos generales:

1. Abre el **proyecto Costing Standard** en TBM Studio.
2. Navegue hasta el área de gestión de componentes.
3. Seleccione e instale los componentes necesarios de Billing Standard.
4. Confirme la instalación:
   - Añade los modelos, conjuntos de datos, tablas y métricas esperados.
   - Crea colecciones de informes que aparecerán en el punto final Billing Standard.

Comprobaciones posteriores a la instalación:

- Todos los modelos Billing Standard se compilan correctamente en In Development.
- Las tablas de dominios clave (aplicaciones, servidores, almacenamiento, nube, proyectos, dispositivos, entidades legales, unidades, precios) son visibles en el modelo de datos.
- El punto final del estándar de facturación se aprovisiona y se vincula al proyecto, incluso si los informes aún no se han promovido.
