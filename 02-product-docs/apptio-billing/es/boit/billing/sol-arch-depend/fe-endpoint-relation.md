---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Relaciones entre el front-end y el endpoint"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
  - "Arquitectura de soluciones y dependencias"
source_path: "boit/billing/sol-arch-depend/fe-endpoint-relation.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Relaciones entre el front-end y el endpoint

Aunque esta guía no profundiza en Frontdoor, es importante comprender cómo los usuarios llegan a Facturación.

- **Fundamentos de facturación**
  - Los usuarios abren la interfaz de Costing Essentials.
  - Billing Essentials aparece como una **recopilación de informes de facturación** dentro de ese proyecto.
  - No hay una entrada de aplicación separada para Billing Essentials.
- **Norma de facturación**
  - Los usuarios ven una **entrada de facturación independiente** en la aplicación front-end o en el selector de terminales.
  - Al seleccionar esta entrada, se abre la interfaz de Billing Standard, que está respaldada por los componentes de facturación instalados en el proyecto Costing Standard.
  - El acceso de los usuarios a Billing Standard se controla a nivel de punto final y dentro de las colecciones de informes.

Las dependencias subyacentes del proyecto (componentes, modelos, tablas) siempre se mantienen en TBM Studio. Los puntos finales simplemente definen cómo se agrupa y presenta ese contenido a los usuarios.
